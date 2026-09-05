# AI-Native User Flow · Juno

## Entry point

**Signal type:** New message / transcript received

A new customer transcript containing a PO concern is uploaded to the Raw data column in Juno to be processed.

**What they see instantly**

"Juno is reading your transcript…" status pill appears under the input column. Empty Insights and PRD columns dim to ~40% to signal the agent is working.

## The flow

1. 1. RAG retrieval over the RocketShip Strategy, top-K = 8.
2. Comparison logic, does the transcript pain point map to a strategic pillar?
3. Risk + alignment scoring, output P0-P3 with a strategic-rationale citation.
4. Confidence check, score < 30 → notRecommended; score ≥ 70 → P0/P1.
2. "Scanning Strategy One-Pager…" → "Cross-referencing 1 transcript with strategic pillars…" → "Synthesising priorities + drafting PRD section…"
3. Path A (Strategy loaded) → grounded prioritization with citations.
Path B (Strategy missing) → "Cautious mode", generic priorities tagged "low confidence" + nudge to load the strategy doc.

## AI moments

**Placement:** Inline & Embedded

There should be insights generated in the second column with a P0 to P3 priority assigned.  Each has source listed and the strategic pillar from the strategy referenced.
There should be a draft PRD that appears in the last column.

Automation occurs with synthesizing the data and providing prioritization where it falls within established guardrails of the strategy guidelines.  When anything falls outside the human PM still reviews and approves.  Assistance to the human PM that they do not start from a blank slate.

## Fallbacks

**Kill switch**

Every insight card generated can be adjusted in terms of priority (down or upgraded) along with clarity of actual issue and alignment to strategic pillar.
The draft PRD can be overwitten / adjusted for clarity.  Some items could be manually removed due to priority overrides.

**Training signal**

Manual priority adjustments needs to be tracked.  More than 10% override in a day should trigger signal/statement to Juno to have strategy doc reviewed and refined.

**Fail-safe**

If any painpoint or support issue is raised that does not align to strategic pillars, it should be flagged to PM to assess and not attempted to assign a priority.

## Self-review

- [ ] Trigger fires on the earliest possible signal, no manual “Start AI” click.
- [ ] At least one breadcrumb message turns latency into transparency.
- [ ] Maneuver matches the M2 value prop (Automation / Augmentation / Insights / Personalization).
- [ ] Every automated decision has a working kill switch.
- [ ] Fail-safe path is explicit. No dead end with a bad AI result.
- [ ] Hidden logic references M3 PRD specs (Top-K, latency target, knowledge base).
