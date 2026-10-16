# MTL-XF-037 — Governance

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Accountability and gates

Commercial Energy Services Director owns business scope, assumptions and action approval. Governance owns source/rights/freeze; Engineer owns transformations; Energy and Facilities Analyst owns interpretation; Energy Forecast Assurance Analyst independently reviews. The simulated Mettelo panel owns programme acceptance. Record actual team members separately from simulated stakeholder roles.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Commercial Energy Services Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Energy and Facilities Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Commercial Energy Services Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Energy Forecast Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Domain controls

This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

**Primary risk:** Multiplying interval Wh by duration again or extrapolating one house into proven commercial savings would invalidate the decision case.

Rank hour-of-week windows by observed appliance kWh and compare with a lagged-demand forecast. Model 5%, 10%, 15% reductions within nominated windows at assumed £0.20/£0.30/£0.40 per kWh, never as verified savings. Keep temperature/humidity diagnostic plots; propose comfort monitoring rather than fabricated compliance.

All capacity, threshold, financial and review/remediation targets are project assumptions unless explicitly attributed. Human deferrals/overrides record reason, evidence, owner and next review. No production action is authorised by this pack.

## Source and evaluation control

All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

Follow [S1 register](../data/SOURCE_REGISTER.md); preserve original bytes outside Git, immutable snapshot, manifest and reviewer access. Checksum mismatch stops processing until investigated. Never silently replace a variant/feed. No raw data uploaded by this update.

Chronological first 60% train, next 20% validation, last 20% test by timestamp. Core forecast is next-interval Appliances using only information available through the preceding interval; lag all contemporaneous sensors/weather as needed. Drop boundary/gap targets with row accounting. Compare previous-interval and train-only hour-of-week median baselines.

Lock target mapping, predictors, timing and policy configuration before test evaluation. Descriptive projects retain resample/sensitivity evidence. Record unsupported metrics and negative findings.

## Change and exception control

Record change ID, requester/date/reason, original/revised source/cohort/requirement, rights/field evidence, affected K/D/AC/DT, time/risk impact, owner, reviewer and decision. New inputs get new freeze IDs and affected checks rerun. Missing mandatory support blocks dependent work.

Each operational exception needs case, rationale, evidence, accountable owner, approval, compensating/manual control, expiry and next review; expired exceptions return to review.

Use only approved public data and fictional operational assumptions. Avoid unnecessary customer identifiers and unsupported protected-characteristic inference.

## Publication and release

Keep attribution, snapshot and limitations in every portfolio/dashboard/slide export. No secrets or private correspondence. Release after all AC/DT/UAT and rerun evidence passes with zero critical/high defects. Record final commit/tag and rollback to approved snapshot/configuration.

## Business acceptance and approval record

The specific use case is: The Commercial Energy Services Director reviews interval-energy quality, next-interval forecast errors and three scheduling hypotheses, then commissions a monitored commercial-site pilot with occupancy, tariff and comfort data.

SC1–SC5 in [acceptance](ACCEPTANCE_CRITERIA.md) govern the five concrete business outputs. G1 records criterion, version, actual team approver, simulated sponsor role, date and assumptions. G3 records measured baseline/alternative, decision and trade-off. G4 records executed pass evidence for each SC; a document's existence is insufficient. Never describe simulated sign-off or unmeasured benefits as real-client agreement or adoption.
