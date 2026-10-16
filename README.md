# MTL-XF-037 — Commercial Building Energy Demand Efficiency Optimisation Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 3–5 · **Duration:** 8 weeks

## The business problem

The energy-services provider must decide whether its demand-analysis method is credible enough to take into a commercial customer pilot. High-consumption windows may identify scheduling hypotheses, but confusing interval energy with power or leaking same-interval measurements into a forecast would exaggerate usefulness. Because the source is one house, the commercial decision is whether and how to validate the method at a customer site, not whether a commercial saving has already been established.

**Simulated organisation:** Confidential Facilities and Energy Services Provider. **Accountable decision owner:** Commercial Energy Services Director.

## Practical use case

The Commercial Energy Services Director reviews interval-energy quality, next-interval forecast errors and three scheduling hypotheses, then commissions a monitored commercial-site pilot with occupancy, tariff and comfort data.

**Decision the project must enable:** Select three monitored scheduling hypotheses and a commercial-site validation plan.

**Current approach:** Propose scheduling changes from aggregate consumption with no consistent forecast baseline or transfer-validation plan.

**Required future approach:** Use correctly aggregated energy, chronological evaluation and explicitly assumed cost scenarios to plan a monitored pilot.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Interval energy and coverage ledger | Unique timestamps, Appliances/lights Wh, appliance kWh, observed/expected ten-minute coverage and gap/duplicate flags; actual date bounds. |
| D6 | Next-interval demand forecast comparison | Previous-interval and train-hour-of-week baselines versus candidate forecast, chronological holdout MAE/RMSE and peak-window errors. |
| D7 | Three scheduling hypotheses and scenario model | Three hour-of-week windows with observed energy, forecast evidence, assumed reduction and nine tariff/reduction outcomes; no operational control commands. |
| D8 | Energy service pilot dashboard | Daily/hourly energy, forecast performance, scheduling scenarios and proxy/coverage limitations. |
| D11 | Commercial-site pilot specification | Metering scope, occupancy and tariff data, comfort monitoring, comparison design, pilot window, owner and stop/review rule for all three hypotheses. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Interval energy and coverage ledger | Six 100 Wh intervals sum to 0.6 kWh; no extra ×1/6 conversion; twenty-minute gaps not treated as adjacent targets; timezone left source-local if unknown. |
| SC2 | D6 — Next-interval demand forecast comparison | Only available past inputs used; rv1/rv2 excluded; identical eligible test targets across methods; publish absolute error and relative change against both baselines. |
| SC3 | D7 — Three scheduling hypotheses and scenario model | 10 kWh×10%×£0.30=£0.30 assumed avoided cost; all windows cite coverage and comfort-data gaps; no achieved savings claim. |
| SC4 | D8 — Energy service pilot dashboard | Reviewer distinguishes Wh/kWh/kW, changes tariff without changing measured energy, and identifies a gap-limited window excluded from recommendation. |
| SC5 | D11 — Commercial-site pilot specification | Explicitly declares single residential proxy; defines commercial transfer evidence, measured cost/comfort outcomes and consent/access needs before any site trial. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [Appliances Energy Prediction](https://archive.ics.uci.edu/dataset/374). **Required input:** energydata_complete.csv. **Expected source population:** 19,735 ten-minute observations.

All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

**Download:** https://archive.ics.uci.edu/static/public/374/appliances+energy+prediction.zip

This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Chronological first 60% train, next 20% validation, last 20% test by timestamp. Core forecast is next-interval Appliances using only information available through the preceding interval; lag all contemporaneous sensors/weather as needed. Drop boundary/gap targets with row accounting. Compare previous-interval and train-only hour-of-week median baselines.

Rank hour-of-week windows by observed appliance kWh and compare with a lagged-demand forecast. Model 5%, 10%, 15% reductions within nominated windows at assumed £0.20/£0.30/£0.40 per kWh, never as verified savings. Keep temperature/humidity diagnostic plots; propose comfort monitoring rather than fabricated compliance.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Energy and Facilities Analyst: Verify Wh-to-kWh aggregation and write three monitored scheduling cards with baseline, comfort observation plan and commercial transfer constraints.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Energy Forecast Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Commercial Energy Services Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Energy and Facilities Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Commercial Energy Services Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Energy Forecast Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
