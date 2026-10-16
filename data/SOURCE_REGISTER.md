# MTL-XF-037 — Source register

## S1 — Appliances Energy Prediction

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/374 |
| Exact download | https://archive.ics.uci.edu/static/public/374/appliances+energy+prediction.zip |
| Required inputs | energydata_complete.csv |
| Source population | 19,735 ten-minute observations |
| Decision owner | Commercial Energy Services Director |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5VC8G

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **11979507 bytes**; SHA-256 **2fccf354445d886e7917620b0195db1f3e3e34d5a067a93b844694a4c561255a**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| energydata_complete.csv | 11979363 | 2820bf712ad0275cb18b85a05250926100d8e65ebb9f4d2d016ca91ea152a25d |

Member names and byte hashes were inspected; CSV record counts were checked where present. Actual cohort transformations and business analysis remain team delivery work.

Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.

## Cohort and field support

All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

**Grain:** One source ten-minute building interval keyed by date; duplicates and irregular gaps must be investigated.

**Required mapping:** date, Appliances, lights, T1…T9, RH_1…RH_9, T_out, Press_mm_hg, RH_out, Windspeed, Visibility, Tdewpoint, rv1, rv2; verify actual weather headers.

**Interpretation limits:** This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5VC8G); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
