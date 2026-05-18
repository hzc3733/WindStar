---
title: "SubAgent"
type: concept
tags: [多Agent, 协作模式, Claude_Code]
sources: [Clippings/Bilibili/2026-05-18-Harness 实践：让 Agent 全自动制作知识讲解视频.md]
last_updated: 2026-05-18
---

## 定义

SubAgent是Claude Code的一种多Agent协作模式，像一个紫禁城主Agent把一个任务分出去，子Agent在自己的完全独立的上下文里面完成，然后再把结果交回来。

## 核心特点

- 各个子Agent之间互相看不到
- 也不会互相讨论
- 适合结果导向性任务
- 比较省token，也容易调度

## 典型应用场景

- 并行开发多个章节
- 一次性检查某段代码
- 让三个SubAgent分别编写三个章节，最后主Agent回收所有结果

## 与Agent_Teams的对比

| 模式 | 特点 | 适用场景 |
| --- | --- | --- |
| **SubAgent** | 独立上下文，不互相讨论，结果导向 | 并行开发、代码检查 |
| **Agent Teams** | 可以互相讨论，共享任务列表，过程导向 | 质检等需要来回反馈的任务 |

## 关联连接
- [[Agent_Teams]] — 另一种多Agent模式
- [[Harness]] — 多Agent属于Harness的编排层
- [[摘要-harness实践知识讲解视频]] — 使用场景来源