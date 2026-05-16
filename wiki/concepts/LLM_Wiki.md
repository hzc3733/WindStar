---
title: "LLM Wiki"
type: concept
tags: [知识库, Karpathy, AI, Obsidian]
sources: [Clippings/Bilibili/AI工具/把B站视频转成本地AI知识库.md]
last_updated: 2026-05-16
---

## 定义
LLM Wiki是由Andrej Karpathy提出的利用Obsidian作为本地知识库、通过双链笔记和AI技术实现知识互联与生长的理念。

## 关键信息

### 核心理念
视频通过Web Clipper抓取，转化为Markdown格式，存入Obsidian vault，让LLM能够理解，最终实现知识生长。

### Karpathy-LLM-Wiki-Vault
基于Karpathy理念构建的开源Obsidian知识库模板，支持YouTube视频自动抓取，由B站UP主"杰森的效率工坊"开源。

### B站适配困境
- B站采用不同的播放器与页面结构，Obsidian Web Clipper无法正确解析
- B站字幕格式与YouTube不同，需专门解析
- BVID等B站特有数据需单独处理

### 解决方案
B站UP主"小陈师傅c_z"开发了Bilibili Web Clipper浏览器扩展，可一键将视频转化为结构化笔记。

### 完整工作流
1. 安装Bilibili Web Clipper扩展
2. 打开任意B站视频，点击扩展图标
3. 插件自动提取标题、up主、字幕、简介
4. 一键生成Markdown文件存入vault
5. 配合Skills功能自动完成双向链接与知识图谱构建

## 关联连接
- [[Obsidian]] — 知识库工具
- [[Bilibili_Web_Clipper]] — B站专用抓取工具
- [[Karpathy_LLM_Wiki_Vault]] — 开源模板
- [[摘要-b站视频转知识库]] — 来源摘要