---
title: "Claude_Code"
type: entity
tags: [AI-Agent, 编程, Anthropic]
sources: [raw/01-articles/技能使用说明书.md]
last_updated: 2026-05-16
---

## 定义

Claude Code 是 Anthropic 官方推出的自主编程 Agent，通过 CLI 运行，可读取文件、写代码、执行 shell 命令、管理 git 工作流，完全自主运行。

## 核心概念

- **PTY 模式**：pseudo-terminal，伪终端。Claude Code 是交互式终端应用，必须配合 PTY 才能正常运行，否则会挂起。
- **工作目录隔离**：每个任务建议在独立目录运行，避免冲突。
- **后台模式**：使用 `background=true` 启动长时间任务，通过 `process` 工具监控进度。

## 常用命令

```bash
# 单次任务（one-shot）
terminal(command="claude --message '实现登录功能'", workdir="~/project", pty=true)

# 后台运行
terminal(command="claude --message '重构认证模块'", workdir="~/project", background=true, pty=true)
```

## 适用场景

构建功能、代码重构、PR 审查、批量修复 issue。

## 关联连接
- [[Hermes_Agent]] — 宿主 Agent
- [[摘要-hermes-agent-ji-neng-shi-yong-shuo-ming-shu]] — 技能来源