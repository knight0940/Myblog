---
title: 几个Agent常见范式的思考
date: 2026-04-4
tag: AI-Agent
---

AI Agent 正在成为人工智能领域最热门的话题之一。本文将深入探讨 AI Agent 的范式设计、实现细节以及在实际项目中的应用经验。

## AI Agent有什么常见范式？

AI Agent 最常见的范式主要有3个，分别是ReAct，Reflection，Plan-Solve。他们分别代表了三种不同的思考-执行模式，简单来说：

### ReAct

ReAct是“一边做一边想”，ReAct有两个主要行为和两个主要元素，分别是 Reasoning，Acting和Observation，Environment，如果以一个Code Agent举例，那么代码仓库就是Environment，LLM通过读取当前仓库代码，随后进行Reasoning，那么他观察到的主要特征就可以被称为Observation，根据该Observation， LLM就会做出相应的动作（或工具调用或输出答案，Acting），那么在LLM执行完对应的动作之后，仓库中的代码（Environment）也自然发生了改变，因此又会产生一个新的Observation。 Agent就会在预设好的轮次里不断进行这个循环以得到最终答案。

### Reflection

人在做错（做对）一件事情之后，或多或少都会回想、复盘自己当时的选择，而Reflection就是将这个常见的人类思考习惯引入了Agent。顾名思义，Reflection其实指的就是反思，在Main Agent执行后，用一个Critic Agent（有着与Main Agent不同的提示词模板）对Main Agent的输出，Thinking历史，Tool Call历史进行复盘反思，评估那些做的好，那些做的差，得到对输出的反馈。随后Main Agent的输出和Critic Agent给的反馈会作为Main Agent的新的上下文以得到新的优化后的输出。

### Plan-Solve

对于这个范式，相信经常使用Claude Code（简称cc）的朋友都知道，它就有一个Plan模式，在你和cc不断讨论出一个满意的方案后，就可以让其执行得到输出。那么它主要是由一个Plan Agent和一个 Execute Agent组成，Plan Agent被要求制定详细的计划并拆分成可执行的各个小步骤，而Execute自然则被要求根据Plan来实现最终的方案。

### 小结

这三种范式并不是冲突的范式，恰恰相反，经常可以看到这三种范式被以各种各样的方式组合在一起使用。

## Prompt实现

从这三种不同的

- 感知模块：处理多模态输入（文本、图像、音频等）
- 记忆系统：短期工作记忆和长期知识存储
- 规划引擎：任务分解和执行计划
- 工具使用：调用外部 API 和工具
- 反思机制：评估和优化决策

## 实践案例

在实际项目中，我们构建了一个基于 LLM 的研究助手 Agent，能够自主检索文献、分析数据并生成报告。以下是一些关键经验：

### 1. 提示词工程

精心设计的提示词是 Agent 成功的关键。我们采用结构化提示词，包含角色定义、任务描述、输出格式等。

### 2. 工具调用

通过 Function Calling 让 Agent 能够使用外部工具，大大扩展了其能力边界。

## 未来展望

随着多模态大模型的不断发展，AI Agent 将在更多领域发挥重要作用。从个人助手到企业应用，Agent 时代才刚刚开始。
