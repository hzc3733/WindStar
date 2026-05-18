---
title: "Agent_Teams"
type: concept
tags: [多Agent, 协作模式, Claude_Code]
sources: [Clippings/Bilibili/2026-05-18-Harness 实践：让 Agent 全自动制作知识讲解视频.md]
last_updated: 2026-05-18
---

## 定义

Agent Teams是Claude Code支持的一种多Agent协作模式，像一个项目小组：一个组长加上几个组员，每个组员都是独立的会话，他们之间可以互相发消息，也可以共享任务列表。

## 与SubAgent的对比

| 模式 | 类比 | 适用场景 | Token开销 |
| --- | --- | --- | --- |
| **SubAgent** | 让三人分别去三个城市办不同事情，办完回来汇报 | 结果导向性任务：并行开发多个章节、一次性检查某段代码 | 比较省token，容易调度 |
| **Agent Teams** | 把三人拉进同一间会议室，边讨论边改方案 | 需要来回反馈的任务：如质检环节，测试看到代码发现问题，开发再改，改完测试复查 | 更高，每个组员都是完整会话 |

## 核心特点

- 组员之间可以互相讨论
- 可以共享任务列表
- 适合需要来回反馈的复杂任务
- 配合T-Max可以在不同终端面板可视化每个组员的工作状态

## 配置要求

需要在Claude Code全局配置中加上环境变量：
```
CLAUDE_AGENT_TEAMS_TMAX=true
```

## 关联连接
- [[SubAgent]] — 另一种多Agent模式
- [[T_Max]] — 配合使用的终端管理器
- [[Harness]] — 多Agent属于Harness的编排层
- [[摘要-harness实践知识讲解视频]] — 使用场景来源