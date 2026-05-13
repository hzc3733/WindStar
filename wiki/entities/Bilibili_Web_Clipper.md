---
title: "Bilibili_Web_Clipper"
type: entity
tags: [工具, 浏览器扩展, Bilibili, 知识管理]
sources: [raw/03-transcripts/2026-05-13-把B站视频转成本地AI知识库！新手也能3分钟上手.md]
last_updated: 2026-05-13
---

## 定义

Bilibili Web Clipper（哔哩哔哩网页剪藏器）是由 B 站 up 主「小陈师傅 cz」开发的浏览器扩展，专为 B 站视频定制的抓取工具。它能够一键将 B 站视频转化为结构化笔记，自动提取标题、up 主、字幕和简介，生成标准 Markdown 文件并保存至 Obsidian 知识库，打通了 B 站学习资源到本地 AI 知识库的最后一环。

## 核心功能

- **一键抓取**：提取 B 站视频的标题、up 主、字幕、简介
- **Markdown 导出**：生成标准 Markdown 格式文件
- **目录配置**：支持自定义保存路径（如 `raw/03-transcripts/`）
- **多浏览器支持**：Chrome、Edge（Chromium 内核）、Firefox

## 技术背景

B 站视频与 YouTube 采用不同的播放器与页面结构，通用 Obsidian Web Clipper 无法正确解析。Bilibili Web Clipper 解决了三个主要困境：
1. **平台差异**：B 站特有的播放器与页面结构
2. **字幕格式**：B 站字幕格式与 YouTube 不同，需专门解析
3. **特有数据**：B 站特有的 BVID 等数据需单独处理

## 关联连接

- [[Obsidian]] — 本地知识库核心
- [[karpathy-llm-wiki-vault]] — 知识库模板
- [[摘要-bilibili-ai-knowledge-base]] — 来源视频摘要
