# Trust-Gap Mitigations · Juno

## Trust gaps

| Gap | Where it shows up | User cost | Mitigation |
|---|---|---|---|
| **The Black-box Gap** | Can the user see why the AI decided? | Closed (5/5 closed) | The actual source is sited for each item along with a portion of the statement or quote so it can be referenced.   |
| **The Hallucination Gap** | Could this confidently be wrong? | Mostly closed, residual risk (4/5 closed) | Where there is low confidence in output, it should be clearly called out that there is low confidence in each instance card.  "Low confidence" should be clearly called out for these items. |
| **The Control Gap** | Can the user steer or stop? | Closed (5/5 closed) | There is an undo button that the human PM can utilize, for which they could do a direct edit and process again. |
| **The Intelligence Tax** | Is the latency / privacy / cognitive load worth the value? | Closed (5/5 closed) | There should be clear labels at all times on data privacy - this can be resolved in a privacy badge being displayed.  Memory in Juno could be utilized only if the human PM opts into this.  There are status updates provided as Juno is processing. |

## Highest-priority fix

**The Hallucination Gap** (4/5). Where there is low confidence in output, it should be clearly called out that there is low confidence in each instance card.  "Low confidence" should be clearly called out for these items.

## Verdict

**Shippable.** Trust posture passes the M4 readiness check. Confirm with eval data in M6 (golden set + guardrails).
