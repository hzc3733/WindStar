---
title: "摘要-hermes-agent-gong-ju-shuo-ming-shu"
type: source
tags: [Hermes, 工具, 官方文档]
sources: [raw/01-articles/工具说明书.md]
last_updated: 2026-05-16
---

## 核心摘要

Hermes Agent 是一款多平台 AI Agent，支持 Web 搜索、浏览器自动化、终端管理、文件操作、代码执行、视觉分析、语音合成等 16 大类工具集。通过配置 config.yaml 可连接 Telegram、Discord、Webhook 等平台，实现跨平台任务自动化。文档详细介绍了每个工具的参数、返回值和注意事项，是理解和二次开发 Hermes Agent 的核心参考资料。

## 关键工具分类

| 类别 | 工具 | 说明 |
|------|------|------|
| web | web_search, web_extract | 互联网搜索与内容提取 |
| browser | browser_navigate, browser_snapshot, browser_click 等 | 浏览器自动化 |
| terminal | terminal, process | 终端与进程管理 |
| file | read_file, write_file, patch, search_files | 文件操作 |
| code_execution | execute_code | Python 代码执行 |
| vision | vision_analyze | 图像分析 |
| image_gen | image_gen | 图像生成 |
| tts | text_to_speech | 语音合成 |
| skills | skills_list, skill_view, skill_manage | 技能管理 |
| todo | todo | 任务规划 |
| memory | memory | 持久化记忆 |
| session_search | session_search | 会话搜索 |
| clarify | clarify | 用户交互 |
| delegation | delegate_task | 任务委托 |
| cronjob | cronjob | 定时任务 |
| messaging | send_message | 跨平台消息 |

## 关联连接
- [[Hermes_Agent]] — 工具宿主 Agent
- [[Web_Search]] — 网页搜索工具
- [[Browser_Automation]] — 浏览器自动化
- [[Terminal_Management]] — 终端管理