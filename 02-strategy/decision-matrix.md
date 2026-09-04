# AI Solution Decision Matrix · Juno

## The decision

Whether RocketShip builds Automated Prioritization in Juno as a Hybrid (RAG + Agentic) Copilot, vs buying a generic LLM API or fine-tuning a model on our corpus.

Why now: roadmap discussions are driven by the loudest voice in Slack rather than customer evidence. Priorities reverse weekly, and the PM cannot defend the call to leadership.

## Options scored

| Option | Cost | Speed | Control | Moat | Risk | Score |
|---|---|---|---|---|---|---|
| Build | 2 | 2 | 5 | 5 | 4 | 3.6 |
| Buy / API | 5 | 4 | 2 | 1 | 2 | 2.8 |
| Fine-tune | 3 | 2 | 4 | 4 | 3 | 3.2 |

## Recommendation

Buy / API is faster, but would require customization on top to actually work against the source systems in Rocketship.  Therefore the speed is offset by the needs still to make it work against the datasources.
Build will create a tailored solution, meeting the risk areas in a more customized manner, but does carry some risk in ensuring rules are built in to ensure output is actionable and drives correct outcomes.  
Fine-tune will still need to overcome the specifics of the data sources and being able to cite and ascertain them properly.  

Given the Build option allows the greatest control for the human PMs that can be continually tailored, this is the better option given buy speed is offset by the remaining customization needed.
