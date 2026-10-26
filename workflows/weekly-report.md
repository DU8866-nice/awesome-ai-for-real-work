# Rows → weekly report / 数据行变周报

**Status:** documentation-reviewed blueprint, not an end-to-end tested integration. This is a conceptual route, not an importable native workflow. The original synthetic rows and expected calculations are author-defined, not actual AI output.

## English

**Deliverable.** A two-week delivery summary with reproducible totals, completion rates, a percentage-point comparison, and a short narrative that does not invent causes.

**Choose a starting tool.** [n8n](https://github.com/n8n-io/n8n) and [Activepieces](https://github.com/activepieces/activepieces) provide visual automation builders for connecting inputs, calculations, and review steps. They require a hosted or self-managed service. [Data Formulator](https://github.com/microsoft/data-formulator) is a visual AI data exploration application for tables and charts. Use a supported self-contained desktop build, or prepare its Python/container route; current CI artifacts and tagged releases have different availability. It is not a drop-in n8n or Activepieces node. Begin manually in one interface before automating refreshes.

**Prepare.** Obtain only the source permissions needed for your real report. Cloud plans, connected applications, hosting, and model APIs may have separate costs. Choose a supported AI provider if generating prose or AI-assisted transformations; local model memory needs depend on the model. A calculator, spreadsheet formula, or reviewed code can compute this small fixture without an LLM. Store secrets in service credentials, not table cells or prompts.

**Route — four steps.**

1. Define grain: one team-week row, `planned` and `done` as item counts. Check duplicates, missing values, and matching reporting periods.
2. Calculate weekly totals and `100 × sum(done) / sum(planned)` with formulas or code. If planned is zero, mark the rate undefined.
3. Subtract the unrounded previous rate from the unrounded current rate, then round display values to two decimals. Give only checked results to the model for narration.
4. Compare totals with input rows, review wording, and approve the report before any scheduled distribution.

**Try the case.** Select `weekly-report` in [starter-pack.json](../examples/starter-pack.json). Copy its four input rows into a table. W43 has 17/22 completed, or **77.27%**; W44 has 22/27, or **81.48%**. The change is **+4.21 percentage points**. Do not average team rates or call this a 4.21% relative increase. Keep `expected` as the answer key, outside the source table.

```text
Write a short weekly update in Chinese using only the supplied rows and
independently calculated metrics. Show planned, done, completion rate,
formula, and source_row_ids for each week. State the change in percentage
points. Do not calculate by guessing, average team percentages, or invent
reasons for change. Separate observations from questions requiring evidence.
If verified metrics are not provided, request calculation before narration.
```

**Acceptance.**

- All four rows contribute exactly once.
- Totals are W43 22/17 and W44 27/22 (planned/done).
- Rates are 77.27% and 81.48%, with +4.21 percentage points.
- No explanation such as “AI saved time” appears without supporting data.

**Limits.** Automation repeats bad definitions as readily as good ones. Chart labels and model-written explanations can hide denominator mistakes. These four rows establish a change, not its cause, statistical significance, or business impact.

## 中文说明

交付一份能重新计算的周报，写清计划量、完成量、完成率及变化。W43 为 **17÷22＝77.27%**；W44 为 **22÷27＝81.48%**；提升 **4.21 个百分点**。先汇总数量再求比率，不能平均两个团队的百分比。

n8n、Activepieces 适合可视化串接数据、计算与审批；Data Formulator 适合交互分析和图表，可用受支持的自包含桌面包，或自行准备 Python/容器环境；CI 构建产物与带标签发布的可用期限不同。它们不是相互可直接导入的节点。托管、外部应用和模型接口可能各自收费；本地模型要核对硬件。这个小样例完全可以用计算器或电子表格算出数字。

四步依次为核查一团队一周一行、用公式计算、用未四舍五入的比率求差再显示两位小数、人工核对后发布。计划量为零时不要除零。若用模型写文字，只给它已经核算的指标，并使用上方提示词；不要让它猜数字或找一个听起来合理的原因。

样例只取 `inputs` 的四行，不把答案键当数据。验收看四行无重复遗漏、两周总数正确、比率及百分点正确、文字不增造原因。该数据无法证明效率提升来自 AI，也无法证明商业收益。本文是**经文档审阅的概念蓝图，并非端到端验证过的集成**，没有运行定时发送或真实模型步骤。

[English index](../README.md) · [中文目录](../README.zh-CN.md) · [Example guide / 样例说明](../examples/README.md)
