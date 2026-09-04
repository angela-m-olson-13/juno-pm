# AI Strategy One-Pager - Juno Automated Prioritization

## 1. Problem & Workflow

The problem that currently exists is that there is lack of clarity on the right prioritization of work.  Priorities constantly shift as there are increasing PO and P1 tickets that stakeholders are trying to get roadmap work done within all while roadmap items are not pursued in proper prioritzed fashion.
Juno will prevent the constant changing priorities that happen which create inefficiences and ensure fact-based conversations on priorities versus based on end user feelings and opinions.

## 2. Target Metrics

Roadmap prioritization is 2 hours per week currently and should reduce to less than 30 minutes per week by the end of the first month (30 days).
Tickets with PO and P1 are addressed 10% faster than current baseline.

## 3. Autonomy Level

Autonomy level would be Co-pilot to get the assistance needed to the human PM to synthesize data from a variety of sources.  Some aspects can be automated with guardrails provided and other items force human sign-off and action.
Agent only would not be good to choose as there needs to be human in the loop for certain conditions - especially those items that relate to regulatory, PII, or legal matters or in the case where prioritization and confidence is not high enough to automate.  

## 4. Data & Model Approach

The approach will be grounded (RAG).  This allows the Rocketship internal systems to be the sources for which Juno synthesizes its data.  Buying a LLM solution that is generic creates real risk of hallucination and incorrect outcomes.  The buy option would still force customization to Rocketship data sources to work properly.

## 5. Risks & Mitigations

A risk is that Juno is overly biased to certain inputs/sources to drive prioritization.  While PO and P1 tickets are important they must be balanced against roadmap items with KPI/ROI established that could have bigger benefit than some high support tickets.
To avoid this situation the output has to balance across the sources when prioritizing.  The amount of items from each source should  be tracked and measured.  There should not be more than 30% from any one source over a period of 2 months.  If this occurs it must be flagged for the human PM to assess Juno guardrails and inform more specific prioritization.

## 6. V1 Scope

The Juno solution should not:
1) Create an communications to stakeholders automatically.  All communication is flagged to the PM to ultimately action.
2) Where there are competing items from two different sources (i.e. Jira and Notion), Juno should not break the tie but highlight to PM to action.
