# MTL-XF-037 — Business context and practical use case

## Organisation and accountable decision

Confidential Facilities and Energy Services Provider is the simulated sponsor. The Commercial Energy Services Director owns the monthly energy-service pilot review and must decide: **Select three monitored scheduling hypotheses and a commercial-site validation plan.**

## The operational problem

The energy-services provider must decide whether its demand-analysis method is credible enough to take into a commercial customer pilot. High-consumption windows may identify scheduling hypotheses, but confusing interval energy with power or leaking same-interval measurements into a forecast would exaggerate usefulness. Because the source is one house, the commercial decision is whether and how to validate the method at a customer site, not whether a commercial saving has already been established.

## How the finished product will be used

The Commercial Energy Services Director reviews interval-energy quality, next-interval forecast errors and three scheduling hypotheses, then commissions a monitored commercial-site pilot with occupancy, tariff and comfort data.

**Current approach:** Propose scheduling changes from aggregate consumption with no consistent forecast baseline or transfer-validation plan.

**Required future approach:** Use correctly aggregated energy, chronological evaluation and explicitly assumed cost scenarios to plan a monitored pilot.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Commercial Energy Services Director | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Energy and Facilities Analyst | Verify Wh-to-kWh aggregation and write three monitored scheduling cards with baseline, comfort observation plan and commercial transfer constraints. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Energy Forecast Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Interval energy and coverage ledger** to support the stated decision, with this evidence: Unique timestamps, Appliances/lights Wh, appliance kWh, observed/expected ten-minute coverage and gap/duplicate flags; actual date bounds.
2. Can the sponsor use **Next-interval demand forecast comparison** to support the stated decision, with this evidence: Previous-interval and train-hour-of-week baselines versus candidate forecast, chronological holdout MAE/RMSE and peak-window errors.
3. Can the sponsor use **Three scheduling hypotheses and scenario model** to support the stated decision, with this evidence: Three hour-of-week windows with observed energy, forecast evidence, assumed reduction and nine tariff/reduction outcomes; no operational control commands.
4. Can the sponsor use **Energy service pilot dashboard** to support the stated decision, with this evidence: Daily/hourly energy, forecast performance, scheduling scenarios and proxy/coverage limitations.
5. Can the sponsor use **Commercial-site pilot specification** to support the stated decision, with this evidence: Metering scope, occupancy and tariff data, comfort monitoring, comparison design, pilot window, owner and stop/review rule for all three hypotheses.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Interval energy and coverage ledger | Unique timestamps, Appliances/lights Wh, appliance kWh, observed/expected ten-minute coverage and gap/duplicate flags; actual date bounds. |
| D6 | Next-interval demand forecast comparison | Previous-interval and train-hour-of-week baselines versus candidate forecast, chronological holdout MAE/RMSE and peak-window errors. |
| D7 | Three scheduling hypotheses and scenario model | Three hour-of-week windows with observed energy, forecast evidence, assumed reduction and nine tariff/reduction outcomes; no operational control commands. |
| D8 | Energy service pilot dashboard | Daily/hourly energy, forecast performance, scheduling scenarios and proxy/coverage limitations. |
| D11 | Commercial-site pilot specification | Metering scope, occupancy and tariff data, comfort monitoring, comparison design, pilot window, owner and stop/review rule for all three hypotheses. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Interval energy and coverage ledger | Six 100 Wh intervals sum to 0.6 kWh; no extra ×1/6 conversion; twenty-minute gaps not treated as adjacent targets; timezone left source-local if unknown. |
| SC2 | D6 — Next-interval demand forecast comparison | Only available past inputs used; rv1/rv2 excluded; identical eligible test targets across methods; publish absolute error and relative change against both baselines. |
| SC3 | D7 — Three scheduling hypotheses and scenario model | 10 kWh×10%×£0.30=£0.30 assumed avoided cost; all windows cite coverage and comfort-data gaps; no achieved savings claim. |
| SC4 | D8 — Energy service pilot dashboard | Reviewer distinguishes Wh/kWh/kW, changes tariff without changing measured energy, and identifies a gap-limited window excluded from recommendation. |
| SC5 | D11 — Commercial-site pilot specification | Explicitly declares single residential proxy; defines commercial transfer evidence, measured cost/comfort outcomes and consent/access needs before any site trial. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

**Failure to prevent:** Multiplying interval Wh by duration again or extrapolating one house into proven commercial savings would invalidate the decision case.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
