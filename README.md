# Juno PM — AI Copilot for RocketShip’s Product Org

> An AI Associate PM that turns Slack/Notion/Jira/Support ticket chaos into a prioritised top-3 risk list and roadmap each day.

_Angela Olson · AI PM Cohort · Aug/Sept 2026_

Repo: https://github.com/angela-m-olson-13/juno-pm

This repo is my final project for the AI Product Management Certification — **Juno PM**. Each module’s artefact lives in its own folder; this README is the dashboard and the pitch.

---

## Module artefacts

### M1 · Prompting
- **System prompt** — [`01-prompting/system-prompt.md`](01-prompting/system-prompt.md)
- **Prototype** — https://lovable.dev/projects/6aa7a44f-2b9a-4b3c-8fe2-ca1ab6465193?magic_link=mc_45a2640f-7cfc-4c13-830b-db4286401f67

### M2 · Strategy
- **Decision matrix** — [`02-strategy/decision-matrix.md`](02-strategy/decision-matrix.md)
- **AI Strategy one-pager** — [`02-strategy/strategy-one-pager.md`](02-strategy/strategy-one-pager.md)

### M3 · RAG / AI PRD
- **AI PRD** — [`03-rag-prd/prd.md`](03-rag-prd/prd.md)

### M4 · AI-Native UX
- **AI user flow** — [`04-ai-ux/user-flow.md`](04-ai-ux/user-flow.md)
- **Trust-gap mitigations** — [`04-ai-ux/trust-gaps.md`](04-ai-ux/trust-gaps.md)

### M5 · Agentic Workflows
- **Agent Workflow Spec (AWSpec)** — [`05-agentic-workflows/awspec.md`](05-agentic-workflows/awspec.md)
- **Agent Control Panel** — [`05-agentic-workflows/agent-control-panel.md`](05-agentic-workflows/agent-control-panel.md)

### M6 · Evals &amp; Guardrails
- **Eval stack** — [`06-evals/eval-stack.md`](06-evals/eval-stack.md)
- **Human evaluation rubric** — [`06-evals/human-rubric.md`](06-evals/human-rubric.md)

---

## PM Execution Plan

### Where Juno is today
- Modules M1 - M6 subject areas are spec'd and committed for Juno.
- The prototype illustrates the M1 prompt and improvement areas.
- Automated evals: 200-item golden set drafted, judge prompt validated against 30 items; not yet wired to CI.
- Human rubric drafted and testers identified.  No actual calibration or measurement has taken place.

### What ships next (next 2 sprints)
-Sprint 1:  Instantiate agents established in M5 through first set of test data in beta mode for initial assessment.
-Sprint 2: Run first patch of data of 40 PO items for evaluation and testing of outcomes with actual graders.

### What I watch (dashboards)
- Daily: thumbs-down rate, regen rate, hand-off rate.
- Weekly: human-rubric mean per dimension; refusal hit-rate; cost per run.
- Per release: golden-set accuracy; format/citation/refusal pass rate.

### Red lines (what blocks shipping)
- Any critical-safety fail (any "1" on safety dimension in human eval).
- <90% golden-set accuracy on automated layer.
- Customer-name fabrication in last 30 days.
- Cost >$0.50 per run.
- P99 latency >5s on PO assessment.
- Any PII or legal / contract citation.
- Any items with confidence interval less than 75% that was not flagged for human PM review.

### Governance
- Compliance: PII scrubber pre-LLM
- Safety: prompt-injection eval row in golden set; refusal on legal/contract content.
- Reliability: 99.5% SLO; cached top-3 fallback if model is down.
- Reputation: 2-hour incident-response playbook in /docs.

---

## Build Insights

- **Friction point.** Interpretation of data from sources - needs clear definition from the strategy to really have prioritizations make sense and be aligned to actual PM logic
- **Key learning.** Evaluation rubics are critical but easy to forget about.  This ensures model is reasonable up front and remains so.  Also forces multi viewpoints in non-emotional scoring to avoid bias as much as possible.
- **Aha moment.** A lot of this material was very new to me, so a lot of 'aha' moments!  I think all the aspects of building in AI was intriguing - much more to consider thoughtfully that does not have to slow down progress or build but helps ensure a meaningful, trustful, and value-driven outcome.

---

_Certification submission — AI Product Management Certification._
