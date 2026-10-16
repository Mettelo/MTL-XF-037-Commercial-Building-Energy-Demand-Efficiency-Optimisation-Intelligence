# MTL-XF-037 — Business context

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Organisation and problem

Confidential Facilities and Energy Services Provider is the fictional organisation. A commercial energy-services provider needs to demonstrate a reliable demand-analysis method before seeking a customer-site pilot. The available data come from a single low-energy house, so commercial savings, occupancy effects and contractual comfort compliance require further evidence.

The Commercial Energy Services Director needs a monthly energy-service pilot review supporting **Select three monitored scheduling hypotheses and a commercial-site validation plan.**

## Stakeholders

| Stakeholder | Decision | Required evidence |
| --- | --- | --- |
| Commercial Energy Services Director | Approve scope, policy assumptions and next investigation/pilot. | D7 policy comparison, D11 recommendations, workload/risk and limitations. |
| Energy and Facilities Analyst | Interpret observations and own action proposals. | K1–K7, source-supported dimensions, sensitivity and case lineage. |
| Data Governance Analyst | Approve source, freeze and interpretation rights. | S1 manifest, licence, actual schema and source-to-output support. |
| Operations / service owner | Accept workload and review/escalation responsibilities. | Action register, eligibility, owners, review dates and override reasons. |
| Energy Forecast Assurance Analyst | Challenge correctness and release readiness. | DT1–DT10, UAT, reconciliations and clean rerun. |

## Workflow to improve

Current simulated process: separate extracts/headline totals → informal prioritisation → manual review with limited lineage. This is a teaching scenario, not an observed real client process.

Proposed process: acquire approved bytes → validate/freeze → curate at declared grain → calculate K1–K7 → compare policies → inspect uncertainty/exclusions → sponsor approves investigation/pilot → record disposition and review date. No score bypasses human approval.

## Questions to answer

1. What is the baseline appliance energy, and what defines its denominator?
2. Which supported groups/cases account for lighting energy, and with what sample support?
3. Which cases change between the baseline and alternative, and why?
4. How do the specified transformation, threshold, cost or capacity alternatives alter the decision?
5. Which recommendations remain unsupported and what evidence must be collected next?

## Decision and action evidence

Rank hour-of-week windows by observed appliance kWh and compare with a lagged-demand forecast. Model 5%, 10%, 15% reductions within nominated windows at assumed £0.20/£0.30/£0.40 per kWh, never as verified savings. Keep temperature/humidity diagnostic plots; propose comfort monitoring rather than fabricated compliance.

Every action record contains case/group key, snapshot, observed measure, eligibility, baseline and alternative rank/policy, evidence link, uncertainty, proposed next step, accountable owner, due/review date, disposition and override rationale. Use source-row IDs; do not invent real customer identities.

## Value and limits

Delivery success is evidence-backed acceptance of D1–D12, not guaranteed model superiority. Benefits remain hypotheses until an approved pilot specifies population, comparator, outcome window and guardrails. D11 includes three next actions and a case where the evidence does not justify action.

This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

**Risk to prevent:** Multiplying interval Wh by duration again or extrapolating one house into proven commercial savings would invalidate the decision case.

**Source boundary:** All 19,735 original timestamps in energydata_complete.csv, approximately 4.5 months. Preserve source-local timestamps without inventing a timezone. Confirm actual minimum/maximum dates and sampling gaps at acquisition.

Missing mandatory support blocks G1 or a dependent output until a governed scope/source decision is recorded.
