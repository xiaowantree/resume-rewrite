# Interview Prep — 押题与故事准备

当用户说"帮我押题"、"准备面试"、"深挖一下简历"时，加载此文件。

基于用户定稿后的简历 bullet points，生成面试追问和故事骨架，帮用户提前准备。

---

## Part 1: Thinking Process 骨架

STAR 框架过于模板化。面试中真正打动人的是 **思考过程** — 你怎么发现问题、怎么分析、为什么做这个决策、踩了什么坑。

对每条值得深挖的 bullet，生成以下骨架，让用户往里填 1-2 句话：

### 骨架模板

```
📌 Bullet: [引用简历原文]

1. 触发点 — 当时遇到了什么问题？什么东西坏了 / 不够用了 / 有人提了新需求？
   → [用户填写]

2. 诊断 — 你怎么定位问题的？看了什么数据？问了谁？做了什么调研？
   → [用户填写]

3. 方案选项 — 你考虑过哪些方案？（至少列两个）
   → 方案A: [用户填写]
   → 方案B: [用户填写]
   → (方案C: ...)

4. 决策 — 为什么选了最终方案？trade-off 是什么？放弃的方案差在哪？
   → [用户填写]

5. 执行中的坑 — 过程中有没有意外？怎么解决的？
   → [用户填写]

6. 结果 — 量化结果（对应简历上的数字）
   → [用户填写]

7. 复盘 — 如果重来一次，你会做什么不同？学到了什么？
   → [用户填写]
```

### 骨架使用规则

- 不是每条 bullet 都需要骨架。优先挑这几类：
  - 有量化结果的（面试官最爱追问"这个数字怎么来的"）
  - 涉及架构决策或技术选型的（"为什么选 X 不选 Y"）
  - 涉及跨团队协作的（behavioral 问题的素材）
  - 简历上最突出/最亮眼的那条（大概率被问到）
- 一份简历通常准备 3-5 个骨架就够了，不要贪多
- 骨架里的第 3 步（方案选项）和第 5 步（坑）是最容易被忽略的，也是面试中最加分的——重点提醒用户填好这两步

---

## Part 2: 场景化出题

对每条被选中的 bullet，按四种面试轮次生成不同角度的追问：

### 四种轮次 & 出题风格

#### HR / Behavioral
问法核心："Tell me about a time when..."
关注点：合作、冲突、优先级、失败、学习
出题模板：
- "Tell me about a time you had to push back on a stakeholder's request. What happened?"
- "Describe a situation where you had to make a trade-off between speed and quality."
- "How did you handle a disagreement with a teammate about [技术决策]?"

#### 技术深挖
问法核心："Walk me through how..."
关注点：实现细节、debug 过程、性能优化、数据质量
出题模板：
- "Walk me through how you built [具体pipeline/系统]. What were the key design decisions?"
- "You mentioned [X]% improvement — how did you measure that? What was the baseline?"
- "What was the hardest bug you encountered in this project? How did you debug it?"
- "How did you handle data quality / schema changes / late-arriving data?"

#### System Design 延伸
问法核心："How would you scale / redesign..."
关注点：扩展性、容错、如果条件变了怎么办
出题模板：
- "If the data volume grew 10x, what would break first? How would you redesign it?"
- "If this needed to be real-time instead of batch, what would change?"
- "How would you make this system fault-tolerant / highly available?"
- "If you had to rebuild this from scratch today, what would you do differently?"

#### Leadership / Influence
问法核心："How did you convince / influence / lead..."
关注点：推动决策、带人、跨团队影响力
出题模板：
- "How did you convince the team to adopt [新工具/方案]?"
- "How did you onboard other engineers onto this system?"
- "How did you prioritize when multiple teams needed your help?"

### 出题规则

- 每条 bullet 出 4 个问题，每种轮次各一个
- 问题必须具体到 bullet 的内容，不能是万能通用问题
- 如果某条 bullet 明显不适合某种轮次（比如纯个人技术活不涉及 leadership），跳过该轮次，用其他轮次补一个
- 标注哪些问题是 **高概率被问到的**（用 ⭐ 标记），帮用户优先准备

---

## 输出格式

### 整体输出结构

对用户选出的每条 bullet，输出两部分：

**A) Thinking Process 骨架**（让用户填写）

**B) 场景化追问表**

| 轮次 | 追问问题 | 优先级 |
|---|---|---|
| HR/Behavioral | [具体问题] | ⭐ |
| 技术深挖 | [具体问题] | ⭐ |
| System Design | [具体问题] | |
| Leadership | [具体问题] | |

### 输出结尾

提醒用户：
- 骨架里第 3 步（方案选项）和第 5 步（执行中的坑）最容易被忽略，也最加分
- ⭐ 标记的题目优先准备
- 准备好骨架后可以回来让我帮你模拟追问
