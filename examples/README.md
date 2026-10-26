# Starter cases / 入门样例

[starter-pack.json](starter-pack.json) contains six original fictional exercises. `schema_version` is `1`, and `synthetic` is `true`. None of the sources, organizations, people, pages, or results describes a real pilot. The `expected` objects are human-defined answer keys, **not actual AI run results**. These cases accompany documentation-reviewed blueprints, not end-to-end tested integrations.

## Try one manually / 手工试一题

1. Pick a case and open its linked guide below. Read its `inputs`; you do not need an API, account, model download, or installation simply to inspect this file.
2. Copy only that case's `inputs` into your chosen tool, together with the guide's prompt. Hide `expected` and `review_checks` until after generation so the answer key cannot leak into the result.
3. Run the actual AI step yourself if desired. Configure its model, permissions, hardware, credentials, and budget separately. This repository does not run a provider or create an integration for you.
4. Save the result locally and compare the defined fields with `expected`. Check meaning and sources as well as values. A paraphrase can pass even when its text differs from the reference.
5. For a real document, recording, website, report, or deck, also inspect the original source and final exported artifact. Fixture success alone does not demonstrate production readiness.

先选一题并阅读对应指南。样例不需要 API 就能阅读或用计算器核对；真正的转写、检索、生成或浏览步骤须自行配置并运行。只把 `inputs` 和提示词给工具，隐藏 `expected` 答案键，完成后再比对。不要把整个 JSON 当成知识库输入，否则模型会直接看到答案。

| Case / 题目 | Guide / 指南 | Main check / 核心检查 |
| --- | --- | --- |
| `documents-to-answers` | [Documents → answers](../workflows/documents-to-answers.md) | 30 days, Mira, correct `docid`, unknown budget / 周期、负责人、引用、拒绝猜测 |
| `meeting-to-actions` | [Meeting → actions](../workflows/meeting-to-actions.md) | Commitments separated from proposals / 承诺与提议分开 |
| `browser-to-table` | [Browser → table](../workflows/browser-to-table.md) | Unknown price stays `null`; sources persist / 未知价格为空并保留来源 |
| `weekly-report` | [Weekly report](../workflows/weekly-report.md) | 77.27%, 81.48%, +4.21 percentage points / 加权完成率与百分点 |
| `research-to-brief` | [Research → brief](../workflows/research-to-brief.md) | Approved two-hour rule versus three-hour proposal / 现行规则与新提议 |
| `sources-to-slides` | [Sources → slides](../workflows/sources-to-slides.md) | Six facts, at most six slides, source IDs / 六项事实、最多六页、来源编号 |

## What the answer keys mean / 答案键含义

The authors selected the source texts, approval statuses, questions, output fields, and desired evidence behavior. They are pedagogical constraints, not measured model accuracy. The reference slide outline is one acceptable arrangement, not a required design. Natural-language action labels and Chinese translations may vary when their meaning remains faithful. Missing information is intentionally represented by JSON `null`, never the string `"null"`, an empty guess, or numeric zero.

内容、批准状态、字段与期望均由作者人为定义，用来暴露常见错误；并非模型评测成绩。幻灯片参考大纲允许重排，行动描述允许忠实改写。空值有意使用 JSON `null`，不能替换成零或字符串。

## Mechanical checks and human review / 机械检查与人工判断

A small script can parse the JSON, verify six unique case IDs and required keys, compare exact numerical/null/status fields, and verify that cited IDs exist in the relevant inputs. Compare ID sets independently of ordering. For the weekly case, recompute sums from `inputs.rows`, calculate rates from total counts, and calculate the difference **before rounding**; use a tolerance of `0.005` for the displayed two-decimal values. These calculations do not need AI.

For a generated outline normalized as `slides[].facts[].source_id`, a script can count slides, check the allowed source IDs, and confirm all six are referenced. It cannot establish that each sentence faithfully represents its source merely because the ID is present. Compare the numerical and pending-decision constraints separately. The `expected` structure is a lightweight teaching contract, not a native workflow format or universal provider response schema; normalize a tool's output before field comparisons.

Human review still decides whether quotations support conclusions, a suggestion was misrepresented, current authority was established, or a deck is legible. `review_checks` records those judgments. The cases contain no PDF, audio, live web navigation, or rendered PPTX: they do not verify OCR, diarization, browser compatibility, provider availability, model quality, or export fidelity. The fictional `.invalid` URLs are provenance labels and must not be opened.

可机械检查 JSON 格式、六个唯一编号、必填字段、数字、空值、状态和引用编号是否存在。周报从四行重新求和，不平均团队百分比；先用原始比率求差再显示两位小数。幻灯片可以数页和查编号，但“有来源编号”不能证明内容忠实。语义、批准权威、录音身份、真实网站操作及导出可读性仍靠人工或真实环境检验。

[English index](../README.md) · [中文目录](../README.zh-CN.md)
