---
title: "OpenClaw"
type: entity
tags: [Agent框架, 多智能体, OpenClaw]
sources: [Clippings/OpenClaw 多 Agent 配置完整指南.md]
last_updated: 2026-05-18
---

## 定义

OpenClaw是一个多智能体（Multi-Agent）框架，用于配置和管理多个独立的AI Agent，实现不同用途、不同人格和不同渠道的隔离使用。

## 核心架构

| 组件 | 说明 | 位置 |
| --- | --- | --- |
| 工作区 | 文件、笔记、人设文件 | `~/.openclaw/workspace-<id>/` |
| 状态目录 | 认证配置、模型注册 | `~/.openclaw/agents/<id>/agent/` |
| 会话存储 | 聊天历史、路由状态 | `~/.openclaw/agents/<id>/sessions/` |
| 主配置 | 全局配置与Agent列表 | `~/.openclaw/openclaw.json` |

## 核心概念

### Agent（智能体）
每个Agent是完全独立的"大脑"，拥有独立的工作区、状态目录和会话存储。

### 多Agent用途
- **多人共用**：不同用户使用不同的Agent，数据隔离
- **工作/生活分离**：工作Agent和个人Agent分开
- **不同人格**：通过SOUL.md定义不同的性格
- **不同模型**：不同Agent使用不同的AI模型
- **渠道隔离**：Telegram用Agent A，WhatsApp用Agent B

### 路由绑定（Bindings）
通过优先级规则决定消息路由到哪个Agent：
1. peer精确匹配（私信/群组ID）
2. guildId（Discord服务器）
3. teamId（Slack团队）
4. accountId（渠道账户）
5. 渠道级匹配
6. 默认Agent

### 沙箱隔离
可配置Agent的沙箱模式：
- `off`：无沙箱
- `all`：始终沙箱，每智能体一个容器

## 关联连接
- [[摘要-openclaw多agent配置]] — 配置指南来源
- [[多Agent架构]] — 多智能体协同设计理念
- [[路由绑定]] — 消息路由机制