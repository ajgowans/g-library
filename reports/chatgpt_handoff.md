# Library handoff

Use this pack to help research metadata and sanity-check reading orders. Treat repo CSVs as the source of truth for ownership.

## Ground Rules

- Do not assume contained-in-collection equals owned original issue.
- Keep Batman/comics facts in CSV reference data, not Python.
- Mark researched metadata with source URLs and confidence.
- Ownership, ordered, MIA, and variant facts must come from the repo data.

## Authoritative Files

- Issue ownership lookup: `reports/shopping_index.csv`.
- Item membership and item reading order: `reports/item_checklist_items.csv`.
- Item completion totals: `reports/item_index.csv` and `reports/item_scope_completion.csv`.
- Dark Knight Returns Saga reading order: `reports/dark_knight_returns_saga_reading_order.csv`.
- Dark Knight Returns Saga completion: `reports/dark_knight_returns_saga_summary.csv` and `reports/dark_knight_returns_saga_missing.csv`.
- Source publication exceptions: `reports/source_publication_exceptions.csv`.
- Annual publication universe: `reports/annuals_master.csv`; strict 1986-1999 annual audit: `reports/annuals_audit.csv`.
- Chronological late Modern local story map: `reports/modern_local_late_era_story_map.csv`.
- Human handoff summary: `reports/chatgpt_handoff.md`.

## Useful Commands

```bash
python3 scripts/series_run_report.py
python3 scripts/collecting_reports.py
python3 scripts/cleanup_report.py
python3 scripts/validate_database.py
```

## Current Report Counts

|status|count|
|---|---|
|absent_from_sheet|780|
|not_owned|47|
|readable_via_collection|2|

## Focused Report Summary

|focus_id|row_count|owned_rows|missing_rows|still_want_original_rows|
|---|---|---|---|---|
|knightfall_to_knightsend|114|114|0|0|
|zero_hour|36|10|26|26|
|bloodlines|25|10|15|15|
|contagion|20|12|8|8|
|legacy|18|6|12|12|
|long_halloween_family|48|17|31|31|

## First Missing Range Items

|series|issue_number|run_status|metadata_arc|still_want_original|wanted_reason|
|---|---|---|---|---|---|
|Azrael|0|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|3|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|4|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|5|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|8|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|9|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|10|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|11|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|12|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|13|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|14|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|15|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|18|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|19|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|20|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|21|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|22|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|23|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|24|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|25|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|26|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|27|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|28|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|29|absent_from_sheet||Yes|absent_from_sheet|
|Azrael|30|absent_from_sheet||Yes|absent_from_sheet|

## First Metadata Gaps For Research

|title|issue_number|run_status|collection_status|story|comic|
|---|---|---|---|---|---|
|Batman|408|absent_from_sheet||||
|Batman|409|absent_from_sheet||||
|Batman|410|owned|Yes|TBC|Batman #410|
|Batman|411|owned|Yes|TBC|Batman #411|
|Batman|412|absent_from_sheet||||
|Batman|413|absent_from_sheet||||
|Batman|414|owned|Yes|TBC|Batman #414|
|Batman|415|absent_from_sheet||||
|Batman|416|owned|Yes|TBC|Batman #416|
|Batman|417|absent_from_sheet||||
|Batman|418|absent_from_sheet||||
|Batman|419|owned|Yes|TBC|Batman #419|
|Batman|420|owned|Yes|TBC|Batman #420|
|Batman|421|owned|Yes|TBC|Batman #421|
|Batman|422|absent_from_sheet||||
|Batman|423|absent_from_sheet||||
|Batman|424|absent_from_sheet||||
|Batman|425|absent_from_sheet||||
|Batman|431|absent_from_sheet||||
|Batman|444|absent_from_sheet||||
|Batman|445|absent_from_sheet||||
|Batman|446|owned|Yes|TBC|Batman #446|
|Batman|447|owned|Yes|TBC|Batman #447|
|Batman|450|absent_from_sheet||||
|Batman|451|absent_from_sheet||||

## First Format Decisions For Review

|cleanup_priority|comic|series|issue_number|current_format|decision_status|
|---|---|---|---|---|---|
|High|Batman #410|Batman|410|Original/Reprint Unknown|needs_decision|
|High|Batman #411|Batman|411|Original/Reprint Unknown|needs_decision|
|High|Batman #414|Batman|414|Original/Reprint Unknown|needs_decision|
|High|Batman #416|Batman|416|Original/Reprint Unknown|needs_decision|
|High|Batman #419|Batman|419|Original/Reprint Unknown|needs_decision|
|High|Batman #420|Batman|420|Original/Reprint Unknown|needs_decision|
|High|Batman #421|Batman|421|Original/Reprint Unknown|needs_decision|
|High|Batman #428|Batman|428|Original/Reprint Unknown|needs_decision|
|High|Batman #429|Batman|429|Original/Reprint Unknown|needs_decision|
|High|Batman #430|Batman|430|Original/Reprint Unknown|needs_decision|
|High|Batman #432|Batman|432|Original/Reprint Unknown|needs_decision|
|High|Batman #433|Batman|433|Original/Reprint Unknown|needs_decision|
|High|Batman #434|Batman|434|Original/Reprint Unknown|needs_decision|
|High|Batman #435|Batman|435|Original/Reprint Unknown|needs_decision|
|High|Batman #436|Batman|436|Original/Reprint Unknown|needs_decision|
|High|Batman #437|Batman|437|Original/Reprint Unknown|needs_decision|
|High|Batman #438|Batman|438|Original/Reprint Unknown|needs_decision|
|High|Batman #439|Batman|439|Original/Reprint Unknown|needs_decision|
|High|Batman #441|Batman|441|Original/Reprint Unknown|needs_decision|
|High|Batman #443|Batman|443|Original/Reprint Unknown|needs_decision|
|High|Batman #446|Batman|446|Original/Reprint Unknown|needs_decision|
|High|Batman #447|Batman|447|Original/Reprint Unknown|needs_decision|
|High|Batman #448|Batman|448|Original/Reprint Unknown|needs_decision|
|High|Batman #449|Batman|449|Original/Reprint Unknown|needs_decision|
|High|Batman #452|Batman|452|Original/Reprint Unknown|needs_decision|

## First Story Metadata Queue Rows

|cleanup_priority|series|issue_number|comic|suggestion_source|decision_status|
|---|---|---|---|---|---|
|High|Batman|410|Batman #410|needs_research|needs_decision|
|High|Batman|411|Batman #411|needs_research|needs_decision|
|High|Batman|414|Batman #414|needs_research|needs_decision|
|High|Batman|416|Batman #416|needs_research|needs_decision|
|High|Batman|419|Batman #419|needs_research|needs_decision|
|High|Batman|420|Batman #420|needs_research|needs_decision|
|High|Batman|421|Batman #421|needs_research|needs_decision|
|High|Batman|446|Batman #446|needs_research|needs_decision|
|High|Batman|447|Batman #447|needs_research|needs_decision|
|High|Batman|458|Batman #458|needs_research|needs_decision|
|High|Batman|459|Batman #459|needs_research|needs_decision|
|High|Batman|460|Batman #460|needs_research|needs_decision|
|High|Batman|461|Batman #461|needs_research|needs_decision|
|High|Batman|462|Batman #462|needs_research|needs_decision|
|High|Batman|464|Batman #464|needs_research|needs_decision|
|High|Batman|466|Batman #466|needs_research|needs_decision|
|High|Batman|467|Batman #467|needs_research|needs_decision|
|High|Batman|468|Batman #468|needs_research|needs_decision|
|High|Batman|469|Batman #469|needs_research|needs_decision|
|High|Batman|470|Batman #470|needs_research|needs_decision|
|High|Batman|471|Batman #471|needs_research|needs_decision|
|High|Batman|472|Batman #472|needs_research|needs_decision|
|High|Batman|473|Batman #473|needs_research|needs_decision|
|High|Batman|474|Batman #474|needs_research|needs_decision|
|High|Batman|476|Batman #476|needs_research|needs_decision|

