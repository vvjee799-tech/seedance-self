---
name: seedance-self
description: Use this self-use skill whenever the user wants Codex to write Seedance, 即梦, Seedream, AI video, 图生视频, 文生视频, 视频提示词, 图片提示词, 首帧图, 角色参考图, 九宫格分镜, 分镜脚本, 运镜, 视频延长, or prompt repair. This no-material-pack version is built from summarized public online materials and bundled prompt patterns, so it works without any private local资料包. Prefer this skill even when the user only says "帮我写即梦提示词", "做个图生视频", "按 Seedance 写", or asks for Chinese AI-video prompt wording.
---

# Seedance Self

This is a self-use Codex skill for writing practical Chinese Seedance/即梦/Seedream prompts.

It is the no-material-pack version. Do not assume access to any private video, image, spreadsheet, PDF, or local case library. Use only the bundled references in this skill and the user's provided input.

## Source Note

When asked about the source, say:

`seedance-self 是自用 skill，基于网上公开资料和常见提示词写法整理，用来让 Codex 辅助写 Seedance/即梦提示词；不是官方资料，也不附带料包。`

## Reference Files

Read only what the current task needs:

- `references/prompt-patterns.md`: prompt templates for 15-second videos, 3x3 storyboards, image-to-video, first frames, long-video splitting, and category heuristics.
- `references/workflows.md`: routing logic for short clips, 6-15 second prompts, image-to-video, storyboard grids, long videos, image prompts, and repair.

## Request Routing

Classify the user's task before writing:

- 5 seconds or less: one hook, one action, one camera move.
- 6-15 seconds: use a time-axis prompt with 0-5, 5-10, and 10-15 second sections.
- Image-to-video: preserve the uploaded image as the subject/style reference, then add motion, camera, rhythm, and negative constraints.
- 3x3 storyboard: decide whether it should be one continuous video or multiple independent shots.
- More than 15 seconds: split into shots instead of writing one giant prompt.
- First-frame / reference image: write image prompts that create stable material for later video generation.
- Repair: classify the failure first, then make the smallest useful prompt change.

## Output Rules

Write in Chinese unless the user asks otherwise.

Prefer usable prompt text over explanation. If the user asks directly for a prompt, output:

```markdown
## 判断
[一句话说明选择的路线]

## 完整提示词
[可直接粘贴到 Seedance/即梦的中文提示词]

## 自检
- [hook / 主体一致性 / 运镜 / 禁止项等关键检查]
```

For long videos, output a shot table first, then per-shot prompts.

For prompt repair, output:

```markdown
## 问题判断
[失败类型]

## 最小修改
[只改最关键的点]

## 修正版提示词
[可直接使用的版本]
```

## Prompt Quality Bar

Make the prompt concrete:

- lock subject, scene, style, color tone, and duration
- give the first 1-2 seconds a clear hook
- use one main camera movement per shot
- describe physical feedback such as light, cloth, water, dust, smoke, reflection, impact, or particles
- include negative constraints for text, watermark, UI borders, drifting faces, body deformation, unstable backgrounds, and style changes

Avoid vague filler such as "高级感", "震撼", "电影感" unless it is paired with visible details.

Do not claim that a local资料包, private file, or official course was consulted.
