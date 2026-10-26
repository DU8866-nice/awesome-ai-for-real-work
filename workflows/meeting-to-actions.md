# Meeting → action register / 会议变行动清单

**Status:** documentation-reviewed blueprint, not an end-to-end tested integration. This is a conceptual route, not an importable native workflow. The original synthetic case and its expected register are author-defined, not actual AI output.

## English

**Deliverable.** An action register separating explicit commitments from suggestions, with owners, deadlines, and transcript references only where evidence exists.

**Choose a starting tool.** [Meetily](https://github.com/Zackriya-Solutions/meetily) provides meeting capture, transcription, and summaries through packaged Windows/macOS desktop applications; Linux uses a source build. [faster-whisper](https://github.com/SYSTRAN/faster-whisper) is a Python transcription library for a developer-managed audio pipeline. [WhisperX](https://github.com/m-bain/whisperX) adds word alignment and optional speaker diarization. They are alternative starting points; this page does not promise an automatic chain between all three.

**Prepare.** For real recordings, obtain the required recording permission and choose microphone/system audio inputs. Download a transcription model. CPU execution is available in the transcription libraries; larger models and GPU acceleration need compatible dependencies and more memory. Meetily summaries require a selected local or cloud model provider; remote summary APIs can incur fees and transmit transcript text. WhisperX diarization can require a Hugging Face read token, model download, and acceptance of the model's conditions. Speaker labels are clusters, not verified real identities.

**Route — four steps.**

1. Capture or import an authorized recording, keeping its date and timezone; begin with a short excerpt.
2. Transcribe, then listen back to names, negations, and deadlines. Keep segment IDs or timestamps; verify any person-to-speaker mapping manually.
3. Extract commitments separately from proposals using the template. Leave absent owners and dates `null`.
4. Review each row against the transcript. Share or create tasks only after a human accepts the register.

**Try the case.** Select `meeting-to-actions` in [starter-pack.json](../examples/starter-pack.json). Feed `inputs`, which contains a fictional transcript with stable segment IDs and fixture-defined speaker names. There is no audio file: this checks action extraction, not speech recognition, speaker identification, or desktop capture. Compare with `expected` after generating a result.

```text
Read the supplied transcript and return JSON with committed_actions and
proposals. Each row needs action, owner, due_date, and source_segment_ids.
Only explicit personal commitments belong in committed_actions.
Keep suggestions separate; never infer an owner or deadline from a nearby
speaker or the meeting date. Use null for missing fields. Do not schedule,
send messages, or create tasks. Explain uncertainties in Chinese.
```

**Acceptance.**

- The two commitments retain Mira/2026-10-21 and Jun/2026-10-22.
- The dashboard remains a proposal with owner and deadline both `null`.
- Every row cites its supporting transcript segment.
- Extraction alone sends or schedules no task.

**Limits.** Overlapping speech, accents, and proper names can corrupt the transcript. Alignment does not prove a sentence was recognized correctly. Diarization can merge or split speakers. Summary quality and available exports differ by product edition; do not assume a README's planned feature is already available.

## 中文说明

交付能直接复核的行动清单，分开“明确承诺”和“仅作建议”。Mira 承诺在 2026-10-21 前发清单，Jun 承诺在 2026-10-22 前验证样本；仪表盘只是提议，负责人及期限都必须为空。

Meetily 在 Windows/macOS 有桌面安装包，Linux 要源码构建。faster-whisper 是 Python 库；WhisperX 适合需要词级对齐或说话人分离的开发者。先准备录音许可、模型下载和硬件；远程摘要接口另有费用及数据传输。WhisperX 的分离模型可能要求下载令牌及同意使用条件。`SPEAKER_00` 等标签不等于真实姓名。

操作依次为录音或导入、回听修订、抽取承诺与提议、人工确认。姓名、否定句和日期需重点回听。上方提示词可输出 JSON 并用中文解释不确定项。样例仅含虚构文字稿，复制 `inputs` 即可，不需要录音或 API 来阅读；真正模型步骤仍须自己运行。

验收包括两项承诺的责任人和日期准确、提议不被强配责任、每项保留原句编号、抽取后不自动发送任务。文字稿有误会传递到行动表；时间对齐和说话人分离均不能代替人工判断。本文是**经文档审阅的概念蓝图，并非端到端验证过的集成**，没有声称实际跑过这些工具。

[English index](../README.md) · [中文目录](../README.zh-CN.md) · [Example guide / 样例说明](../examples/README.md)
