---
title: "MCP"
type: concept
tags: [Anthropic, 协议, 工具扩展]
sources: [Clippings/Bilibili/AI工具/保姆级Claude Code速成.md]
last_updated: 2026-05-16
---

## 定义
MCP（Model Context Protocol，模型上下文协议）是Anthropic发明的协议标准，用于让AI工具（如Claude Code）连接外部工具和服务的接口。MCP可以理解为Claude Code去连接外部工具的一个桥梁。

## 关键信息

### 核心功能
- **工具扩展**：MCP Market等网站提供大量MCP扩展
- **标准化接口**：统一了AI工具与外部服务的连接方式
- **按需安装**：用户可以根据需要安装不同功能的MCP

### 常见MCP
- **Playwright MCP**：控制浏览器自动化操作
- **文件系统MCP**：读写本地文件
- **Git MCP**：版本控制操作

### 安装方式
在Claude Code中可以通过命令直接安装MCP，安装后按下斜杠`/`可以查看所有已安装的MCP。

### 与Skills的区别
- **MCP**：连接外部工具的接口/桥梁
- **Skills**：给Claude Code装的现成能力包，既能连接外部服务，又预设了大量提示词指导AI完成特定工作

## 关联连接
- [[Claude_Code]] — MCP的载体工具
- [[Skills]] — 另一个扩展机制
- [[MCP_Market]] — MCP扩展市场