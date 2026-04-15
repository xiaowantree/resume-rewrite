# Data Engineer Resume Copilot

一个 Claude Code Skill，帮 **Data Engineering** 求职者把简历从"职责描述"改写成"成就导向"，同时提供 JD 匹配和面试押题。

## 这个 Skill 能做什么

专为 DE 方向求职者打造的简历辅导工具，不需要你懂 HR 套路，也不需要纠结中英文表达 —— 粘贴原文或大白话描述即可。

### 主要功能

- **改简历（Diagnose Mode）** — 粘贴现有 bullets，输出三列诊断表（原文 | 问题 | 推荐写法），逐条改写
- **大白话转简历（Raw Input Mode）** — 用中文口语描述你做了什么，自动生成专业英文 bullets
- **JD 匹配（JD Match Mode）** — 对比你的简历和目标岗位，输出关键词覆盖率和调整建议
- **面试押题（Interview Prep Mode）** — 基于定稿简历，生成 Thinking Process 故事骨架和四轮追问（HR、技术深挖、System Design、Leadership）

## 安装

### Claude Code（推荐）

直接 clone 到 Claude Code 的 skills 目录：

```bash
git clone https://github.com/xiaowantree/data-engineer-resume-copilot.git ~/.claude/skills/resume-rewrite
```

重启 Claude Code 后，Skill 会自动识别并根据你的输入自动触发。

### 手动安装

如果已经 clone 到别的地方，把整个目录复制到 skills 目录即可：

```bash
# 进入已 clone 的目录所在位置
cp -r resume-rewrite ~/.claude/skills/
```

确认安装成功：

```bash
ls ~/.claude/skills/resume-rewrite/
# 应该看到：SKILL.md  references/
```

## 使用

安装后直接在 Claude Code 中用自然语言触发，不需要输入任何命令。

### 改简历

```
> 帮我改简历
> [粘贴你的 bullet points]
```

Skill 会：
1. 逐条诊断，输出三列诊断表
2. 总结共性问题（动词重复、缺量化等）
3. 追问业务价值和具体数字
4. 输出 paste-ready 的最终英文版本

### 大白话描述

```
> 我去年主要在做ETL，处理了几百万条数据，用的Python和Airflow
```

Skill 会拆分你描述的工作线条，一条一条帮你补细节，生成专业 bullets。

### JD 匹配

```
> 帮我看看这个JD match吗
> [粘贴职位描述]
```

Skill 会输出关键词覆盖表、逐条 bullet 对齐度、以及三类行动建议（措辞调整 / 关键词补充 / bullet 替换）。

### 面试押题

简历定稿后：

```
> 帮我押题
```

Skill 会挑 3-5 条最可能被问到的 bullets，为每条生成 Thinking Process 骨架 + 四轮面试追问表。

## 文件结构

```
resume-rewrite/
├── README.md                    ← 本文档
├── SKILL.md                     ← 核心逻辑（入口路由、诊断规则、改写规则）
└── references/
    ├── terminology.md           ← HR 动词、术语翻译表、ATS 关键词清单
    └── interview-prep.md        ← 面试押题的故事框架和出题模板
```

| 文件 | 何时被加载 |
|---|---|
| `SKILL.md` | Skill 被触发时自动加载 |
| `references/terminology.md` | 诊断或改写 bullets 时按需加载 |
| `references/interview-prep.md` | 用户要求面试押题时按需加载 |

## 设计理念

1. **简历写的是"成就"，不是"职责"** — 每条 bullet 必须有 action、method、result、business outcome 四要素
2. **量化是底线** — 每条至少一个数字，没有数字就用合理的占位符提醒补充
3. **HR 友好 > 技术炫技** — `idempotent upserts` 不如 `data integrity controls`
4. **面试不靠 STAR，靠 Thinking Process** — 真正打动人的是你怎么思考、怎么权衡、踩过什么坑

## 联系作者

- 小红书：[小万来咯](https://www.xiaohongshu.com/user/profile/11882426419)
- 网站：[xiaowantree.com](https://xiaowantree.com)
- 微信：qgm226131
