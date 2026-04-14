# Resume Rewrite Skill

一个 Claude Skill，专门帮助 **Data Engineering** 求职者改写、诊断和优化简历 bullet points，让你的简历更突出成就、更符合 HR 阅读习惯、更容易通过 ATS 筛选。

## 功能

- **改简历模式** — 粘贴你现有的简历 bullet，输出三列诊断表（原文 | 问题 | 推荐写法），逐条改写
- **大白话模式** — 用中文口语描述你做了什么，自动生成专业的英文 bullet points
- **JD 匹配模式** — 上传职位描述，对比你的简历，输出关键词覆盖率报告和调整建议
- **面试押题模式** — 基于定稿简历，生成 Thinking Process 故事骨架和四轮面试追问（HR、技术深挖、System Design、Leadership）

## 下载

```bash
git clone https://github.com/xiaowantree/resume-rewrite-skill.git
```

## 使用方式

### Claude Code（CLI / 桌面版 / IDE 插件）

通过命令行安装，安装后 Skill 永久生效，自动触发，无需每次手动上传：

```bash
claude install-skill SKILL.md
```

### Claude 网页版（claude.ai）

网页版不支持安装 Skill，但可以通过上传文件实现相同效果：

1. 打开 [claude.ai](https://claude.ai)，开始一个新对话
2. 点击输入框左侧的 **附件按钮**（回形针图标）
3. 上传 `SKILL.md` 文件
4. 直接开始对话，例如输入「帮我改简历」，然后粘贴你的 bullet points

> 注意：网页版每次新对话都需要重新上传 SKILL.md。如果需要面试押题功能，还需一并上传 `references/interview-prep.md`。

## 触发方式

上传或安装后，当你在对话中做以下操作时，Skill 会自动激活：

- 粘贴简历 bullet points 或描述工作经历
- 说「帮我改简历」「帮我写简历」「帮我看看这个JD」「帮我押题」「准备面试」等
- 上传或粘贴一段职位描述（Job Description）

## 文件结构

```
resume-rewrite-skill/
├── SKILL.md                      ← 核心逻辑：入口路由、诊断规则、改写规则、输出格式
└── references/
    ├── terminology.md            ← HR 高频动词、术语翻译对照表、ATS 关键词清单
    └── interview-prep.md         ← Thinking Process 故事框架、场景化面试出题模板
```
