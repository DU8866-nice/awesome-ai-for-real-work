# Sources → reviewable slides / 来源事实变幻灯片

**Status:** documentation-reviewed blueprint, not an end-to-end tested integration. This is a conceptual route, not an importable native workflow. The original synthetic pilot facts and expected outline are author-defined, not actual AI output.

## English

**Deliverable.** A deck of at most six slides using six supplied pilot facts, with visible source IDs on factual slides and a reviewed export. An attractive layout must not introduce results absent from the evidence.

**Choose a starting tool.** [Presenton](https://github.com/presenton/presenton) offers Windows/macOS/Linux desktop applications and a Docker web route, with editable PPTX export. [Banana Slides](https://github.com/Anionex/banana-slides) provides outline/material-based generation, visual editing, and exports; editable PPTX export is labeled Beta. [PPTAgent](https://github.com/icip-cas/PPTAgent) is an agent-skill route with a more involved development environment, including platform, Python, browser, and office-conversion dependencies. Start with an application interface unless you need that flexibility.

**Prepare.** Select supported text and optional image providers. Local models need compatible inference and sufficient memory; remote providers can charge for text and images. Banana Slides' image-model services may be paid. Free source code does not make generation or hosting free. PPTAgent's documented skill route requires Linux/WSL or macOS, uv, npm, and LibreOffice: verify current requirements before choosing it. This blueprint installs or runs none of these tools.

**Route — four steps.**

1. Create a fact ledger with one source ID per supplied statement; identify the audience and maximum slide count.
2. Draft an outline before generating slides. Attach each fact's source ID to its destination slide; use only supplied numbers.
3. Generate or compose the deck in one selected tool. Use restrained visuals; label any decorative illustration so it cannot be mistaken for measured data.
4. Inspect every exported slide for clipped text, readable citations, numerical fidelity, and editable/export behavior. Open the actual PPTX/PDF, not just an outline preview.

**Try the case.** Select `sources-to-slides` in [starter-pack.json](../examples/starter-pack.json). Supply `inputs`, keeping `expected` for later review. Its six facts cover duration, people, teams, task types, interviews, and a pending decision. A six-slide reference outline is supplied, but alternative layouts may pass. No time savings, ROI, or approved rollout is present. Reading the fixture requires no model; deck generation must be run separately by you.

```text
Create an outline in Chinese for at most inputs.max_slides slides using
only inputs.facts. Return slides with title and facts; each fact needs its
exact source_id. Cover all six source IDs. Preserve numbers and the pending
decision status. Do not invent benefits, percentages, ROI, quotes, or an
approved rollout. Mark missing evidence explicitly. Keep source IDs visible
when turning the outline into a deck, then review the exported pages.
```

**Acceptance.**

- The deck contains at most six slides.
- All six source IDs are covered, and factual claims retain their IDs.
- Quantities and pending status remain exact.
- The export is legible without clipped content.
- No unsupported savings or rollout claim is added.

**Limits.** Generated images may distort text or imply evidence. Exported elements may differ from the editor, especially in evolving editable formats. The fixture can check content planning; it cannot prove PPTX editability, rendering quality, or compatibility with your office application.

## 中文说明

交付最多 **6 页**的试点汇报，覆盖样例六项事实，每项事实在页面上回指来源编号。参考大纲并非唯一答案，可以合并排版，但不得新增节省时间、收益率或已批准推广等结论。

普通用户可先看 Presenton 的三平台桌面版或 Banana Slides；后者可编辑 PPTX 导出标为 Beta。PPTAgent 是代理技能路线，涉及 Python、浏览器、LibreOffice 及 Linux/WSL 或 macOS 等环境，准备更复杂。文本模型和图像模型分别确认费用，Banana Slides 的图像服务可能收费；开源不等于运行全免费。本地推理也要准备硬件。

操作顺序为建立事实清单、先定带来源的大纲、生成或排版、打开实际导出文件检查。上方提示词要求中文大纲；只复制样例 `inputs`，让 `expected` 保持为答案键。装饰图不能冒充试点截图或数据图。

验收看页数、六个来源覆盖、数字与待决定状态准确、导出可读、没有新增效果承诺。内容检查可以对 JSON 做；文字溢出、图片错字、PPTX 可编辑性和办公软件兼容性必须检查真实导出。本文是**经文档审阅的概念蓝图，并非端到端验证过的集成**，没有把大纲样例当成实际生成的演示稿。

[English index](../README.md) · [中文目录](../README.zh-CN.md) · [Example guide / 样例说明](../examples/README.md)
