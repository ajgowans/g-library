# Story Architecture Audit

## Already Exists

- `story_arc_checklists.csv` stores curated story/crossover checklist rows.
- `event_checklists.csv` stores event rows.
- `issue_metadata.csv` and `story_metadata_decisions.csv` identify story/arc membership for many issues.
- `focused_report_sets.csv` and existing focused reports expose Knightfall, Zero Hour, Bloodlines, Contagion, Legacy, and Long Halloween views.
- `publications.csv` and `publication_contents.csv` model collected editions separately from original issue ownership.
- `shopping_index.csv` is now the authoritative ownership/recommendation row source.

## Reused

- Existing event/story checklist rows are imported into `reports/item_checklists.csv`.
- Existing issue metadata creates Level A story-identification memberships.
- Existing Knightfall imported reading-order rows create an imported Knightfall block without claiming verified phase boundaries.

## Needs Normalising

- Several existing checklist sequences are grouped order labels, not verified reading orders.
- Knightquest currently needs a verified Crusade/Search split.
- No Man's Land data exists as issue metadata but needs complete Level B/C checklists.
- Crisis and DC One Million are item placeholders until verified scope data is added.

## Added

- `items.csv`, `item_relationships.csv`, and `item_scopes.csv` define the scalable item hierarchy.
- `reports/item_index.csv` summarizes completion and confidence.
- `reports/item_checklists.csv` joins item rows to shopping ownership data.
- `reports/story_coverage_gaps.csv` generates a research backlog.

## Counts

- Level A: 26
- Level B: 82
- Level C: 1
- Item checklist rows generated: 2228
