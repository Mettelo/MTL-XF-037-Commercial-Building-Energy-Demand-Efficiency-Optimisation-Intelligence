# MTL-XF-037 — Data acquisition and engineering

## Approved S1

[Appliances Energy Prediction](https://archive.ics.uci.edu/dataset/374); required files: **energydata_complete.csv**. Expected source population: 19,735 ten-minute observations.

Exact official download:

https://archive.ics.uci.edu/static/public/374/appliances+energy+prediction.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

**Grain:** One source ten-minute building interval keyed by date; duplicates and irregular gaps must be investigated.

**Required fields:** date, Appliances, lights, T1…T9, RH_1…RH_9, T_out, Press_mm_hg, RH_out, Windspeed, Visibility, Tdewpoint, rv1, rv2; verify actual weather headers.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Chronological first 60% train, next 20% validation, last 20% test by timestamp. Core forecast is next-interval Appliances using only information available through the preceding interval; lag all contemporaneous sensors/weather as needed. Drop boundary/gap targets with row accounting. Compare previous-interval and train-only hour-of-week median baselines.

## Interpretation and quality

This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
