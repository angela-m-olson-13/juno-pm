# Trust-Gap Mitigations · Juno

Feature: Juno PM - before a lot of RAG features are built in.

## Trust gaps

| Gap | Where it shows up | User cost | Mitigation |
|---|---|---|---|
| **The Black-box Gap** | Can the user see why the AI decided? | Noticeable but recoverable (3/5 closed) | Citations to the actual source of the requested product features.  Actual quotes within transcripts. |
| **The Hallucination Gap** | Could this confidently be wrong? | Noticeable but recoverable (3/5 closed) | Specify "watermarks" where there is low-confidence.  Provide supporting signal evidence from transcripts. |
| **The Control Gap** | Can the user steer or stop? | Noticeable but recoverable (3/5 closed) | An undo button to the transcript provided. Able to regenerate after PM override of clarity on problem statement.  |
| **The Intelligence Tax** | Is the latency / privacy / cognitive load worth the value? | Noticeable but recoverable (3/5 closed) | Clear indications of data privacy and data use, including memory.  Provide real-time process steps while processing data - status breadcrumbs. |

## Highest-priority fix

**The Black-box Gap** (3/5). Citations to the actual source of the requested product features.  Actual quotes within transcripts.

## Verdict

**Hold.** At least one gap is still open. Close before shipping or down-scope the feature until the gap is closed.


_____
