# Seedance Prompt Patterns

This is the self-contained prompt pattern reference for `seedance-self`.

This repository is the no-material-pack version. It does not include videos, images, spreadsheets, PDFs, paid course files, private case libraries, or any local dataset. The patterns are condensed from publicly available online tutorials, prompt-writing examples, common Seedance/即梦 usage notes, and practical prompt engineering experience.

Use it to write Seedance/即梦/Seedream prompts without depending on any local material folder.

## Condensed 15-Second Video Template

Use this when the user wants a complete 6-15 second video prompt.

```text
【基础设置】
任务类型：[文生视频 / 图生视频 / 多图参考 / 分镜图驱动]
视频时长：[X秒]
画幅比例：[9:16 / 16:9 / 1:1]
风格基调：[主题风格]，[渲染/摄影/画面质感]，[统一色调]。
主体锁定：[主角/物体/场景必须保持一致]

【时间轴详细描述】
00-05秒：
画面内容：[开头视觉 hook，不要缓慢铺垫]
运镜方式：[单一主运镜，避免三轴同时复杂运动]
物理细节：[材质、光影、烟雾、衣摆、水花、碎片等真实反馈]

05-10秒：
画面内容：[核心动作/转折/冲突/变化]
光影特效：[具体光源、颜色、环境反应]
动态细节：[主体与环境的交互]

10-15秒：
画面内容：[高潮/揭示/定格/二刷钩子]
环境反馈：[破坏、回声、余波、气氛变化]
收尾方式：[冲向镜头/背影定格/渐隐/悬念]

【音效/台词】
环境音效：[SFX]
人物台词：[如有，写清角色、语气、台词]

【禁止项】
禁止文字、字幕、水印、LOGO、UI边框、分镜格线、人物变脸、肢体畸变、背景漂移、风格突变。
```

## Condensed 3x3 Storyboard Template

Use this when the user says 九宫格、分镜图、漫画分镜、storyboard.

```text
【环境设定】
[地点]，[时间/天气]，[气氛]，[光影]。

【角色设计】
[主角身份、外观、服装、道具、情绪]。角色外观全程一致。

【九宫格剧情流转】
第一行：起势与铺垫，对应 0-5 秒
Panel 1：[远景/开场]
Panel 2：[推进/特写]
Panel 3：[对峙/触发事件]

第二行：冲突与爆发，对应 5-10 秒
Panel 4：[动作/交锋]
Panel 5：[特效/高潮推进]
Panel 6：[环境反应/破坏]

第三行：结果与余韵，对应 10-15 秒
Panel 7：[宏大全景]
Panel 8：[局部细节]
Panel 9：[收尾定格/二刷钩子]

【转换为视频时的硬约束】
只参考分镜内容，不复制九宫格边框、编号、网格线、文字框、气泡、UI元素。
```

## Image-To-Video Prompt Pattern

For uploaded images, keep the prompt shorter and more directive.

```text
@图片1 作为首帧和主体参考，保持画面中的[主体/服装/场景/色调]一致。
视频时长[X秒]，画幅[比例]。
开头1-2秒直接出现[视觉钩子]，不要缓慢推镜铺垫。
主体进行[具体动作]，动作节奏为[缓慢凝视/突然反应/爆发变化/连续运动]。
镜头[推近/拉远/轻微环绕/固定机位/手持感]，全程只保留一个主运镜方向。
环境产生[光影/烟雾/水花/碎片/风/反射]等真实反馈。
结尾[定格/反转/悬念/呼应开头]。
禁止生成文字、字幕、水印、LOGO、UI边框；禁止人物变脸、肢体畸变、背景漂移、风格突变。
```

## First-Frame / Reference Image Prompt Pattern

Use when the user needs an image before video generation.

```text
画幅比例：[9:16 / 16:9 / 1:1]。
主体：[身份、年龄段如需要、外观、服装、道具]。
场景：[地点、时间、天气、背景层次]。
构图：[全身/半身/特写，主体占比，视角]。
光影：[主光源、色调、阴影、体积光/反射]。
动作预备：[适合后续动起来的起始姿势]。
风格：[写实摄影/电影感/CG渲染/国风/卡通等]。
禁止：文字、水印、LOGO、畸形手、重复肢体、脸部崩坏、过度磨皮、背景杂乱。
```

## Long Video Pipeline

For more than 15 seconds, do not write one giant prompt. Split into shots:

| 镜头 | 时长 | 画面事件 | 运镜 | 参考素材 | 音效/台词 | 连续性锚点 |
|---|---:|---|---|---|---|---|

Recommended process:

1. Write concept and hook.
2. Create character/style/scene bible.
3. Break into 5-15 second shots.
4. Create or choose first frames for key shots.
5. Write one prompt per shot.
6. Add editing rhythm and transitions.
7. Plan repair/retry points.

## Example Category Heuristics

When no local examples are available, use these category patterns:

- 熊猫 / 萌宠: clean subject, simple action, warm humor, readable background, avoid overly complex human-like motion.
- 治愈风景: one strong natural impossible object, soft color contrast, slow but not empty camera motion, atmospheric SFX.
- 人物巨兽: scale contrast, foreground/background depth, low-angle or wide shot, environmental reaction.
- 国风/古风: clear costume silhouette, restrained color palette, mist/lantern/moon/water/cloth movement.
- CG/科幻: precise material behavior, reflection, glow, particles, mechanical motion, no generic "high tech" vagueness.
- 舞蹈/人物动作: full-body reference, simple stable background, clear limb visibility, avoid crowded choreography.

## Disclosure

When the user asks where the method comes from, say briefly:

`这是 seedance-self 自用总结版，基于网上公开资料和常见提示词经验整理，不附带官方资料包或私有案例库。`
