# MTL-XF-037 — References and mappings

Retain source documentation, licence/citation notices and required codebooks for Appliances Energy Prediction. Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.

Version each reference with ID, official URL, retrieval date/version, content checksum, rights, raw→display mapping, rationale, owner and reviewer. Unknown categories remain visible; validate mapping completeness/uniqueness and all many-to-many joins.

**Interpretation rule:** This is a residential proxy, not a commercial-building portfolio. Appliances and lights are Wh per interval; no measured occupancy, tariff, floor area or commercial comfort standard exists. Exclude random rv1/rv2. Same-interval sensor explanations are not advance forecasts.

**Project policy assumptions:** Rank hour-of-week windows by observed appliance kWh and compare with a lagged-demand forecast. Model 5%, 10%, 15% reductions within nominated windows at assumed £0.20/£0.30/£0.40 per kWh, never as verified savings. Keep temperature/humidity diagnostic plots; propose comfort monitoring rather than fabricated compliance.

Keep choices separate from publisher facts. Register categorical/segment/class labels, unit conversions and any financial or capacity assumptions. Do not invent operational history absent from S1.

A reference explains the source; it cannot supply an unmeasured outcome. Register supplements and scope changes in [SOURCE_REGISTER.md](../SOURCE_REGISTER.md) before dependent work.
