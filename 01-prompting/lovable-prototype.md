# Prototype · Juno

## Prototype link

https://product-mind-fusion.lovable.app

## What it demonstrates

The end-to-end orchestration of a 6-agent AI product squad. It proves the flow of taking raw, unstructured multi-channel inputs (like support tickets or transcripts), pushing them through sequential and parallel AI specialist agents, and consolidating the output into a single, Jira-ready PRD dashboard.

## Debrief

- **What worked:** The locked 3-column layout and the visual state management. The interactive pipeline stepper successfully organized the cognitive load, allowing users to inspect the intermediate JSON outputs of individual agents (like the Synthesizer or Data Scientist) without losing the context of the master PRD rendering in the Markdown preview canvas.
- **What broke / felt like a toy:** The parallel execution logic for the specialist agents (Engineer, Marketer, Data) felt completely simulated. Because this is a frontend-heavy prototype, it relies on static or sequentially chained timeouts rather than true asynchronous multi-agent processing. Furthermore, without a live backend ingest API endpoint handling webhooks from Slack or Zendesk, the 'Data Intake' column acts as a manual text-dump rather than a seamless pipeline, making the automation feel like a toy.
- **What I'd change next pass:** I would decouple the orchestration logic entirely from the frontend. Next pass, I would build a dedicated backend ingest API to handle the actual LLM chaining (via LangGraph or CrewAI) and true parallel execution. The frontend UI should be reduced to a thin client that simply polls the backend and renders the streaming Markdown and JSON payloads as the agents complete their tasks. I redo the UI/UX. Although I love the proposed mechanics it's too bust and it can be overwhelming for the average user.
