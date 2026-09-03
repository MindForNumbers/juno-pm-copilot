# AI Solution Decision Matrix · Juno

## The decision

Whether RocketShip builds Automated Prioritization and Spec Drafting in Juno as a custom 6-agent Hybrid (RAG + Agentic) Copilot, vs buying an off-the-shelf AI product tool/API, vs fine-tuning an open-source LLM on internal artifacts. Why now: Product discovery is bottlenecked by manual qualitative analysis, and roadmap priorities reverse weekly because decisions lack verifiable customer evidence to withstand executive scrutiny.

## Options scored

| Option | Cost | Speed | Control | Moat | Risk | Score |
|---|---|---|---|---|---|---|
| Build | 2 | 2 | 5 | 5 | 4 | 3.6 |
| Buy / API | 5 | 5 | 2 | 1 | 2 | 3.0 |
| Fine-tune | 3 | 2 | 4 | 4 | 3 | 3.2 |

## Recommendation

Build. Control and Moat are the decisive axes for enterprise roadmap governance. An off-the-shelf Buy/API tool cannot enforce strict citation contracts or custom schema definitions across proprietary Zendesk, Gong, and Slack silos, recreating the loudest-voice problem. Fine-tuning is too rigid for fast-moving product changes and still requires live retrieval. Building a custom 6-agent Hybrid Copilot gives us full governance over research synthesis, engineering risk flagging, and telemetry specs while keeping the PM in control of final publication.
