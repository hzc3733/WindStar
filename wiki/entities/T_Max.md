---
title: "T_Max"
type: entity
tags: [终端管理器, 多Agent, 可视化]
sources: [Clippings/Bilibili/2026-05-18-Harness 实践：让 Agent 全自动制作知识讲解视频.md]
last_updated: 2026-05-18
---

## 定义

T-Max是一个开源的终端管理器，可以在一个窗口中同时管理多个终端会话。在Agent Teams中用于可视化每个组员的工作状态。

## 核心功能

**多会话管理**
在一个窗口中同时管理多个终端会话，配合Agent Teams使用。

**Agent可视化**
Agent Teams中每个组员会出现在不同的终端面板，可以同时看到测试员在审核哪里、开发者在开发哪里。

## 在Claude Code中的配置

需要在全局配置中加入环境变量来启用：
```
CLAUDE_AGENT_TEAMS_TMAX=true
```

## 关联连接
- [[Agent_Teams]] — 配合使用的多Agent模式
- [[Claude_Code]] — 集成使用的Agent
- [[摘要-harness实践知识讲解视频]] — 使用场景来源