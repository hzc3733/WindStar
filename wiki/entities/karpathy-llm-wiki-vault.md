---
title: "karpathy-llm-wiki-vault"
type: entity
tags: [知识库, 工具, Obsidian, LLM, 模板]
sources: [raw/03-transcripts/2026-05-13-把B站视频转成本地AI知识库！新手也能3分钟上手.md]
last_updated: 2026-05-13
---

## 定义

karpathy-llm-wiki-vault 是由 B 站 up 主「杰森的效率工坊」开源的 Obsidian 知识库模板，基于 Andre Karpathy 提出的 LLM-Wiki 核心理念构建。该模板提供了标准化的知识管理结构，支持 YouTube 视频自动抓取和本地知识库管理，配合 skills 功能可自动完成双向链接与知识图谱构建。

## 核心目录结构

- `raw/01-articles/` — 网页剪藏的 Markdown 文章
- `raw/02-papers/` — 论文和 PDF 文献
- `raw/03-transcripts/` — 视频转录文案和会议记录
- `raw/09-archive/` — 已处理文件的归档目录
- `wiki/sources/` — 资料摘要
- `wiki/entities/` — 实体（人物、公司、工具、产品）
- `wiki/concepts/` — 概念（框架、方法论、理论）
- `wiki/syntheses/` — 综合分析

## 核心技能

- `/ingest` — 将 raw/ 目录下的原始资料编译到 wiki/
- `/query` — 向知识库提问
- `/lint` — 检查并修复 wiki 目录中的错误（死链、孤儿页面等）

## 关联连接

- [[Obsidian]] — 本地知识库核心
- [[Obsidian_Web_Clipper]] — 网页剪藏工具
- [[Bilibili_Web_Clipper]] — B 站专用抓取扩展
- [[摘要-bilibili-ai-knowledge-base]] — B 站视频知识库教程来源
