---
title: "Obsidian"
type: entity
tags: [工具, 知识管理, 双链笔记]
sources: [raw/03-transcripts/2026-05-13-把B站视频转成本地AI知识库！新手也能3分钟上手.md]
last_updated: 2026-05-13
---

## 定义

Obsidian 是一款本地优先的双链笔记软件，以 Markdown 为基础，支持双向链接、知识图谱可视化和插件扩展。作为本地知识库核心，它能够将笔记转化为 LLM 可理解的结构化知识，实现知识互联与知识生长。

## 核心能力

- **双链笔记**：通过 `[[双向链接]]` 连接笔记
- **知识图谱**：可视化笔记间的关联
- **插件生态**：支持 Local REST API、Web Clipper 等扩展
- **本地优先**：数据存储在本地，无云服务依赖

## 工作流中的角色

在 LLM Wiki 工具链中，Obsidian 担任「本地知识库核心」角色：
- 接收 Web Clipper 抓取的 Markdown 文件
- 配合 skills 功能自动构建双向链接
- 生成可被 LLM 理解的知识图谱

## 关联连接

- [[karpathy-llm-wiki-vault]] — Obsidian 知识库模板
- [[Obsidian_Web_Clipper]] — 网页剪藏插件
- [[Bilibili_Web_Clipper]] — B 站专用抓取扩展
