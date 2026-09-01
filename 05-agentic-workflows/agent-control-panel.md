# Agent Control Panel · Juno

## Autonomy level

Agent can draft a P0 risk summary and Jira stub.  Agent cannot auto-close threads or direct message customers.

## Controls

- **Kill switch:** max_steps: 6.  Abort if same tool fails 2x in a row.  Hard timeout:  90 seconds wall clock
- **Rate / cost caps:** corpus.retrieve -> {chunks:{{text, source, score}], summary, confidence}.
salesforce.lookup_arr -> {arr_usd, contract_end, churn_risk}.
- **Escalate-on-stuck:** After 3 failed retrievals -> degrade to 'cautious mode' (no priorities - just thread links).  After 2 tool errors -> escalate to PM with full trace.

## Monitoring

**Confidence thresholds (map to actions):**

>= 80% -> auto-post to #pm-daily.  70 to 79% -> post to #pm-juno-review with @on-call-pm.  <70% -> require PM approval.

**Checkpoints:**

Any thread mentioning 'churn', 'legal', or 'security' -> requires approval.  Any PO with confidence < 70% -> PM review.

**North Star (re-read every loop):**

Your single goal is to surface the top-3 strategic risks from #escalations every weekday morning.  Always cite a strategic pillar.  Never invent customer names.  Escalate ambiguity to the PM.

## Permissions

READ:  Slack #escalations, Strategy KB, Salesforce ARR.  
WRITE: #pm-daily only, Jira stubs only.  Cannot edit Salesforce or post outside of #pm-daily.

