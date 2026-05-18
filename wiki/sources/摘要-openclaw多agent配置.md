---
title: "摘要-openclaw多agent配置"
type: source
tags: [OpenClaw, Agent, 多智能体, 配置指南]
sources: [Clippings/OpenClaw 多 Agent 配置完整指南.md]
last_updated: 2026-05-18
---

## 核心摘要

本文详细说明如何在OpenClaw中配置多个独立的Agent（智能体），实现不同用途、不同人格、不同渠道的隔离使用。

**多Agent的核心用途**
- 多人共用：不同用户使用不同Agent，数据隔离
- 工作/生活分离：工作Agent和个人Agent分开
- 不同人格：通过SOUL.md定义不同性格
- 不同模型：不同Agent使用不同AI模型
- 渠道隔离：Telegram用Agent A，WhatsApp用Agent B

**配置方法**
方法一使用向导添加（`openclaw agents add <agent-id>`），方法二手动配置（推荐）需创建工作区目录、Agent状态目录，复制认证配置，编辑主配置文件添加agents.list，最后重启Gateway。

**路由绑定规则**
优先级：peer精确匹配 > guildId > teamId > accountId > 渠道级 > 默认Agent。bindings配置决定消息路由到哪个Agent。

**进阶配置**
- 不同模型：为不同Agent设置不同AI模型
- 沙箱隔离：mode可设置为off/all，每Agent一个容器
- 工具权限：通过allow/deny控制工具访问
- Agent间通信：开启agentToAgent功能

## 关联连接
- [[OpenClaw]] — Agent框架本体
- [[多Agent架构]] — 多智能体协同设计理念
- [[路由绑定]] — 消息路由机制
- [[沙箱隔离]] — 安全隔离机制