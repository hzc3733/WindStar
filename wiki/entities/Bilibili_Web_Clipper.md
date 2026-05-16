---
title: "Bilibili_Web_Clipper"
type: entity
tags: [浏览器扩展, B站, 内容抓取]
sources: [raw/03-transcripts/2026-05-13-把B站视频转成本地AI知识库！新手也能3分钟上手.md]
last_updated: 2026-05-16
---

## 定义

Bilibili Web Clipper 是由B站up主小陈师傅（c_z）开发的浏览器扩展，专为B站视频定制的 Web Clipper 工具，可一键将B站视频转化为结构化 Markdown 笔记，打通了B站学习资源到本地AI知识库的最后一环。

## 核心功能

- **一键抓取**：提取 B站视频的标题、up主、字幕、简介
- **Markdown 导出**：生成标准 Markdown 格式文件
- **目录配置**：支持自定义保存路径（如 `raw/03-transcripts/`）
- **多浏览器支持**：Chrome、Edge（Chromium 内核）、Firefox

## 技术背景

B 站视频与 YouTube 采用不同的播放器与页面结构，通用 Obsidian Web Clipper 无法正确解析。Bilibili Web Clipper 解决了三个主要困境：
1. **平台差异**：B站特有的播放器与页面结构
2. **字幕格式**：B站字幕格式与YouTube不同，需专门解析
3. **特有数据**：B站特有的 BVID 等数据需单独处理

## 关联连接
- [[摘要-bilibili-llm-wiki-intro]] — 来源
- [[Obsidian]] — 配合使用的知识库工具
- [[Karpathy_LLM_Wiki_Vault]] — 配套知识库模板