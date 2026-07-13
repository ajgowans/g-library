# Cover Image Handoff

The cover system is designed to avoid repeated web lookups. The private repo stores master/display/thumb image files locally. The public mirror exposes the manifest and reports, but not the private image cache.

## What Exists

- `data/reference/cover_images.csv` is the cover manifest.
- `assets/covers/master/` stores master images.
- `assets/covers/display/` stores standard viewer images.
- `assets/covers/thumb/` stores thumbnails.
- `reports/cover_gaps.csv` lists visual-viewer publications missing covers.
- `reports/cover_gaps_owned.csv` lists owned publications missing covers.
- `reports/cover_quality_flags.csv` lists covers needing review.
- `reports/cover_quality_review.html` is the review page.
- `reports/visual_collection_viewer.html` links to generated visual views.

## Research CSV Format

When asking an external assistant to find cover sources, request CSV with this header:

```csv
publication_id,display_title,series,issue_number,cover_type,source_name,source_page_url,image_source_url,confidence,notes
```

Rules:

- `publication_id` must exactly match `reports/cover_gaps.csv` or `reports/cover_gaps_owned.csv` where available.
- `cover_type` should be `Cover A` for standard/original cover.
- `source_page_url` should be the issue page used for verification.
- `image_source_url` should be a direct image URL if available, otherwise the issue page URL can be used for supported sources.
- `confidence` should be `high`, `medium`, or `review`.
- `notes` should mention why the image is the original regular cover.

## Import A Research CSV

Example:

```bash
python3 scripts/import_cover_sources.py ~/Downloads/new_cover_sources.csv --report reports/cover_source_import_new_batch.csv
python3 scripts/fetch_cover_images.py --publication-id-csv reports/cover_source_import_new_batch.csv --missing --timeout 20
python3 scripts/cover_quality_report.py
python3 scripts/cover_gap_report.py
python3 scripts/build_visual_viewer.py
python3 scripts/build_public_mirror.py
```

Use `--dry-run` before fetching if you want to preview:

```bash
python3 scripts/fetch_cover_images.py --publication-id-csv reports/cover_source_import_new_batch.csv --missing --dry-run
```

Fetching from the web requires network access. If network access is blocked, rerun the same command after approving the network request.

## Import Local High-Resolution Files

Put local image files in an inbox folder such as:

```text
inbox/covers/warhammer_monthly_high_res/
```

Then run:

```bash
python3 scripts/import_local_cover_images.py inbox/covers/warhammer_monthly_high_res
python3 scripts/cover_quality_report.py
python3 scripts/cover_gap_report.py
python3 scripts/build_visual_viewer.py
python3 scripts/build_public_mirror.py
```

The local importer currently maps Warhammer Monthly filenames like:

- `Warhammer_Monthly_71.jpg` -> `VIEW-warhammer-monthly-71`
- filenames containing `gratis` or `birthday` -> `VIEW-warhammer-monthly-free-birthday-special-1`
- filenames containing `awesome`, `promo`, or `full_color` -> `VIEW-deathwing-special-promotional-issue-1`

If files do not map, check `reports/local_cover_import_report.csv`.

## Rebuild Display/Thumbnail Files Offline

If master images already exist and only display/thumb files need rebuilding:

```bash
python3 scripts/fetch_cover_images.py --offline --missing
```

For a specific publication:

```bash
python3 scripts/fetch_cover_images.py --offline --force --publication-id PUB-BAT-0404
```

## Current Known Cover Follow-Ups

- Warhammer Monthly `#69` and `#70` still need higher-resolution files.
- `reports/cover_gaps_owned.csv` is the best next queue for covers that matter most in the collection.
- `reports/cover_quality_flags.csv` is the best queue for suspicious or low-quality images.

## Commit Guidance

- Commit generated images under `assets/covers/master`, `assets/covers/display`, and `assets/covers/thumb` in the private repo.
- Do not commit `inbox/`; it is ignored and should remain a local drop zone.
- Regenerate and push the public mirror after reports change.
