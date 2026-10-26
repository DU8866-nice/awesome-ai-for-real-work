# Choose a tool / 如何选工具

Start with one deliverable: a cited answer, an action list, a table, a brief, a chart or a slide deck. Pick the smallest toolchain that can produce it. A high star count helps you discover a project; it does not tell you which one you can run well.

先说清楚要交付什么，再选最短的工具链。想整理一段会议，不必先搭一个全功能智能体平台。

| Route / 路线 | Good starting point / 起点 | Preparation / 准备 |
| --- | --- | --- |
| Desktop / 桌面起步 | AnythingLLM, Meetily | Install the supported edition; prepare documents or audio and a model route. / 装支持的版本，准备资料和模型。 |
| Visual workflow / 可视化流程 | Dify, n8n, Activepieces | A running instance, provider credentials and a bounded flow. / 可用实例、服务凭据和具体步骤。 |
| Developer / 开发接入 | Docling, Stagehand, Deep Agents | Runtime, code, model/tool configuration and output validation. / 开发环境、代码、模型工具与检查。 |
| Team system / 团队部署 | Onyx, RAGFlow | Storage, permissions, indexing, model services and maintenance. / 存储、权限、索引和维护。 |

## Four separate costs / 分开看四种成本

1. **Application**: Community, enterprise and hosted editions can differ. / 社区、企业与托管版本不一定相同。
2. **Model services**: Language, embedding, reranking, search, transcription and image generation may be billed separately. / 大模型、嵌入、重排、搜索、转写和生图可能各自收费。
3. **Hardware and hosting**: Local models consume memory, storage and compute; a self-hosted web interface can still call a cloud model. / 本地模型占硬件，自托管界面也可能调用云模型。
4. **Checking and maintenance**: Budget time to inspect references, numbers, exports and changed integrations. / 给核对引用、数字、导出和维护接口留出时间。

No prices or hardware performance are promised here. Check the upstream documentation for the particular version, model and deployment route. / 本库不承诺固定价格或硬件表现，以所选版本的官方要求为准。

## Make the output checkable / 让结果能验收

- Documents: cite source IDs and say when the supplied files do not answer the question. / 文档问答应有来源，没依据就明确说不知道。
- Meetings: separate decisions, commitments, suggestions and unresolved items. / 把决定、承诺、提议和未决事项分开。
- Tables: preserve source links and use null for unavailable fields. / 表格保留来源，缺字段不编。
- Reports: compute metrics from the input and state the denominator. / 指标要计算，并说清分母。
- Browser actions: start read-only; define where the flow must stop before submitting or changing information. / 浏览器先从只读开始，事先规定提交与修改的边界。
- Slides: inspect the exported file, not just the generation preview. / 检查实际导出的文件。

The [starter pack](../examples/starter-pack.json) contains synthetic inputs and authored checks for six tasks. It does not need an API key to read; actually generating an AI output requires your chosen tool and provider.

[English README](../README.md) · [中文首页](../README.zh-CN.md)
