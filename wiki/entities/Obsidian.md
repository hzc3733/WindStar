---
title: "Obsidian"
type: entity
tags: [知识库, 双链笔记, 本地存储]
sources: [Clippings/Bilibili/AI工具/把B站视频转成本地AI知识库.md]
last_updated: 2026-05-16
---

## 定义
Obsidian是一款本地知识库核心工具，支持双链笔记与图谱可视化，是Karpathy LLM-Wiki理念的重要载体。

## 关键信息

### 在LLM-Wiki中的角色
- 作为本地知识库核心
- 支持双链笔记与图谱可视化
- 配合Local REST API插件提供外部读写接口

### 核心功能
- **双链笔记**：通过`[[页面名称]]`语法建立页面间链接
- **图谱可视化**：可视化展示知识网络
- **本地存储**：所有数据存储在本地，保证隐私

### 相关插件
- **Local REST API**：为外部工具提供读写笔记库的HTTP接口
- **Bilibili Web Clipper**：专用于B站视频的网页剪藏插件

### 工具链组合
完整工具链包含四个核心组件：
1. Obsidian（本地知识库核心）
2. Local REST API插件（外部接口）
3. Karpathy-LLM-Wiki-Vault模板（标准化结构）
4. Bilibili Web Clipper（视频抓取）

## 关联连接
- [[LLM_Wiki]] — 知识库理念
- [[摘要-b站视频转知识库]] — 来源摘要