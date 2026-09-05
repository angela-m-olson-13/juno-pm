# AI PRD · Juno

## Problem & user

RocketShip PMs need evidence-based prioritization. Juno turns noisy Slack, tickets, and strategy docs into a ranked, cited backlog they can defend.

## Solution overview

**Retrieval strategy:** Hybrid

Hybrid is best approach.  Juno PM needs to synthesize specific data that requires specific date/time/person.  Juno PM also needs to ascertain trends and sentiments over time to inform prioritization and concerns that are more hidden.  Long context would be taxing in terms of tokens to read full data when not necessary and RAG alone will miss full contenxt / sentiment.  Therefore need balance of both to meet the needs of the Juno PM and human PM.

## Retrieval requirements (RAG)

- **Sources:** Juno must access Rocketship internal:  Slack channels, support tickets, Jira, and Notion.  The Strategy established in module 2 provides the overall context.
In terms of volume, there should be 2 months of data from each of these sources to build historical context for prioritization.
- **Chunking / indexing:** Hybrid (Semantic + Keyword)
- **Grounding rule:** Each priority identified needs to reference the Strategy document as well as cite the source for which the item came from (i.e. Jira, Notion, etc.) as evidence.  Exact quotes or statements from the source should be included for reference to the PM.
- **Freshness:** The Strategy, when changed, should be used immediately as soon as published.  Data sources beyond support tickets should be refreshed every two hours, every day.  Support tickets should be updated every 30 minutes every day.

## Requirements

| # | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| 1 | Retrieval quality and latency | Must | Top-K = 8 retrieval segments per prioritization run. p95 latency target < 3s end-to-end (from "Process" click to ranked PRD draft). At our $0.03/1k token blended cost, this lands at ~$0.07 per Juno run - acceptable for daily PM use. |
| 2 | Fail-safe on empty retrieval | Must | If retrieval returns < 3 relevant segments OR if no strategy doc is loaded, Juno does NOT produce a P0/P1 ranking. Instead it returns a clear banner: "Insufficient evidence to recommend priority - load a strategy document or escalate to PM judgement." |
| 3 | Grounded trust | Must | Each priority identified needs to reference the Strategy document as well as cite the source for which the item came from (i.e. Jira, Notion, etc.) as evidence.  Exact quotes or statements from the source should be included for reference to the PM. |

## Out of scope

Decisions that cannot be cited to a source in the knowledge base. Anything Juno is not allowed to retrieve or act on without a human.
