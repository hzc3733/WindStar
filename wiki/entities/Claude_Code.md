---
title: "Claude Code"
type: entity
tags: [Anthropic, AI工具, Agent, 开发工具]
sources: [Clippings/Bilibili/AI工具/保姆级Claude Code速成.md]
last_updated: 2026-05-16
---

## 定义
Claude Code是Anthropic公司开发的AI编程与通用Agent工具，本质上是一个Harness（驾驭大模型的外壳），通过反复调用底层大模型几十上百次来完成复杂任务。

## 关键信息

### 核心特性
- **通用Agent能力**：不仅限于编程，可用于自动化、浏览器控制、Skill开发、PPT制作、飞书操作、视频剪辑等
- **Harness架构**：Claude Code、Open Claude、Hermes Agent等产品本质都是驾驭大模型的方式，负责调度背后的模型和思考过程
- **多模型支持**：可以配置使用国产模型（如KIMI K2.6），国内网络可直接使用

### 国内安装与配置
- 安装命令通过PowerShell以管理员身份运行
- 国内网络环境可直接安装使用
- 配置国产模型只需添加API Key和模型参数

### MCP扩展
- MCP（Model Context Protocol）是Claude Code连接外部工具的接口
- 通过MCP Market可以安装多种扩展
- Playwright MCP可实现浏览器自动化控制

### 上下文管理
- Context Compact：上下文占用过高时自动总结释放
- 建议手动在完成阶段性任务后主动Compact
- 重要信息应让AI直接写入文件成为永久记忆

### 权限模式
- 默认模式：每条命令都需要用户批准
- Bypass Permissions：绝大部分命令不再需要批准（最激进模式）

## 关联连接
- [[Harness]] — AI驾驭层概念
- [[MCP]] — 模型上下文协议
- [[Skills]] — 技能扩展机制
- [[上下文管理]] — 上下文腐烂与Compact机制
- [[摘要-claude-code-speedrun]] — 来源摘要