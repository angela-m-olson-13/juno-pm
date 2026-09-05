# Agent Workflow Spec (AWSpec) · Juno

## Goal

PO are prioritized into a daily top 3 with source and strategic pillar sited.  

**Primary actor:** Agent + Human-in-the-loop

## Trigger

A new message for escalation thread is established for a PO critical priority item.  That thread should have at least 3 in the thread length within a 30 minute time span.  

## Steps & tools

**Pattern:** ReAct (single-agent reason-act-observe loop)

| Step | Action | Tool / model | Guardrail |
|---|---|---|---|
| 1 | Read the thread and customer id and any KPI/ROI impact sited. | slack.read_thread(id), read-only | Agent can READ Slack #escalations + Strategy document + Salesforce ROI + Salesforce KPI. Agent can WRITE to PM daily report and create Jira stubs. Agent CANNOT edit Salesforce records, edit Jira tickets after creation, or post outside PM daily report. |
| 2 | RAG retrieval over the RocketShip Strategy, top-K = 8. | corpus.retrieve(query, k=6), read-only |  |
| 3 | Score the risk and align with strategic pillar.  Priorities are P0-P3. | salesforce.lookup_roi(customer_id), read-only |  |
| 4 | Draft summary card (transcript quote + strategic citation). | salesforce.lookup.kpi(customer_id), read-only |  |
| 5 | Post to the daily PM report or provide to human PM for review if confidence does not meet threshold. | jira.create_stub(payload), write, requires confidence >= 75% |  |
| 6 | _ | slack.post(channel, payload), write, restricted to PM daily report |  |

**Schemas**

- corpus.retrieve → {chunks:[{text,source,pillar,score}]}.
- salesforce.lookup_roi → {roi_usd, contract_end, churn_risk}.
- salesforce.lookup_kpi → {kpi_%, contract_end, churn_risk}.
- jira.create_stub → {ticket_id, url, status}.

**Memory (in or out of scope)**

- **Episodic:** In-scope: Juno outputs, retrieved information from source and any prioritization scores.  
Lifetime:  end of run.
- **Semantic:** In-scope: RocketShip strategy, Juno system prompt, and any PM preferences.  Lifetime: indefinite, with weekly refresh.
Out of scope: Any legal contracts or PII information. 
- **Working:** In-scope: Current thread, customer identifier, any KPI/ROI sited, confidence score and any specific source sites. 
- **External:** Slack thread API (read), Notion thread API (read), Support tickets (read), RocketShip Strategy (read), #pm-daily channel (write), Jira (write, stub creation only).

## Human-in-the-loop

PM reviews any PO escalation with less than a 75% confidence level.  PM has 1 hour to review once notified, before it is published to the daily report.

## Success & failure

- **Done when:** - Success: Top 3 risks are published to the daily PM report.  
- Failure: if any single tool error occurs, log the issue and report.  Stop agent.
- Escalation: any items with less than 75% confidence need to be escalated to human PM for review.
- Timeout: 90s wall clock → abort with partial output.
- **Fails safe when:** Agent can READ Slack #escalations + Strategy document + Salesforce ROI + Salesforce KPI. Agent can WRITE to PM daily report and create Jira stubs. Agent CANNOT edit Salesforce records, edit Jira tickets after creation, or post outside PM daily report.

- [ ] Every tool lists scope (read-only vs write) and a schema.
- [ ] Read/write boundaries match the AI PRD (M3).
