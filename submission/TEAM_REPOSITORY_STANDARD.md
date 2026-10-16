# MTL-XF-037 — Team repository standard

Create **MTL-XF-037-<team-name>** under **Mettelo** and add individual member accounts. Record [master URL](https://github.com/Mettelo/MTL-XF-037-Commercial-Building-Energy-Demand-Efficiency-Optimisation-Intelligence), reviewed master specification commit and final team commit/tag.

## Required areas

- README.md and CONTRIBUTIONS.md
- data/SOURCE_REGISTER.md; data/raw/README.md; data/reference/; data/metadata/; data/curated/
- docs/01-discovery/; docs/02-data-governance/; docs/03-data-model/; docs/04-data-quality/
- docs/05-kpi-catalogue/; docs/06-analysis/; docs/07-decision-framework/
- docs/08-assurance-uat/; docs/09-technical-handover/
- src/; tests/; dashboard/; deliverables/; submission/FINAL_SUBMISSION.md

Use sql/notebooks/analysis folders where useful; explain unused areas and avoid duplicate implementations. Pin free toolchain/dependencies and one documented run entry point. Keep raw payloads in approved storage outside Git, with verified manifest and reviewer access; never embed credentials.

## README and contribution evidence

State Select three monitored scheduling hypotheses and a commercial-site validation plan. Name Commercial Energy Services Director as simulated sponsor. Include cohort, acquisition/restore, environment/run instructions, five findings, baseline/alternative, assumptions, UAT/rerun and evidence links. Preserve the simulated-client declaration and this limit: This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

Assign named people to all seven [brief roles](../project/PROJECT_BRIEF.md). Every member links authored artefacts, at least one substantive review, and demo/handover contribution. Issues, commits, PRs and review records support evidence; commit count or one person's bulk upload is insufficient.

## Project-specific handover

Verify Wh-to-kWh aggregation and write three monitored scheduling cards with baseline, comfort observation plan and commercial transfer constraints.

Maintain D1–D12/AC1–AC12/DT1–DT10 evidence index with owner, distinct reviewer, state and final-commit path. Connect numeric claims to frozen source and code/configuration. Record all manual adjustments, excluded cases and limitations; preserve an insufficient-evidence case.
