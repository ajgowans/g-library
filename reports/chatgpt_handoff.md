# Gotham Library ChatGPT Handoff

Use this pack to help research metadata and sanity-check reading orders. Treat repo CSVs as the source of truth for ownership.

## Ground Rules

- Do not assume contained-in-collection equals owned original issue.
- Keep Batman/comics facts in CSV reference data, not Python.
- Mark researched metadata with source URLs and confidence.
- Ownership, ordered, MIA, and variant facts must come from Andrew or the repo data.

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
|absent_from_sheet|139|
|not_owned|11|
|readable_via_collection|2|

## Focused Report Summary

|focus_id|row_count|owned_rows|missing_rows|still_want_original_rows|
|---|---|---|---|---|
|knightfall_to_knightsend|66|66|0|0|
|zero_hour|36|10|26|26|
|bloodlines|25|10|15|15|
|contagion|20|12|8|8|
|legacy|18|6|12|12|
|long_halloween_family|48|17|31|31|

## First Missing Range Items

|series|issue_number|run_status|metadata_arc|still_want_original|wanted_reason|
|---|---|---|---|---|---|
|Batman|408|absent_from_sheet||Yes|absent_from_sheet|
|Batman|409|absent_from_sheet||Yes|absent_from_sheet|
|Batman|412|absent_from_sheet||Yes|absent_from_sheet|
|Batman|413|absent_from_sheet||Yes|absent_from_sheet|
|Batman|415|absent_from_sheet||Yes|absent_from_sheet|
|Batman|417|absent_from_sheet||Yes|absent_from_sheet|
|Batman|418|absent_from_sheet||Yes|absent_from_sheet|
|Batman|422|absent_from_sheet||Yes|absent_from_sheet|
|Batman|423|absent_from_sheet||Yes|absent_from_sheet|
|Batman|424|absent_from_sheet||Yes|absent_from_sheet|
|Batman|425|absent_from_sheet||Yes|absent_from_sheet|
|Batman|426|not_owned|A Death in the Family|Yes|not_owned|
|Batman|427|not_owned|A Death in the Family|Yes|not_owned|
|Batman|431|absent_from_sheet||Yes|absent_from_sheet|
|Batman|440|not_owned|A Lonely Place of Dying|Yes|Readable via collected edition, but no owned individual issue is recorded.|
|Batman|442|not_owned|A Lonely Place of Dying|Yes|Readable via collected edition, but no owned individual issue is recorded.|
|Batman|444|absent_from_sheet||Yes|absent_from_sheet|
|Batman|445|absent_from_sheet||Yes|absent_from_sheet|
|Batman|450|absent_from_sheet||Yes|absent_from_sheet|
|Batman|451|absent_from_sheet||Yes|absent_from_sheet|
|Batman|453|absent_from_sheet||Yes|absent_from_sheet|
|Batman|454|absent_from_sheet||Yes|absent_from_sheet|
|Batman|463|absent_from_sheet||Yes|absent_from_sheet|
|Batman|465|absent_from_sheet||Yes|absent_from_sheet|
|Batman|475|absent_from_sheet||Yes|absent_from_sheet|

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

## First Format Decisions For Andrew

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

