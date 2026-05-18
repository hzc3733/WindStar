---
title: "CC_Switch"
type: entity
tags: [工具, 模型切换, Claude_Code]
sources: [Clippings/Bilibili/2026-05-18-Harness 实践：让 Agent 全自动制作知识讲解视频.md]
last_updated: 2026-05-18
---

## 定义

CC Switch是一个桌面配置工具，可以让Claude Code/Codex等Agent切换为任意的语言模型。在该视频中用于给Claude Code配置MiniMax token plan。

## 核心功能

| 功能 | 说明 |
| --- | --- |
| 模型切换 | 将Claude Code切换为指定模型 |
| 提供商配置 | 内置MiniMax等提供商支持 |
| API Key管理 | 粘贴并保存API密钥 |

## 使用流程

1. 下载安装包（GitHub release页面）
2. 打开CC Switch
3. 在agent栏选择Claude Code
4. 点击加号，选择MiniMax提供商
5. 粘贴MiniMax token plan的API Key
6. 主模型全部改成MiniMax M2.7
7. 点击添加并启用

## 关联连接
- [[Claude_Code]] — 被切换的Agent
- [[MiniMax]] — 切换目标模型
- [[摘要-harness实践知识讲解视频]] — 使用场景来源