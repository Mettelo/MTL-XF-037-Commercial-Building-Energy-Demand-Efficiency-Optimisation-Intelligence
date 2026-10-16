# MTL-XF-037 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Energy Forecast Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Commercial Energy Services Director approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | Six 100 Wh intervals sum to 0.6 kWh; no extra ×1/6 conversion; twenty-minute gaps not treated as adjacent targets; timezone left source-local if unknown. |
| AC6 | D6 / SC2 | Only available past inputs used; rv1/rv2 excluded; identical eligible test targets across methods; publish absolute error and relative change against both baselines. |
| AC7 | D7 / SC3 | 10 kWh×10%×£0.30=£0.30 assumed avoided cost; all windows cite coverage and comfort-data gaps; no achieved savings claim. |
| AC8 | D8 / SC4 | Reviewer distinguishes Wh/kWh/kW, changes tariff without changing measured energy, and identifies a gap-limited window excluded from recommendation. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Explicitly declares single residential proxy; defines commercial transfer evidence, measured cost/comfort outcomes and consent/access needs before any site trial. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Interval energy and coverage ledger

**Accountable delivery role:** Energy and Facilities Analyst. **Business reviewer:** Commercial Energy Services Director. **Independent assurance:** Energy Forecast Assurance Analyst.

**Required artefact:** data/curated/interval-energy-and-coverage-ledger.csv and docs/05-kpi-catalogue/interval-energy-and-coverage-ledger.md.

**Content:** Unique timestamps, Appliances/lights Wh, appliance kWh, observed/expected ten-minute coverage and gap/duplicate flags; actual date bounds.

**Pass condition:** Six 100 Wh intervals sum to 0.6 kWh; no extra ×1/6 conversion; twenty-minute gaps not treated as adjacent targets; timezone left source-local if unknown.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Next-interval demand forecast comparison

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Commercial Energy Services Director. **Independent assurance:** Energy Forecast Assurance Analyst.

**Required artefact:** docs/06-analysis/next-interval-demand-forecast-comparison.md plus machine-readable evaluation_results.csv.

**Content:** Previous-interval and train-hour-of-week baselines versus candidate forecast, chronological holdout MAE/RMSE and peak-window errors.

**Pass condition:** Only available past inputs used; rv1/rv2 excluded; identical eligible test targets across methods; publish absolute error and relative change against both baselines.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Three scheduling hypotheses and scenario model

**Accountable delivery role:** Energy and Facilities Analyst. **Business reviewer:** Commercial Energy Services Director. **Independent assurance:** Energy Forecast Assurance Analyst.

**Required artefact:** docs/07-decision-framework/three-scheduling-hypotheses-and-scenario-model.csv plus policy.md.

**Content:** Three hour-of-week windows with observed energy, forecast evidence, assumed reduction and nine tariff/reduction outcomes; no operational control commands.

**Pass condition:** 10 kWh×10%×£0.30=£0.30 assumed avoided cost; all windows cite coverage and comfort-data gaps; no achieved savings claim.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Energy service pilot dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Commercial Energy Services Director. **Independent assurance:** Energy Forecast Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Daily/hourly energy, forecast performance, scheduling scenarios and proxy/coverage limitations.

**Pass condition:** Reviewer distinguishes Wh/kWh/kW, changes tariff without changing measured energy, and identifies a gap-limited window excluded from recommendation.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Commercial-site pilot specification

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Commercial Energy Services Director. **Independent assurance:** Energy Forecast Assurance Analyst.

**Required artefact:** deliverables/commercial-site-pilot-specification.pdf plus editable slides and supporting cards/runbook.

**Content:** Metering scope, occupancy and tariff data, comfort monitoring, comparison design, pilot window, owner and stop/review rule for all three hypotheses.

**Pass condition:** Explicitly declares single residential proxy; defines commercial transfer evidence, measured cost/comfort outcomes and consent/access needs before any site trial.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Energy conversion | Six observations of 100 Wh sum to 0.6 kWh and average demand is 0.6 kW. |
| DT2 | Gap handling | A twenty-minute gap cannot be treated as an adjacent ten-minute forecast target. |
| DT3 | Temporal isolation | Changing future test outcomes cannot alter training features, imputation or threshold choice. |
| DT4 | Random features | rv1 and rv2 are excluded from core predictors. |
| DT5 | Proxy disclosure | Every commercial recommendation identifies the single-house proxy limitation. |
| DT6 | Savings scenario | 10 kWh at 10% reduction and £0.30/kWh yields £0.30 assumed avoided cost, not achieved savings. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** The Commercial Energy Services Director reviews interval-energy quality, next-interval forecast errors and three scheduling hypotheses, then commissions a monitored commercial-site pilot with occupancy, tariff and comfort data. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Reviewer distinguishes Wh/kWh/kW, changes tariff without changing measured energy, and identifies a gap-limited window excluded from recommendation. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
