---
title: "摘要-harness实践知识讲解视频"
type: source
tags: [Harness, Agent, 视频生成, Claude_Code, Skill]
sources: [Clippings/Bilibili/2026-05-18-Harness 实践：让 Agent 全自动制作知识讲解视频.md]
last_updated: 2026-05-18
---

## 核心摘要

本文是"code秘密花园"作者的Harness实践教程，演示如何用Agent全自动制作知识讲解视频。核心观点：视频效果不是用视频生成模型做的，而是一个由Agent用web coding生成的网页，通过录屏产出视频。

**关键发现：Harness的本质是驾驭过程而非使用能力**
模型本身能写代码、能生成，但真正的挑战是：怎么让每次都能稳定产出？怎么让不同人、不同文章、不同主题都能稳定？答案是一套机制：划定边界、设定检查点、自检和修复。

**Skill设计核心要素（6个部分）**
1. 执行和编排：让模型知道下一步该做什么
2. 状态和记忆：跨步骤保持连续性和稳定性
3. 工具系统：模型能做什么
4. 约束和恢复：出错了怎么办
5. 评估和观测：怎么知道做的对不对
6. 约束和恢复：处理反馈的方式

**视频生成四阶段流程**
阶段一：内容编写（产出口播稿+开发计划）→ 人工检查点 → 阶段二：章节开发（逐章验收，并行开发）→ 人工检查点 → 阶段三：音频合成（TTS） → 阶段四：录屏产出视频

**关键技术组件**
- Claude Code/MiniMax：核心执行Agent
- CC Switch：模型切换工具
- T-Max：终端管理器，多Agent可视化
- Garden Skills：Skill开源仓库

## 关联连接
- [[Harness]] — 驾驭工程的核心概念
- [[Claude_Code]] — 核心执行Agent
- [[Skills]] — Skill设计方法
- [[Agent_Teams]] — 多Agent协作模式
- [[Web_Video_Presentation]] — 具体Skill实现