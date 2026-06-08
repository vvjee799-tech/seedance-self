# seedance-self

自用 Codex skill：搜集网上资料进行总结的、让 Codex 写 Seedance/即梦/Seedream 提示词的 skill。

这是无料包版本。不包含视频、图片、表格、PDF、课程文件、私有案例库或任何本地资料包；只包含可分享的提示词模板、工作流和测试样例。非官方，仅供自用参考。

## 能做什么

- 写 Seedance/即梦中文视频提示词
- 写图生视频、文生视频、多图参考提示词
- 写首帧图、角色参考图、九宫格分镜提示词
- 把长视频拆成镜头表和逐镜头提示词
- 修复提示词问题，比如主体漂移、变脸、运镜太复杂、开头无 hook

## 安装

把整个 `seedance-self` 文件夹放到你的 Codex skills 目录里：

```text
C:\Users\<你的用户名>\.codex\skills\seedance-self
```

重启 Codex 或开启新会话后，就可以用下面这些说法触发：

```text
帮我写一个即梦图生视频提示词
按 Seedance 写一个 15 秒短片
这张图怎么做成视频
写一个九宫格分镜提示词
修一下这个 Seedance 提示词
```

## 文件结构

```text
seedance-self/
├── SKILL.md
├── README.md
├── references/
│   ├── prompt-patterns.md
│   └── workflows.md
└── evals/
    └── evals.json
```

## 说明

本 skill 是自用总结版，基于网上公开资料和常见提示词经验整理，用于让 Codex 更稳定地写 Seedance/即梦提示词。它不是 ByteDance、即梦、Seedance 或 Seedream 的官方资料。
