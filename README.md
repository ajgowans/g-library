# Comics / Gotham Library

Repo starter pack for Andrew's comics database.

## Current imported data

- Batman rows: 707
- Other rows: 140
- Heavy Metal rows: 20
- Warhammer manual intake rows: 52
- Total rows: 920

## What this version contains

- `data/raw/` - untouched exports from the current spreadsheet tabs.
- `data/manual/warhammer_intake.csv` - manual intake sheet for Warhammer comics before they become a fuller source tab.
- `data/processed/comics_master.csv` - merged and lightly normalised master comics table.
- `data/reference/collection_areas.csv` - collection area labels such as Gotham, DC Other, Heavy Metal, and Warhammer.
- `data/reference/facsimiles_batman_seed.csv` - starter Batman facsimile checklist.
- `data/reference/collecting_strategy.csv` - collecting rules, including Cover A only for facsimiles, Absolute Batman, and Absolute Catwoman.
- `reports/facsimiles_missing.csv` - facsimiles not found in the uploaded collection data.
- `scripts/` - small Python scripts to regenerate reports locally.

## Setup and validation

Run:

```bash
python3 -m pip install -r requirements.txt
python3 scripts/validate_database.py
python3 scripts/privacy_audit.py --no-fail
python3 scripts/build_public_mirror.py
python3 scripts/import_collection.py
python3 scripts/audit_collection.py
python3 scripts/copy_report.py
python3 scripts/check_in_order.py --dry-run ORD-FAC-DC-411-NONFOIL
python3 scripts/cleanup_report.py
python3 scripts/story_metadata_inbox.py
python3 scripts/story_metadata_authority_review.py
python3 scripts/order_report.py
python3 scripts/facsimile_report.py
python3 scripts/event_report.py
python3 scripts/story_arc_report.py
python3 scripts/series_run_report.py
python3 scripts/character_focus_report.py
python3 scripts/shop_lookup.py
python3 scripts/lookup.py "Batman 531"
python3 scripts/publication_report.py
python3 scripts/hidden_gotham_report.py
python3 scripts/wanted_report.py
python3 scripts/collecting_reports.py
python3 scripts/promote_story_decisions.py --dry-run
python3 scripts/fp_watcher.py --dry-run
```

## Immediate next steps

1. Commit this starter pack to `https://github.com/ajgowans/comics`.
2. Confirm which matching early issues are facsimiles versus originals/reprints.
3. Expand `facsimiles_batman_seed.csv` as new DC facsimiles are announced.
4. Add story checklist data for Knightfall, Contagion, Legacy, Cataclysm, Road to No Man's Land, and No Man's Land.


## v0.4 update

Facsimiles are now first-class entries in `data/reference/facsimiles_batman.csv`.

Generated reports:

- `reports/archive/` - manually preserved report snapshots, when a specific old generated report needs a named reference.
- `reports/manual_review/` - human review notes derived from reports; scripts should not overwrite this folder.
- `reports/collection_audit.csv` - data-quality and collector-uncertainty findings from `comics_master.csv`.
- `reports/ownership_to_confirm.csv` - owned/ambiguous rows to confirm against the physical collection.
- `reports/duplicate_candidates.csv` - possible duplicate title/issue rows.
- `reports/collection_audit_summary.csv` - counts by audit check.
- `reports/mia_items.csv` - items believed owned but currently not found.
- `reports/ordered_items.csv` - items ordered from retailers, including order status, arrival status, printing, cover, and price.
- `reports/ordered_not_arrived.csv` - ordered items that should not yet count as owned.
- `reports/copies_inventory.csv` - physical-copy inventory combining confirmed owned copy rows from `copies.csv` with pending ordered copies from `orders.csv`.
- `reports/copy_coverage_by_issue.csv` - issue-level copy counts, split into owned originals, owned facsimiles, ordered copies, variants, and readable copies.
- `reports/orders_to_check_in.csv` - parcel/check-in queue for ordered items that have not arrived.
- `reports/orders_to_check_in_summary.csv` - pending order counts grouped by retailer/status/format, with known price totals.
- `reports/orders_to_check_in_commands.csv` - ready-to-run dry-run and check-in commands for each pending order.
- `reports/tbc_story_items.csv` - owned rows whose story/event classification is still `TBC`.
- `reports/format_to_confirm.csv` - owned rows whose copy type is still uncertain.
- `reports/format_cleanup_priority.csv` - prioritized version of format uncertainty, with decision IDs and suggested copy buckets.
- `reports/format_cleanup_summary.csv` - counts for format cleanup by priority and decision status.
- `reports/story_metadata_work_queue.csv` - prioritized queue for story metadata gaps and TBC rows.
- `reports/story_metadata_backfill_candidates.csv` - review-ready metadata rows suggested from existing collection story labels.
- `reports/story_metadata_cleanup_summary.csv` - counts for story metadata cleanup by priority/source/status.
- `reports/event_zero_hour_checklist.csv` - Zero Hour core and tie-in checklist with ownership status.
- `reports/event_bloodlines_checklist.csv` - Bloodlines annual crossover checklist with ownership status.
- `reports/event_owned.csv` - event checklist rows currently owned.
- `reports/event_missing.csv` - event checklist rows not currently matched in the collection.
- `reports/story_arc_inventory.csv` - story labels currently present in the collection, with owned/missing/MIA and uncertain-format counts.
- `reports/story_arc_summary.csv` - checklist coverage by curated story arc.
- `reports/story_arc_contagion_checklist.csv` - Contagion checklist with ownership and edition/format fields.
- `reports/story_arc_legacy_checklist.csv` - Legacy checklist with ownership and edition/format fields.
- `reports/story_arc_missing.csv` - curated story-arc checklist rows not currently matched in the collection.
- `reports/story_arc_editions_to_confirm.csv` - owned story-arc rows whose physical edition/copy type still needs confirmation.
- `reports/series_run_summary.csv` - issue-span summaries for imported runs such as Catwoman and Batman: Shadow of the Bat.
- `reports/series_run_gaps.csv` - gaps inside imported title spans, split into not-owned, MIA, and absent-from-sheet ranges.
- `reports/series_run_issues.csv` - issue-by-issue run status, story label, format, and notes.
- `reports/series_run_missing_issues.csv` - one row for every missing/unowned issue in Andrew's configured run ranges.
- `reports/series_run_metadata_gaps.csv` - configured run issues that still need story-arc metadata.
- `reports/readable_stories.csv` - stories readable through owned original issues, facsimiles, original-format publications, or collected editions.
- `reports/original_issues_still_wanted.csv` - issues readable via collected edition but still missing as individual comics.
- `reports/collections_owned.csv` - owned collected editions, original graphic novels, prestige books, and their contained issue coverage where known.
- `reports/publication_coverage.csv` - story-level coverage split into original issue, facsimile, and collection coverage.
- `reports/hidden_gotham_checklist.csv` - data-driven checklist for hidden Gotham-adjacent books to research or collect.
- `reports/privacy_audit.csv` - public-repo privacy audit covering secrets, `.env` files, local paths, contact info, scan/media files, large binaries, README, and licence presence.
- `public_mirror/` - generated public-safe mirror folder for GPT Classic/public GitHub sharing, built by `scripts/build_public_mirror.py` and intentionally ignored by git in the private working repo.
- `reports/wanted_items.csv` - consolidated shopping/watch list from missing run issues, story-arc gaps, and wanted facsimiles.
- `reports/batman_range_wantlist.csv` - practical wanted list for configured Batman/Detective run ranges, including edition/readability context.
- `reports/knightfall_to_knightsend_report.csv` - focused reading-order/coverage report driven by `data/reference/focused_report_sets.csv`.
- `reports/zero_hour_report.csv` - focused Zero Hour checklist/coverage report driven by `event_checklists.csv`.
- `reports/bloodlines_report.csv` - focused Bloodlines checklist/coverage report driven by `event_checklists.csv`.
- `reports/contagion_report.csv` - focused Contagion checklist/coverage report driven by `story_arc_checklists.csv`.
- `reports/legacy_report.csv` - focused Legacy checklist/coverage report driven by `story_arc_checklists.csv`.
- `reports/long_halloween_family_report.csv` - focused Haunted Knight, Long Halloween, Dark Victory, When in Rome, Long Halloween Special, and Last Halloween reading-order/coverage report driven by `story_arc_checklists.csv`.
- `reports/story_arc_long_halloween_family_checklist.csv` - curated story-arc checklist output for the Long Halloween family.
- `reports/focused_report_summary.csv` - counts for each configured focused report set.
- `reports/catwoman_focus.csv` - data-driven Catwoman collector dashboard from collection rows, event/story-arc checklists, copy coverage, and Hidden Gotham seeds.
- `reports/character_focus_summary.csv` - counts for each configured character/topic focus report.
- `reports/shop_lookup.csv` - merged comic-shop lookup table for owned, ordered, wanted, gap, story/event, and copy context.
- `reports/shop_lookup.html` - phone-friendly searchable shop lookup page generated from CSV data.
- `scripts/lookup.py` - command-line shop lookup, for example `python3 scripts/lookup.py "Batman 531"`.
- `scripts/mobile_lookup.py` - minimal prompt-only lookup wrapper for quick phone/terminal use; bare numbers such as `531` try the ordered series list in `data/reference/mobile_lookup_series.csv`.
- `reports/chatgpt_handoff.md` - compact handoff pack for asking ChatGPT to research metadata or sanity-check reading orders.
- `reports/facsimiles_shopping_priority.csv` - facsimiles to look for where no matching owned issue was found.
- `reports/facsimiles_existence_to_confirm.csv` - facsimile rows that need a source URL or listing check before treating the facsimile as definitely real/current.
- `reports/facsimiles_ordered_not_arrived.csv` - facsimiles already ordered but not yet owned/readable.
- `reports/facsimiles_needs_ownership_confirmation.csv` - matching issue exists in the collection, but the format must be confirmed manually.
- `reports/owned_facsimiles.csv` - facsimile copies that appear to be owned from current collection notes.

Run:

```bash
python3 scripts/import_collection.py
python3 scripts/audit_collection.py
python3 scripts/copy_report.py
python3 scripts/cleanup_report.py
python3 scripts/order_report.py
python3 scripts/facsimile_report.py
python3 scripts/event_report.py
python3 scripts/story_arc_report.py
python3 scripts/series_run_report.py
python3 scripts/character_focus_report.py
python3 scripts/shop_lookup.py
python3 scripts/publication_report.py
python3 scripts/hidden_gotham_report.py
python3 scripts/wanted_report.py
python3 scripts/collecting_reports.py
python3 scripts/promote_story_decisions.py --dry-run
```

## Event checklists

Event reading order lives in `data/reference/event_checklists.csv`. Collection ownership stays in the raw/master collection CSVs. This lets an event like Zero Hour include the owned core miniseries, Gotham tie-ins, and wider optional DC tie-ins without muddying the shelf inventory.

## Story arc checklists

Story arc reading order lives in `data/reference/story_arc_checklists.csv`. These reports are for Batman-family arcs such as Contagion and Legacy, where Andrew wants both the missing issues and the edition/copy type of owned issues.

Run:

```bash
python3 scripts/story_arc_report.py
```

## Series run gaps

Series run ranges live in `data/reference/series_run_ranges.csv`. The current configured ranges are:

- `Batman #404-574`
- `Detective Comics #568-741`
- `Warhammer Monthly #0-86`

The default report checks every issue in those ranges and labels it as owned, not owned, MIA, or absent from the sheet. `reports/series_run_missing_issues.csv` is the practical shopping/checking list.

Issue-level story labels live in `data/reference/issue_metadata.csv`. The series run reports join this metadata into the missing list so the output shows story arc, story title, part label, role, notes, and source URL where known.

Series run reports also overlay `data/reference/story_metadata_decisions.csv` when confirmed issue metadata is missing. Rows sourced from decisions are labelled with `metadata_status` and `metadata_source` so review-grade metadata stays distinct from confirmed reference metadata.

## Cleanup Workflow

Format decisions and story metadata review are data-driven. Manual decisions live in:

- `data/reference/format_decisions.csv`
- `data/reference/story_metadata_decisions.csv`

Run:

```bash
python3 scripts/audit_collection.py
python3 scripts/series_run_report.py
python3 scripts/cleanup_report.py
python3 scripts/promote_story_backfill.py --dry-run
python3 scripts/promote_story_decisions.py --dry-run
```

Use `reports/format_cleanup_priority.csv` to work through owned books whose physical copy type is still uncertain. Use `reports/story_metadata_work_queue.csv` and `reports/story_metadata_backfill_candidates.csv` to decide which issue metadata rows should be promoted into `data/reference/story_metadata_decisions.csv` or `data/reference/issue_metadata.csv`. The `promote_story_backfill.py` helper imports backfill candidates as review decisions without adding story facts to Python. The `promote_story_decisions.py` helper promotes only approved/confirmed decisions into `data/reference/issue_metadata.csv`.

External story research should go into `data/manual/story_metadata_research_inbox.csv` first. This is the paste target for rows researched by ChatGPT or another assistant. Validate it before importing:

```bash
python3 scripts/story_metadata_inbox.py
python3 scripts/story_metadata_inbox.py --dry-run --import-valid
python3 scripts/story_metadata_inbox.py --import-valid
```

The inbox script writes:

- `reports/story_metadata_inbox_valid.csv` - high-confidence rows that can be imported as review decisions.
- `reports/story_metadata_inbox_needs_review.csv` - blank/low/medium confidence rows, duplicate matches, and rows already represented in trusted metadata or decisions.
- `reports/story_metadata_inbox_conflicts.csv` - rows that disagree with existing trusted metadata, existing decisions, or another inbox row.
- `reports/story_metadata_inbox_summary.csv` - counts for the inbox validation run.

Arc-title authority corrections should go into `data/manual/story_metadata_authority_review.csv`. This stage distinguishes official arc/event titles from descriptive placeholders such as `Untitled: [description]`.

Run:

```bash
python3 scripts/story_metadata_authority_review.py
python3 scripts/story_metadata_authority_review.py --apply --dry-run
python3 scripts/story_metadata_authority_review.py --apply
```

The authority review script writes:

- `reports/story_metadata_authority_valid.csv` - rows safe to apply to review decisions.
- `reports/story_metadata_authority_needs_review.csv` - rows missing required sources or classification.
- `reports/story_metadata_authority_conflicts.csv` - duplicate/conflicting correction rows.
- `reports/story_metadata_authority_summary.csv` - counts for the authority review run.

## Publications and Collections

Publication/container data lives in:

- `data/reference/publications.csv`
- `data/reference/publication_contents.csv`
- `data/reference/copies.csv`

This model distinguishes:

- owning an original individual issue
- owning a facsimile
- owning a collected edition that contains the issue
- owning an original graphic novel or prestige publication first published in that format

Collected-edition coverage can make a story readable, but it does not count as owning the original individual issue.

Physical-copy ownership lives in `data/reference/copies.csv` where cover, printing, format, ownership status, and variant status can be tracked per copy. This is how the library distinguishes, for example, an owned Detective Comics #411 foil facsimile from an ordered Detective Comics #411 non-foil facsimile.

`Ordered` is also separate from owned. Ordered items are tracked in `data/reference/orders.csv` and can appear in the raw collection files as `Collection=Ordered`, but scripts do not count them as owned until they arrive and are changed to `Yes`.

When parcels arrive, run `python3 scripts/copy_report.py` and work through `reports/orders_to_check_in.csv`. Use `reports/orders_to_check_in_summary.csv` to see pending parcels by retailer/status/format, and `reports/orders_to_check_in_commands.csv` for ready-to-run dry-run/check-in commands. The check-in step marks the order arrived and adds or updates the owned physical copy row in `data/reference/copies.csv`.

Use `scripts/check_in_order.py` to do that safely:

```bash
python3 scripts/check_in_order.py --dry-run ORD-FAC-DC-411-NONFOIL
python3 scripts/check_in_order.py ORD-FAC-DC-411-NONFOIL
python3 scripts/check_in_order.py ORD-FAC-DC-031 ORD-FAC-DC-038
```

The script updates `data/reference/orders.csv`, adds or updates the matching row in `data/reference/copies.csv`, and regenerates the copy, order, facsimile, publication, and wanted reports.

Run:

```bash
python3 scripts/copy_report.py
python3 scripts/order_report.py
python3 scripts/publication_report.py
```

## Collection Areas And Manual Intake

Collection areas live in `data/reference/collection_areas.csv`. Manual intake files live in `data/manual/*_intake.csv` and are imported by `scripts/import_collection.py` alongside the raw spreadsheet exports.

Warhammer intake currently starts in:

```text
data/manual/warhammer_intake.csv
```

Run:

```bash
python3 scripts/import_collection.py
python3 scripts/shop_lookup.py
```

## Hidden Gotham

Hidden Gotham research seeds live in `data/reference/hidden_gotham.csv`. The script reads that file and checks it against the current collection without hardcoding the checklist in Python.

Run:

```bash
python3 scripts/hidden_gotham_report.py
```

## Wanted items

`scripts/wanted_report.py` combines the practical buying/watch queues into `reports/wanted_items.csv`. This is the input that retailer watchers should match against.

Run:

```bash
python3 scripts/series_run_report.py
python3 scripts/facsimile_report.py
python3 scripts/story_arc_report.py
python3 scripts/wanted_report.py
```

Run:

```bash
python3 scripts/series_run_report.py
python3 scripts/series_run_report.py --infer-ranges --title Catwoman --title "Shadow of the Bat"
```


## Forbidden Planet watcher

The next practical milestone is a retailer watcher for Forbidden Planet.

Run:

```bash
python3 -m pip install -r requirements.txt
python3 scripts/fp_watcher.py --dry-run
```

Live mode searches the fixed Batman/Absolute/Facsimile catalogue URLs and the first 40 rows from `reports/wanted_items.csv`:

```bash
python3 scripts/fp_watcher.py
python3 scripts/fp_watcher.py --max-wanted-searches 100
python3 scripts/fp_watcher.py --no-wanted-searches
```

Output:

```text
reports/fp_candidates.csv
reports/fp_wanted_matches.csv
```

Default collecting rule: **Cover A / standard cover / original art only. Variant covers are excluded.**
