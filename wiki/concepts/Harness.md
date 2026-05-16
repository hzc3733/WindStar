---
title: "Harness"
type: concept
tags: [AI架构, Agent, 大模型]
sources: [Clippings/Bilibili/AI工具/保姆级Claude Code速成.md]
last_updated: 2026-05-16
---

## 定义
Harness是驾驭大模型的核心架构层，负责调度背后的模型、处理思考过程。Claude Code、Open Claude、Hermes Agent等产品本质都是Harness，它们通过反复调用底层大模型几十上百次来完成复杂任务。

## 关键信息

### 核心作用
- **模型调度**：Harness负责调度背后的模型，决定何时调用、调用多少次
- **思考处理**：处理AI的推理和思考过程
- **工具整合**：将大模型能力封装成用户可用的工具

### 产品形态
- Claude Code（Anthropic）
- Open AI的Agent产品
- Hermes Agent
- 国产Agent产品

### 与国产模型的关系
Harness本质上是一层壳，所以国产模型也能用在这层壳里面。用户输入命令后，Harness会反反复复调用大模型数十次，执行时间往往比直接使用豆包等产品要久。

## 关联连接
- [[Claude_Code]] — 典型Harness产品
- [[MCP]] — Harness连接外部工具的协议