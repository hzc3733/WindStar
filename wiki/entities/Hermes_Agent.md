---
title: "Hermes_Agent"
type: entity
tags: [AI-Agent, 多平台, 工具集]
sources: [raw/01-articles/工具说明书.md, raw/01-articles/技能使用说明书.md]
last_updated: 2026-05-16
---

## 定义

Hermes Agent 是一款多平台 AI Agent 框架，通过模块化工具集实现跨平台任务自动化。支持 Web 搜索、浏览器自动化、终端管理、文件操作、代码执行等 16 大类工具，以及 80 个可扩展技能。

## 核心能力

### 16 大工具集

| 类别 | 工具数 | 代表工具 |
|------|--------|---------|
| web | 2 | web_search, web_extract |
| browser | 9+ | browser_navigate, browser_click |
| terminal | 2 | terminal, process |
| file | 4 | read_file, write_file, patch |
| code_execution | 1 | execute_code |
| vision | 1 | vision_analyze |
| image_gen | 1 | image_gen |
| tts | 1 | text_to_speech |
| skills | 3 | skills_list, skill_view, skill_manage |
| todo | 1 | todo |
| memory | 1 | memory |
| session_search | 1 | session_search |
| clarify | 1 | clarify |
| delegation | 1 | delegate_task |
| cronjob | 1 | cronjob |
| messaging | 1 | send_message |

### 80 个技能（17 个分类）

覆盖 autonomous-ai-agents、creative、data-science、devops、email、gaming、github、mcp、media、mlops、note-taking、productivity、red-teaming、research、smart-home、social-media、software-development 等领域。

## 平台支持

通过 config.yaml 配置，可连接 Telegram、Discord、Webhook 等平台，实现跨平台消息收发和任务触发。

## 关联连接
- [[摘要-hermes-agent-gong-ju-shuo-ming-shu]] — 工具文档
- [[摘要-hermes-agent-ji-neng-shi-yong-shuo-ming-shu]] — 技能文档
- [[Claude_Code]] — 集成的 AI 编程 Agent
- [[vLLM]] — 集成的 LLM 推理服务