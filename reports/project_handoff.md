# Item Handoff

This repository is a CSV-first comics collection database. Python scripts should generate reports from reference CSV files; they should not contain Batman/comics facts, issue ranges, reading orders, or collecting policy directly in code.

## Core Principles

- The source of truth is structured CSV data plus generated reports.
- Ownership is not the same as readability.
- Owning a collected edition does not mean the original issue is owned.
- Facsimiles, original issues, collected editions, graphic novels, prestige books, annuals, specials, one-shots, and miniseries must remain distinguishable.
- A single physical publication should resolve to one canonical ownership result everywhere it appears.
- Public mirror files are for external research and discussion; private raw/source ownership files are intentionally excluded.

## Main Public Files To Read First

- `reports/chatgpt_handoff.md` - generated snapshot of current priorities and useful report pointers.
- `reports/item_index.csv` - item-level completion totals.
- `reports/item_scope_completion.csv` - completion totals by item scope.
- `reports/item_checklist_items.csv` - issue-level item checklist export.
- `reports/shopping_index.csv` - practical issue lookup with ownership/order/wantlist status.
- `reports/global_publication_reconciliation.csv` - canonical publication ownership/debugging table.
- `reports/cross_item_ownership_conflicts.csv` - ownership contradictions to resolve.
- `reports/unresolved_owned_batman_gotham_publications.csv` - owned source rows that still need canonical mapping.
- `data/reference/cover_images.csv` - cover manifest and local asset metadata.
- `reports/cover_gaps.csv` - all missing covers for visual viewers.
- `reports/cover_gaps_owned.csv` - missing covers for owned comics.
- `reports/cover_quality_flags.csv` - covers needing review.
- `reports/visual_collection_viewer.html` - visual viewer index.

## Important Reference Tables

- `data/reference/publications.csv` - publication model.
- `data/reference/publication_contents.csv` - collected edition contents.
- `data/reference/publication_aliases.csv` - title/alias reconciliation.
- `data/reference/items.csv` - item identities.
- `data/reference/item_scopes.csv` - item scope definitions.
- `data/reference/item_memberships.csv` - issue-level item membership.
- `data/reference/item_relationships.csv` - relationships between items.
- `data/reference/series_run_ranges.csv` - collecting ranges.
- `data/reference/story_arc_checklists.csv` - story arc issue membership.
- `data/reference/event_checklists.csv` - event issue membership.
- `data/reference/visual_view_presets.csv` - visual viewer run/page definitions.

## Research Rules For External Assistants

- Return CSV, not prose, when asked for data.
- Preserve existing `PublicationID` values from reports when provided.
- Cite source URLs for every bibliographic or cover claim.
- Use official issue pages or stable database pages where possible.
- Prefer original regular/Cover A artwork for visual reading-order pages.
- Do not use variant, foil, sketch, virgin, incentive, ratio, blank, signed, or exclusive covers unless explicitly requested.
- If uncertain, mark `confidence=review` and explain in `notes`.
- Do not invent story arc names. Use `Standalone` or `Untitled: [short neutral description]` where no official title exists.

## Local Validation Commands

Run these in the private repo root:

```bash
python3 scripts/validate_database.py
python3 scripts/regression_tests.py
python3 scripts/cover_quality_report.py
python3 scripts/cover_gap_report.py
python3 scripts/build_visual_viewer.py
python3 scripts/build_public_mirror.py
```

The public mirror is generated from `data/reference/public_mirror_files.csv`. Do not add private raw source files to that manifest.
