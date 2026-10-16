# MTL-XF-037 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Facilities and Energy Services Provider · **Sponsor:** Commercial Energy Services Director · **Team:** 6–8 · **Duration:** 8 weeks · **Cycle:** monthly energy-service pilot review

## Problem and commission

The energy-services provider must decide whether its demand-analysis method is credible enough to take into a commercial customer pilot. High-consumption windows may identify scheduling hypotheses, but confusing interval energy with power or leaking same-interval measurements into a forecast would exaggerate usefulness. Because the source is one house, the commercial decision is whether and how to validate the method at a customer site, not whether a commercial saving has already been established.

> Select three monitored scheduling hypotheses and a commercial-site validation plan.

## Practical use case and business outputs

The Commercial Energy Services Director reviews interval-energy quality, next-interval forecast errors and three scheduling hypotheses, then commissions a monitored commercial-site pilot with occupancy, tariff and comfort data.

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Interval energy and coverage ledger | Unique timestamps, Appliances/lights Wh, appliance kWh, observed/expected ten-minute coverage and gap/duplicate flags; actual date bounds. |
| D6 | Next-interval demand forecast comparison | Previous-interval and train-hour-of-week baselines versus candidate forecast, chronological holdout MAE/RMSE and peak-window errors. |
| D7 | Three scheduling hypotheses and scenario model | Three hour-of-week windows with observed energy, forecast evidence, assumed reduction and nine tariff/reduction outcomes; no operational control commands. |
| D8 | Energy service pilot dashboard | Daily/hourly energy, forecast performance, scheduling scenarios and proxy/coverage limitations. |
| D11 | Commercial-site pilot specification | Metering scope, occupancy and tariff data, comfort monitoring, comparison design, pilot window, owner and stop/review rule for all three hypotheses. |

## Required success contract

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Interval energy and coverage ledger | Six 100 Wh intervals sum to 0.6 kWh; no extra ×1/6 conversion; twenty-minute gaps not treated as adjacent targets; timezone left source-local if unknown. |
| SC2 | D6 — Next-interval demand forecast comparison | Only available past inputs used; rv1/rv2 excluded; identical eligible test targets across methods; publish absolute error and relative change against both baselines. |
| SC3 | D7 — Three scheduling hypotheses and scenario model | 10 kWh×10%×£0.30=£0.30 assumed avoided cost; all windows cite coverage and comfort-data gaps; no achieved savings claim. |
| SC4 | D8 — Energy service pilot dashboard | Reviewer distinguishes Wh/kWh/kW, changes tariff without changing measured energy, and identifies a gap-limited window excluded from recommendation. |
| SC5 | D11 — Commercial-site pilot specification | Explicitly declares single residential proxy; defines commercial transfer evidence, measured cost/comfort outcomes and consent/access needs before any site trial. |

[Detailed acceptance](ACCEPTANCE_CRITERIA.md) defines executed evidence; [deliverables](DELIVERABLES.md) defines exact artefacts and ownership. G1 records simulated sponsor approval, not invented real-client agreement.

## Core scope

All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

Required source: energydata_complete.csv. Model grain: One source ten-minute building interval keyed by date; duplicates and irregular gaps must be investigated.

This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Select three monitored scheduling hypotheses and a commercial-site validation plan. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Multiplying interval Wh by duration again or extrapolating one house into proven commercial savings would invalidate the decision case. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One source ten-minute building interval keyed by date; duplicates and irregular gaps must be investigated. |
| Energy and Facilities Analyst | Verify Wh-to-kWh aggregation and write three monitored scheduling cards with baseline, comfort observation plan and commercial transfer constraints. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Chronological first 60% train, next 20% validation, last 20% test by timestamp. Core forecast is next-interval Appliances using only information available through the preceding interval; lag all contemporaneous sensors/weather as needed. Drop boundary/gap targets with row accounting. Compare previous-interval and train-only hour-of-week median baselines. |
| BI / Decision Product Developer | Four views for the monthly energy-service pilot review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Energy Forecast Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Chronological first 60% train, next 20% validation, last 20% test by timestamp. Core forecast is next-interval Appliances using only information available through the preceding interval; lag all contemporaneous sensors/weather as needed. Drop boundary/gap targets with row accounting. Compare previous-interval and train-only hour-of-week median baselines.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Rank hour-of-week windows by observed appliance kWh and compare with a lagged-demand forecast. Model 5%, 10%, 15% reductions within nominated windows at assumed £0.20/£0.30/£0.40 per kWh, never as verified savings. Keep temperature/humidity diagnostic plots; propose comfort monitoring rather than fabricated compliance.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Commercial Energy Services Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Energy and Facilities Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Commercial Energy Services Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Energy Forecast Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).
