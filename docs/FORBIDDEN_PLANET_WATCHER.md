# Forbidden Planet Watcher

Goal: find buyable comics on Forbidden Planet that match the collection strategy, especially:

- Batman-related Facsimile Editions
- Absolute Batman
- Absolute Catwoman
- Batman-related Absolute one-shots, annuals, specials and crossovers

## Cover rules

Default rule: **standard Cover A only**.

The watcher should exclude listings containing variant terms unless explicitly allowed:

- Variant
- Foil Variant
- Card Stock Variant
- Blank Variant
- Incentive Variant
- Ratio Variant
- Exclusive Variant
- Cover B, Cover C, Cover D, etc.

For facsimiles, prefer listings with:

- `Facsimile Edition`
- `Cover A`
- original cover artist / original art where visible

For Absolute Batman, prefer:

- `Absolute Batman #N (Cover A Nick Dragotta)`
- Standard later printings only if first printing Cover A is unavailable and you deliberately choose a reading copy

## Matching logic

A product is a candidate if:

1. It is in a wanted category.
2. It does not appear to be already owned.
3. It passes the Cover A / no-variant filter.
4. It is not marked as ignored in `collecting_strategy.csv`.

The script outputs review files. It should not auto-buy anything.

## Suggested manual workflow

1. Run `python scripts/fp_watcher.py`.
2. Open `reports/fp_candidates.csv`.
3. Check the product pages manually.
4. Buy only the standard Cover A/original art versions.
5. Update ownership fields in the collection CSV after purchase.
