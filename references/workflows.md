# Seedance Self Workflows

Use these workflows after classifying the user's request.

## Route A: 5 Seconds Or Less

Use when the user wants a very short clip, a viral moment, or one impossible visual beat.

Goal: one idea, one hook, one transformation or reveal.

Structure:

1. Hook in the first 1-2 seconds.
2. One core visual action.
3. One camera direction.
4. One lighting/material style.
5. One ending beat that invites replay.

Avoid:

- multi-character story
- too many locations
- long emotional arc
- too many props or effects

Output:

```markdown
## 判断
适合做 5 秒短瞬间，因为...

## 完整提示词
[中文 Seedance prompt]

## 自检
- 一个核心事件
- 前 2 秒有 hook
- 无多余剧情
```

## Route B: 6-15 Second Time-Axis Video

Use a 0-5 / 5-10 / 10-15 second time-axis structure.

Default structure:

- 0-5 seconds: setup / visual hook
- 5-10 seconds: development / conflict / transformation
- 10-15 seconds: climax / reveal / replay hook

Include:

- style baseline
- subject lock
- scene lock
- camera movement per segment
- physical interaction
- SFX/dialogue if useful
- negative constraints

Output:

```markdown
## 配置
时长:
比例:
素材:

## 完整提示词
【基础设置】
...

【时间轴详细描述】
00-05秒:
05-10秒:
10-15秒:

【音效/台词】
...

【禁止项】
...
```

## Route C: Image-To-Video

Use when the user uploads or names an image and wants video.

Principle: trust the image for existing visual facts. Text should mainly add what the image cannot provide:

- duration
- aspect ratio
- camera direction
- action rhythm
- emotional hook
- what to avoid
- hard constraints

First output if image details are unknown:

- explain what needs to be inferred from the image
- ask for the mode if needed: `反应`, `凝视`, or `自动判断`

Prompt controls:

- Keep text concise enough for Seedance.
- For most image-to-video prompts, target 300-900 Chinese characters unless the user explicitly needs long segmentation.
- Use `@图片1` style references.

Include risk checks:

- real person face
- watermark/text/UI
- grid lines/storyboard cells
- physical plausibility
- character drift
- background drift

## Route D: 3x3 Storyboard Grid

Use when the source is a nine-grid storyboard, manga storyboard, or the user asks for "按九宫格生成".

First decide:

- D-1: one video with three time bands, usually 0-5 / 5-10 / 10-15 seconds.
- D-2: multiple independent prompts, then edit together.

Use D-1 when:

- the grid is one continuous event
- subject/location/style are consistent
- action can fit within 15 seconds

Use D-2 when:

- more than 4 major scene changes
- multiple locations/styles
- episodic story or complex plot
- continuity would be unreliable in one generation

Always tell the model not to copy:

- grid borders
- panel numbers
- caption boxes
- UI marks
- speech bubbles unless explicitly needed

## Route E: Long Video

Use when the user needs more than 15 seconds.

Seedance single generation should not be treated as a complete long-video solution. Build a pipeline:

1. Concept and audience hook.
2. Character/style/scene bible.
3. Shot list.
4. First-frame or reference images for key shots.
5. Per-shot prompts, usually 5-15 seconds.
6. Editing rhythm.
7. Continuity and color matching.
8. Repair/retry plan.

Output a table:

| Shot | Duration | Visual Event | Camera | Reference | Audio/SFX | Continuity Anchor |

For 45+ seconds, group shots into acts or a 25-cell production map.

## Image Prompt Generation

Use when the user needs first frames, character cards, reference images, or text-to-image prompts before video.

Output:

- aspect ratio
- subject
- setting
- composition
- lighting
- material/detail
- style baseline
- negative constraints

For character reference images:

- prefer full-body front view if later used for animation
- mention stable costume, face, hair, body proportions
- avoid over-stylized camera distortion

For first frames:

- match the intended video aspect ratio
- include a clear starting pose/action
- leave room for motion

## Repair And Critique

Use when the user says the generated result is bad.

Classify the failure:

- prompt too broad
- too many events
- weak first 2 seconds
- subject drift
- background drift
- hand/body deformation
- style mismatch
- camera too complex
- text/watermark copied
- action continuity broken

Then propose the smallest fix:

- simplify one core event
- lock subject/background
- split into multiple shots
- add stronger negative constraints
- use first-frame/reference image
- change route from C/D-1 to D-2

Do not rewrite everything if a targeted patch is enough.
