<div align="center">
  <h1>Awesome AI for Real Work</h1>
  <img src="media/workflow.svg" width="800" height="210" alt="Input, AI workflow, reviewable output">
  <p><strong>Choose a task. Build a workflow. Check the output.</strong></p>
  <a href="https://awesome.re"><img src="https://awesome.re/badge-flat2.svg" alt="Awesome"></a>
</div>

<p align="center">
  <a href="README.zh-CN.md">简体中文</a>&nbsp; · &nbsp;
  <a href="docs/choosing-tools.md">Choose a tool</a>&nbsp; · &nbsp;
  <a href="docs/source-review.md">Source review</a>&nbsp; · &nbsp;
  <a href="contributing.md">Contributing</a>
</p>

A task-first collection of **30 AI projects across 9 categories**, with **6 workflow blueprints**, synthetic starter inputs and concrete output checks. Find a useful starting point for documents, meetings, browser tasks, research, reports and slides.

Start with the job, then choose the tool. Entries distinguish desktop apps, visual builders and developer tools, and state the model or deployment preparation. Stars are a discovery signal, not evidence that a tool fits your task.

**New here?** Pick one task below and try the [synthetic starter inputs](examples/starter-pack.json). The guides are workflow blueprints, not native one-click imports.

## Contents

- [Start with a Task](#start-with-a-task)
- [Personal Agents](#personal-agents)
- [Visual Workflows](#visual-workflows)
- [Document Intake](#document-intake)
- [Knowledge Workspaces](#knowledge-workspaces)
- [Research and Briefs](#research-and-briefs)
- [Browser Tasks](#browser-tasks)
- [Audio to Actions](#audio-to-actions)
- [Data and Slides](#data-and-slides)
- [Evaluation](#evaluation)
- [Selection and Review](#selection-and-review)
- [Related](#related)

## Start with a Task

| I want to | Start with | Reviewable output |
| --- | --- | --- |
| [Answer questions from your documents](workflows/documents-to-answers.md) | AnythingLLM / Docling | Answer + source IDs; unsupported questions stay unknown. |
| [Turn a meeting into actions](workflows/meeting-to-actions.md) | Meetily | Transcript + decisions + owners that were actually stated. |
| [Collect a comparison table](workflows/browser-to-table.md) | Browser Use / Stagehand | A table with sources and explicit missing fields. |
| [Draft a weekly report](workflows/weekly-report.md) | n8n / Data Formulator | Computed metrics + a short explanation. |
| [Write a source-backed brief](workflows/research-to-brief.md) | GPT Researcher / DeerFlow | Claims, references and unresolved disagreements. |
| [Make slides from approved facts](workflows/sources-to-slides.md) | Presenton | An editable deck with checked facts and layout. |

Each guide includes English and Chinese instructions, a reusable prompt, sample inputs and acceptance checks. Fixture `expected` values are authored targets, not recorded AI outputs.

## Personal Agents

- [OpenClaw](https://github.com/openclaw/openclaw) - A personal assistant that connects models, tools and messaging surfaces to carry out multi-step tasks. `Agent / setup`. Configure a model and the tools it may use; local installation does not make a hosted model local. Start with a read-only folder task.
- [Hermes Agent](https://github.com/NousResearch/hermes-agent) - An assistant with reusable skills, persistent context and terminal or messaging interfaces. `Agent / CLI`. Choose a model provider and execution backend. Inspect created skills before reusing them; provider and hosted-backend charges are separate.
- [Deep Agents](https://github.com/langchain-ai/deepagents) - An agent harness with planning, filesystem context and subagent building blocks for longer tasks. `Developer`. This is a development foundation, not a ready-made office assistant. Supply a tool-calling model, tools and an appropriate execution environment.

## Visual Workflows

- [n8n](https://github.com/n8n-io/n8n) - Connect triggers, application integrations and AI steps into a repeatable workflow. `Visual / self-host or cloud`. Configure service credentials and a model where needed. Self-hosting, cloud plans and model calls have different costs; n8n uses fair-code licenses.
- [Activepieces](https://github.com/activepieces/activepieces) - Build app-to-app flows with reusable integration pieces and AI actions. `Visual / self-host or cloud`. Connect only the services a flow needs. Community Edition is MIT; enterprise features and hosted plans have separate terms.
- [Dify](https://github.com/langgenius/dify) - Create AI applications using model configuration, document retrieval and workflow steps. `Visual / server`. Needs a deployed instance and model/embedding services for the chosen flow. The Dify license includes conditions beyond Apache 2.0.
- [Langflow](https://github.com/langflow-ai/langflow) - Compose AI components visually and expose a finished flow through its APIs or tool interfaces. `Desktop or server / visual`. Use a supported desktop package or deploy the service, configure authentication and connect a model. A visual canvas still needs working components and credentials.

## Document Intake

- [Docling](https://github.com/docling-project/docling) - Parse documents into structured representations for search, extraction and AI workflows. `Developer / Python`. Prepare the parser models and a suitable runtime. Code is MIT; individual model licenses and complex-layout quality need separate checks.
- [MinerU](https://github.com/opendatalab/MinerU) - Convert complex PDFs and office documents into Markdown or JSON for downstream processing. `Parser / setup`. Choose a supported parsing backend and prepare models. Code includes additional license conditions; hosted parsing and local execution differ.
- [Marker](https://github.com/datalab-to/marker) - Convert documents to Markdown or JSON while retaining useful layout and table structure. `Developer / Python`. Check the current backend and model requirements. Apache-2.0 code and the model weights have different commercial-use terms.
- [MarkItDown](https://github.com/microsoft/markitdown) - Turn supported office and other files into Markdown that is easier to inspect and feed into AI tools. `Developer / Python`. Basic conversion is not an AI agent. Optional image-description and document-intelligence routes require their own services and credentials.

## Knowledge Workspaces

- [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) - Organize documents in workspaces and ask questions using configured language and embedding models. `Desktop or self-host`. Desktop is a practical starting point. Check the chosen model route, file parsers and workspace sources; cloud providers may receive content.
- [RAGFlow](https://github.com/infiniflow/ragflow) - Build document-grounded retrieval and question-answering workflows with parsing and agent features. `Server / setup`. Prepare the service stack, storage and model providers. The current upstream Docker guide excludes macOS; follow its supported deployment route.
- [Onyx](https://github.com/onyx-dot-app/onyx) - Connect team knowledge sources and provide AI search and chat over indexed information. `Team / self-host`. Connector access, indexing and model routing need configuration. Edition-specific licensing and source permissions matter for a team deployment.
- [Open Notebook](https://github.com/lfnovo/open-notebook) - Keep source material, notes and model-assisted conversations together in a notebook workspace. `Web / self-host`. Configure the services used for language, embedding, speech or generated audio. Self-hosting the notebook does not make every provider local.

## Research and Briefs

- [GPT Researcher](https://github.com/assafelovic/gpt-researcher) - Gather material and generate a research report with source references. `Research agent / setup`. Configure the selected model and search/data providers and set a run budget. Check that citations support each claim and are current.
- [DeerFlow](https://github.com/bytedance/deer-flow) - Coordinate longer research and creation tasks with tools, files and a configured execution environment. `Agent harness / setup`. Configure the model, optional search and sandbox/tool access. Its broader execution capability requires more setup than a search box.

## Browser Tasks

- [Browser Use](https://github.com/browser-use/browser-use) - Use a language-model agent to navigate pages and perform browser tasks. `Developer / browser agent`. The library, hosted browser and hosted models are separate offerings. Start with public read-only extraction and a bounded output schema.
- [Stagehand](https://github.com/browserbase/stagehand) - Combine browser actions and structured extraction in an application workflow. `Developer / SDK`. Requires programming and a model configuration; browser hosting depends on the deployment route. Validate extracted fields against the page.
- [Skyvern](https://github.com/Skyvern-AI/skyvern) - Automate browser workflows using model-assisted page understanding and visual interaction. `Browser workflows / setup`. Configure a model and browser environment. Local/self-hosted and managed services differ; AGPL code terms apply to the selected edition.

## Audio to Actions

- [faster-whisper](https://github.com/SYSTRAN/faster-whisper) - Transcribe recordings using Whisper models through CTranslate2. `Developer / Python`. Download models and choose CPU or a compatible GPU setup. It produces a transcript, not a trustworthy summary or action list by itself.
- [WhisperX](https://github.com/m-bain/whisperX) - Add alignment, word-level timestamps and optional speaker diarization to transcription. `Developer / Python`. Alignment and diarization have separate models and requirements; some downloads need provider access acceptance. Speaker labels do not identify real people.
- [Meetily](https://github.com/Zackriya-Solutions/meetily) - Capture or import meeting audio, transcribe it and generate model-assisted summaries. `Desktop / local-first`. Choose local or hosted summary models. Windows/macOS packages and Linux source setup differ, as do Community and PRO features. Check commitments against the recording.

## Data and Slides

- [Data Formulator](https://github.com/microsoft/data-formulator) - Explore data with AI-assisted transformations and visualizations. `Interactive / setup`. Prepare the data and supported model route. Recompute totals, filters and denominators before using a generated chart in a report.
- [Presenton](https://github.com/presenton/presenton) - Generate, edit and export presentations using a configured model and your source material. `Desktop or self-host`. Use the desktop or self-hosted app, configure a model and any image services, then visually inspect the actual editable PPTX export.
- [Banana Slides](https://github.com/Anionex/banana-slides) - Create slide decks from ideas, outlines, source documents and visual references. `Web / setup`. Configure supported language/image providers. Image calls may cost extra; editable PPTX export is marked Beta and needs inspection.
- [PPTAgent](https://github.com/icip-cas/PPTAgent) - Create and revise presentations through an agent-assisted generation and review workflow. `Developer / agent skill`. The current main branch uses an agent-skill route with Linux/WSL or macOS, development tools and LibreOffice conversion dependencies. Follow the matching version.

## Evaluation

- [promptfoo](https://github.com/promptfoo/promptfoo) - Compare prompts or models against reusable test cases and output assertions. `Developer / CLI`. Model-based runs may cost money. Deterministic checks and model-judged scores answer different questions; inspect failures, not just a single score.
- [Langfuse](https://github.com/langfuse/langfuse) - Trace AI application runs and organize evaluation, datasets and feedback. `Observability / setup`. Instrument the application and choose where traces are stored. Community and enterprise features differ; traces may contain prompts and outputs.
- [Arize Phoenix](https://github.com/Arize-ai/phoenix) - Inspect model and retrieval traces and evaluate AI application behavior. `Observability / setup`. Instrumentation and evaluation still require setup and may use model services. Phoenix uses Elastic License 2.0; do not assume an MIT/Apache grant.

## Selection and Review

Reviewed **2026-10-26** against primary repository metadata and READMEs. Archived projects are excluded from the main list. See the [source review](docs/source-review.md) for dated star snapshots, upstream links, last-push timestamps and review limits, or use the [machine-readable catalog](docs/catalog.json).

Entries need a concrete task, primary documentation and an output a person can inspect. The collection includes open-source and source-available projects with additional conditions. **Application licenses, model-weight licenses, hosting and API charges are separate questions.** This list's CC0 dedication does not relicense upstream projects.

This is an AI-assisted, documentation-reviewed collection. The 30 applications were not individually installed or runtime-tested for this edition, and the six blueprints are not end-to-end tested integrations. Synthetic fixtures and deterministic checks help you inspect results; they do not certify generated content. Read [contributing](contributing.md) to propose an addition or correct a claim.

## Related

- [Awesome](https://github.com/sindresorhus/awesome) - The clear contents and concise-entry convention used by this list.
- [Awesome LLM Apps](https://github.com/Shubhamsaboo/awesome-llm-apps) - AI application examples and agent projects for deeper development.
- [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents) - A broader directory of agents and products.
- [Awesome Offline Productivity](https://github.com/DU8866-nice/awesome-offline-productivity) - The companion collection for local-file and offline tasks.

The selection, descriptions and examples here are independently authored. There is no affiliation with the referenced lists, paid placement, affiliate linking or fabricated test result.
