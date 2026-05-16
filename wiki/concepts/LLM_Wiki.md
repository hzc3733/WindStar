---
title: "LLM_Wiki"
type: concept
tags: [知识管理, AI, 双链笔记, Karpathy]
sources: [raw/03-transcripts/2026-05-13-把B站视频转成本地AI知识库！新手也能3分钟上手.md]
last_updated: 2026-05-16
---

## 定义

LLM-Wiki 是由 Andrej Karpathy 提出的知识管理理念，核心思想是利用 Obsidian 作为本地知识库，通过 Web Clipper 抓取视频/网页内容并转化为 Markdown 格式，让 LLM 能够理解并实现知识互联与知识生长。

## 核心理念

1. **视频通过 Web Clipper 抓取**，转化为 Markdown 格式存入 Obsidian Vault
2. **让 LLM 能够理解**笔记内容，实现 AI 可读的知识结构
3. **最终实现知识生长**，通过双链和图谱可视化让知识不断繁衍互联

## 完整工具链

| 组件 | 作用 |
|------|------|
| Obsidian | 本地知识库核心，支持双链笔记与图谱可视化 |
| Local Rest API 插件 | 为外部工具提供读写笔记库的接口 |
| Karpathy-LLM-Wiki-Vault 模板 | 提供标准化的知识管理结构 |
| Bilibili Web Clipper | 抓取B站视频原数据与字幕，打通最后一环 |

## 关联连接
- [[摘要-bilibili-llm-wiki-intro]] — 来源
- [[Obsidian]] — 承载工具
- [[Karpathy_LLM_Wiki_Vault]] — 开源模板
- [[Bilibili_Web_Clipper]] — B站专用抓取工具