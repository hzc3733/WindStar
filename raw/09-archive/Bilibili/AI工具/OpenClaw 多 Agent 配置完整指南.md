---
title: "OpenClaw 多 Agent 配置完整指南"
source: "https://www.cnblogs.com/zhaoxxnbsp/p/19796149"
author:
  - "[[直角漫步]]"
published: 2026-03-30
created: 2026-05-16
description: "本文档详细说明如何在 OpenClaw 中配置多个独立的 Agent（智能体），实现不同用途、不同人格、不同渠道的隔离使用。 目录 概念介绍 准备工作 方法一：使用向导添加 Agent 方法二：手动配置（推荐） 配置路由绑定 为每个 Agent 设置人设 进阶配置 验证与管理 常见场景示例 故障排除"
tags:
  - "clippings"
---
2026-03-30 15:54阅读: 4678评论: 0推荐: 1

> 本文档详细说明如何在 OpenClaw 中配置多个独立的 Agent（智能体），实现不同用途、不同人格、不同渠道的隔离使用。

---

## 目录

## 1\. 概念介绍

### 1.1 什么是 Agent？

一个 **Agent（智能体）** 是一个完全独立的"大脑"，拥有：

| 组件 | 说明 | 位置 |
| --- | --- | --- |
| 工作区 | 文件、笔记、人设文件 | `~/.openclaw/workspace-<id>/` |
| 状态目录 | 认证配置、模型注册 | `~/.openclaw/agents/<id>/agent/` |
| 会话存储 | 聊天历史、路由状态 | `~/.openclaw/agents/<id>/sessions/` |

### 1.2 多 Agent 的用途

| 场景 | 说明 |
| --- | --- |
| **多人共用** | 不同用户使用不同的 Agent，数据隔离 |
| **工作/生活分离** | 工作 Agent 和个人 Agent 分开 |
| **不同人格** | 不同的 SOUL.md 定义不同的性格 |
| **不同模型** | 不同 Agent 使用不同的 AI 模型 |
| **渠道隔离** | Telegram 用 Agent A，WhatsApp 用 Agent B |

### 1.3 目录结构预览

配置完成后的目录结构：

```bash
~/.openclaw/
├── openclaw.json              # 主配置文件
├── workspace/                 # main agent 工作区
│   ├── AGENTS.md
│   ├── SOUL.md
│   ├── USER.md
│   └── memory/
├── workspace-work/            # work agent 工作区
│   ├── AGENTS.md
│   ├── SOUL.md
│   └── ...
├── workspace-family/          # family agent 工作区
│   └── ...
└── agents/
    ├── main/
    │   ├── agent/             # 认证配置
    │   │   ├── auth-profiles.json
    │   │   └── models.json
    │   └── sessions/          # 会话存储
    ├── work/
    │   ├── agent/
    │   └── sessions/
    └── family/
        ├── agent/
        └── sessions/
```

---

## 2\. 准备工作

### 2.1 确认当前配置

```bash
# 查看当前 agents 配置
cat ~/.openclaw/openclaw.json | jq '.agents'

# 查看当前目录结构
ls -la ~/.openclaw/agents/
```

### 2.2 备份现有配置

```bash
# 备份配置文件
cp ~/.openclaw/openclaw.json ~/.openclaw/openclaw.json.backup

# 备份工作区（可选）
cp -r ~/.openclaw/workspace ~/.openclaw/workspace.backup
```

### 2.3 确保 Gateway 正在运行

```bash
openclaw gateway status
```

如果未运行：

```bash
openclaw gateway start
```

---

## 3\. 方法一：使用向导添加 Agent

### 3.1 运行添加命令

```bash
openclaw agents add <agent-id>
```

示例：

```bash
openclaw agents add work
```

### 3.2 向导交互流程

向导会依次询问：

1. **Agent 名称** ：如 "工作助手"
2. **工作区路径** ：默认 `~/.openclaw/workspace-work`
3. **默认模型** ：可选，留空则使用全局默认
4. **绑定渠道** ：可选择绑定到特定渠道

### 3.3 验证添加结果

```bash
openclaw agents list
```

---

## 4\. 方法二：手动配置（推荐）

手动配置更灵活，适合复杂场景。

### 4.1 创建工作区目录

```bash
# 创建 work agent 工作区
mkdir -p ~/.openclaw/workspace-work

# 创建 family agent 工作区
mkdir -p ~/.openclaw/workspace-family

# 创建 memory 子目录
mkdir -p ~/.openclaw/workspace-work/memory
mkdir -p ~/.openclaw/workspace-family/memory
```

### 4.2 创建 Agent 状态目录

```bash
# work agent
mkdir -p ~/.openclaw/agents/work/agent
mkdir -p ~/.openclaw/agents/work/sessions

# family agent
mkdir -p ~/.openclaw/agents/family/agent
mkdir -p ~/.openclaw/agents/family/sessions
```

### 4.3 复制认证配置（可选）

如果想让新 Agent 使用相同的 API 认证：

```bash
# 复制 main agent 的认证配置到 work agent
cp ~/.openclaw/agents/main/agent/auth-profiles.json ~/.openclaw/agents/work/agent/

# 复制模型配置
cp ~/.openclaw/agents/main/agent/models.json ~/.openclaw/agents/work/agent/
```

### 4.4 编辑主配置文件

编辑 `~/.openclaw/openclaw.json` ：

```bash
nano ~/.openclaw/openclaw.json
# 或
vim ~/.openclaw/openclaw.json
```

在配置文件中添加 `agents.list` 部分：

```
{
  "meta": {
    // ... 保留原有内容
  },
  "wizard": {
    // ... 保留原有内容
  },
  "auth": {
    // ... 保留原有内容
  },
  "models": {
    // ... 保留原有内容
  },

  // ========== 添加 agents 配置 ==========
  "agents": {
    "defaults": {
      "model": {
        "primary": "zai/glm-5"
      },
      "models": {
        "zai/glm-5": {
          "alias": "GLM"
        }
      },
      "workspace": "/root/.openclaw/workspace",
      "compaction": {
        "mode": "safeguard"
      }
    },
    "list": [
      {
        "id": "main",
        "default": true,
        "name": "小沃",
        "workspace": "~/.openclaw/workspace",
        "agentDir": "~/.openclaw/agents/main/agent"
      },
      {
        "id": "work",
        "name": "工作助手",
        "workspace": "~/.openclaw/workspace-work",
        "agentDir": "~/.openclaw/agents/work/agent",
        "model": "zai/glm-5"
      },
      {
        "id": "family",
        "name": "家庭助手",
        "workspace": "~/.openclaw/workspace-family",
        "agentDir": "~/.openclaw/agents/family/agent",
        "model": "zai/glm-5"
      }
    ]
  },
  // ========== agents 配置结束 ==========

  "tools": {
    "profile": "coding"
  },
  "commands": {
    // ... 保留原有内容
  },
  "session": {
    "dmScope": "per-channel-peer"
  },
  "channels": {
    // ... 保留原有内容
  },
  "gateway": {
    // ... 保留原有内容
  }
}
```

### 4.5 重启 Gateway 使配置生效

```bash
# 重启 Gateway
openclaw gateway restart

# 或通过 systemd
systemctl --user restart openclaw-gateway
```

### 4.6 验证配置

```bash
# 列出所有 agents
openclaw agents list

# 预期输出：
# ┌────────┬──────────┬─────────────────────────────┬─────────┐
# │ ID     │ Name     │ Workspace                   │ Default │
# ├────────┼──────────┼─────────────────────────────┼─────────┤
# │ main   │ 小沃     │ ~/.openclaw/workspace       │ ✓       │
# │ work   │ 工作助手 │ ~/.openclaw/workspace-work  │         │
# │ family │ 家庭助手 │ ~/.openclaw/workspace-family│         │
# └────────┴──────────┴─────────────────────────────┴─────────┘
```

---

## 5\. 配置路由绑定

绑定（Bindings）决定消息路由到哪个 Agent。

### 5.1 绑定规则优先级

优先级从高到低：

1. `peer` 匹配（精确私信/群组 ID）
2. `guildId` （Discord 服务器）
3. `teamId` （Slack 团队）
4. `accountId` （渠道账户）
5. 渠道级匹配
6. 默认 Agent

### 5.2 添加绑定配置

在 `openclaw.json` 中添加 `bindings` 部分：

```
{
  // ... 其他配置

  "bindings": [
    // 示例1：Telegram 消息路由到 work agent
    {
      "agentId": "work",
      "match": {
        "channel": "telegram"
      }
    },

    // 示例2：特定用户路由到特定 agent
    {
      "agentId": "work",
      "match": {
        "channel": "telegram",
        "peer": {
          "kind": "dm",
          "id": "5010223608"
        }
      }
    },

    // 示例3：特定群组路由到 family agent
    {
      "agentId": "family",
      "match": {
        "channel": "telegram",
        "peer": {
          "kind": "group",
          "id": "-1001234567890"
        }
      }
    }
  ]
}
```

### 5.3 完整配置示例

```
{
  "agents": {
    "defaults": {
      "model": { "primary": "zai/glm-5" },
      "models": { "zai/glm-5": { "alias": "GLM" } },
      "workspace": "/root/.openclaw/workspace",
      "compaction": { "mode": "safeguard" }
    },
    "list": [
      {
        "id": "main",
        "default": true,
        "name": "小沃",
        "workspace": "~/.openclaw/workspace",
        "agentDir": "~/.openclaw/agents/main/agent"
      },
      {
        "id": "work",
        "name": "工作助手",
        "workspace": "~/.openclaw/workspace-work",
        "agentDir": "~/.openclaw/agents/work/agent"
      },
      {
        "id": "family",
        "name": "家庭助手",
        "workspace": "~/.openclaw/workspace-family",
        "agentDir": "~/.openclaw/agents/family/agent"
      }
    ]
  },

  "bindings": [
    // 特定 Telegram 用户 -> work
    {
      "agentId": "work",
      "match": {
        "channel": "telegram",
        "peer": { "kind": "dm", "id": "5010223608" }
      }
    },
    // 其他 Telegram 消息 -> main
    {
      "agentId": "main",
      "match": { "channel": "telegram" }
    },
    // Web UI -> main
    {
      "agentId": "main",
      "match": { "channel": "webchat" }
    }
  ],

  "channels": {
    "telegram": {
      "enabled": true,
      "botToken": "your-bot-token",
      "dmPolicy": "pairing",
      "proxy": "http://127.0.0.1:10808"
    }
  },

  // ... 其他配置
}
```

### 5.4 验证绑定

```bash
openclaw agents list --bindings
```

---

## 6\. 为每个 Agent 设置人设

每个 Agent 可以有独立的人设文件。

### 6.1 人设文件说明

| 文件 | 作用 |
| --- | --- |
| `SOUL.md` | 定义 Agent 的性格、语气、价值观 |
| `USER.md` | 定义用户信息 |
| `AGENTS.md` | 定义工作区规则和行为指南 |
| `IDENTITY.md` | 定义 Agent 身份信息 |
| `TOOLS.md` | 本地工具笔记 |

### 6.2 创建 work agent 人设

创建 `~/.openclaw/workspace-work/SOUL.md` ：

```bash
nano ~/.openclaw/workspace-work/SOUL.md
```

内容示例：

```markdown
# SOUL.md - 工作助手人设

## 身份

- 名称：阿工
- 角色：专注工作的 AI 助手
- 语气：专业、简洁、高效

## 核心原则

1. **效率优先**：回答直接，不废话
2. **专业准确**：提供可靠的技术建议
3. **任务导向**：帮助用户完成工作目标

## 行为规范

- 代码优先于解释
- 使用清单和表格组织信息
- 主动询问关键细节
- 遇到不确定的问题，坦诚说明

## 禁止事项

- 不闲聊
- 不主动分享个人观点
- 不做与工作无关的事情
```

### 6.3 创建 family agent 人设

创建 `~/.openclaw/workspace-family/SOUL.md` ：

```bash
nano ~/.openclaw/workspace-family/SOUL.md
```

内容示例：

```markdown
# SOUL.md - 家庭助手人设

## 身份

- 名称：小家
- 角色：温馨的家庭助手
- 语气：亲切、温暖、有耐心

## 核心原则

1. **家庭友好**：内容适合所有年龄段
2. **温暖陪伴**：像家人一样关心用户
3. **生活助手**：帮助解决日常问题

## 能力范围

- 天气查询
- 日程提醒
- 生活建议
- 亲子教育
- 健康小贴士
- 简单娱乐（笑话、故事）

## 语气风格

- 使用表情符号 🌸
- 多用"我们"、"一起"
- 遇到问题给鼓励
```

### 6.4 复制基础文件

```bash
# 复制 AGENTS.md 模板
cp ~/.openclaw/workspace/AGENTS.md ~/.openclaw/workspace-work/
cp ~/.openclaw/workspace/AGENTS.md ~/.openclaw/workspace-family/

# 创建空的 memory 目录
mkdir -p ~/.openclaw/workspace-work/memory
mkdir -p ~/.openclaw/workspace-family/memory
```

---

## 7\. 进阶配置

### 7.1 为 Agent 设置不同模型

```
{
  "agents": {
    "list": [
      {
        "id": "main",
        "default": true,
        "workspace": "~/.openclaw/workspace",
        "model": "zai/glm-5"  // 默认模型
      },
      {
        "id": "work",
        "workspace": "~/.openclaw/workspace-work",
        "model": "zai/glm-4.7"  // 更强大的模型
      },
      {
        "id": "chat",
        "workspace": "~/.openclaw/workspace-chat",
        "model": "zai/glm-4.7-flash"  // 快速响应
      }
    ]
  }
}
```

### 7.2 为 Agent 设置沙箱隔离

```
{
  "agents": {
    "list": [
      {
        "id": "main",
        "default": true,
        "workspace": "~/.openclaw/workspace",
        "sandbox": {
          "mode": "off"  // 无沙箱
        }
      },
      {
        "id": "work",
        "workspace": "~/.openclaw/workspace-work",
        "sandbox": {
          "mode": "all",      // 始终沙箱
          "scope": "agent",   // 每智能体一个容器
          "docker": {
            "setupCommand": "apt-get update && apt-get install -y git curl"
          }
        }
      }
    ]
  }
}
```

### 7.3 限制 Agent 工具权限

```
{
  "agents": {
    "list": [
      {
        "id": "main",
        "default": true,
        "workspace": "~/.openclaw/workspace",
        // 无限制
      },
      {
        "id": "restricted",
        "workspace": "~/.openclaw/workspace-restricted",
        "tools": {
          "allow": ["read", "web_search", "web_fetch"],
          "deny": ["exec", "write", "edit", "sessions_spawn"]
        }
      }
    ]
  }
}
```

### 7.4 配置 Agent 间通信

```
{
  "tools": {
    "agentToAgent": {
      "enabled": true,
      "allow": ["main", "work", "family"]
    }
  }
}
```

---

## 8\. 验证与管理

### 8.1 列出所有 Agents

```bash
# 基本信息
openclaw agents list

# 包含绑定信息
openclaw agents list --bindings

# JSON 格式
openclaw agents list --json
```

### 8.2 测试特定 Agent

```bash
# 向指定 agent 发送消息测试
openclaw agent --agent work --message "你好，介绍一下你自己"
```

### 8.3 查看会话状态

```bash
# 查看所有会话
openclaw status

# 查看特定 agent 的会话
openclaw sessions list
```

### 8.4 查看日志

```bash
# 实时日志
openclaw logs --follow

# 筛选特定 agent
openclaw logs --follow | grep "agentId"
```

### 8.5 重启特定 Agent

```bash
# 重启整个 Gateway（所有 agents）
openclaw gateway restart
```

---

## 9\. 常见场景示例

### 9.1 场景：工作/生活分离

**需求** ：Telegram 用于工作，Web UI 用于个人

```
{
  "agents": {
    "list": [
      {
        "id": "personal",
        "default": true,
        "name": "小沃",
        "workspace": "~/.openclaw/workspace"
      },
      {
        "id": "work",
        "name": "阿工",
        "workspace": "~/.openclaw/workspace-work"
      }
    ]
  },
  "bindings": [
    { "agentId": "work", "match": { "channel": "telegram" } },
    { "agentId": "personal", "match": { "channel": "webchat" } }
  ]
}
```

### 9.2 场景：多人共用

**需求** ：不同家庭成员使用不同的 Agent

```
{
  "agents": {
    "list": [
      { "id": "main", "default": true, "workspace": "~/.openclaw/workspace" },
      { "id": "alice", "workspace": "~/.openclaw/workspace-alice" },
      { "id": "bob", "workspace": "~/.openclaw/workspace-bob" }
    ]
  },
  "bindings": [
    { "agentId": "alice", "match": { "channel": "telegram", "peer": { "kind": "dm", "id": "111111111" } } },
    { "agentId": "bob", "match": { "channel": "telegram", "peer": { "kind": "dm", "id": "222222222" } } }
  ]
}
```

### 9.3 场景：群组专用 Agent

**需求** ：家庭群使用温馨的家庭助手

```
{
  "agents": {
    "list": [
      { "id": "main", "default": true, "workspace": "~/.openclaw/workspace" },
      { "id": "family", "workspace": "~/.openclaw/workspace-family" }
    ]
  },
  "bindings": [
    {
      "agentId": "family",
      "match": {
        "channel": "telegram",
        "peer": { "kind": "group", "id": "-1001234567890" }
      }
    }
  ]
}
```

### 9.4 场景：高/低模型搭配

**需求** ：重要任务用强模型，日常聊天用快模型

```
{
  "agents": {
    "list": [
      { "id": "chat", "default": true, "model": "zai/glm-4.7-flash", "workspace": "~/.openclaw/workspace" },
      { "id": "pro", "model": "zai/glm-4.7", "workspace": "~/.openclaw/workspace-pro" }
    ]
  },
  "bindings": [
    { "agentId": "pro", "match": { "channel": "telegram", "peer": { "kind": "dm", "id": "YOUR_ID" } } },
    { "agentId": "chat", "match": { "channel": "telegram" } }
  ]
}
```

---

## 10\. 故障排除

### 10.1 配置不生效

```bash
# 检查配置语法
cat ~/.openclaw/openclaw.json | jq .

# 重启 Gateway
openclaw gateway restart

# 查看错误日志
openclaw logs | grep -i error
```

### 10.2 Agent 找不到

```bash
# 确认 agent 目录存在
ls -la ~/.openclaw/agents/

# 确认工作区存在
ls -la ~/.openclaw/workspace-*

# 检查配置
openclaw agents list
```

### 10.3 认证问题

```bash
# 检查认证配置
cat ~/.openclaw/agents/<agent-id>/agent/auth-profiles.json

# 如果缺失，从 main 复制
cp ~/.openclaw/agents/main/agent/auth-profiles.json ~/.openclaw/agents/<agent-id>/agent/
```

### 10.4 会话隔离问题

```bash
# 检查会话目录
ls -la ~/.openclaw/agents/*/sessions/

# 查看会话列表
openclaw sessions list
```

### 10.5 恢复备份

```bash
# 恢复配置文件
cp ~/.openclaw/openclaw.json.backup ~/.openclaw/openclaw.json

# 重启
openclaw gateway restart
```

---

## 附录：快速命令参考

```bash
# 添加 agent（向导）
openclaw agents add <id>

# 列出 agents
openclaw agents list
openclaw agents list --bindings

# 测试 agent
openclaw agent --agent <id> --message "测试消息"

# 重启 gateway
openclaw gateway restart

# 查看状态
openclaw status

# 查看日志
openclaw logs --follow
```

---

## 附录：配置文件模板

### 完整 openclaw.json 示例

```
{
  "meta": {
    "lastTouchedVersion": "2026.3.11",
    "lastTouchedAt": "2026-03-14T10:00:00.000Z"
  },
  "auth": {
    "profiles": {
      "zai:default": {
        "provider": "zai",
        "mode": "api_key"
      }
    }
  },
  "models": {
    "mode": "merge",
    "providers": {
      "zai": {
        "baseUrl": "https://open.bigmodel.cn/api/coding/paas/v4",
        "api": "openai-completions",
        "models": [
          { "id": "glm-5", "name": "GLM-5", "contextWindow": 204800, "maxTokens": 131072 }
        ]
      }
    }
  },
  "agents": {
    "defaults": {
      "model": { "primary": "zai/glm-5" },
      "models": { "zai/glm-5": { "alias": "GLM" } },
      "workspace": "/root/.openclaw/workspace",
      "compaction": { "mode": "safeguard" }
    },
    "list": [
      {
        "id": "main",
        "default": true,
        "name": "小沃",
        "workspace": "~/.openclaw/workspace",
        "agentDir": "~/.openclaw/agents/main/agent"
      },
      {
        "id": "work",
        "name": "工作助手",
        "workspace": "~/.openclaw/workspace-work",
        "agentDir": "~/.openclaw/agents/work/agent"
      }
    ]
  },
  "bindings": [
    { "agentId": "work", "match": { "channel": "telegram" } },
    { "agentId": "main", "match": { "channel": "webchat" } }
  ],
  "tools": {
    "profile": "coding"
  },
  "channels": {
    "telegram": {
      "enabled": true,
      "botToken": "YOUR_BOT_TOKEN",
      "dmPolicy": "pairing",
      "proxy": "http://127.0.0.1:10808"
    }
  },
  "gateway": {
    "port": 18789,
    "mode": "local",
    "bind": "lan",
    "auth": {
      "mode": "token",
      "token": "YOUR_TOKEN"
    }
  }
}
```

---

适用于 OpenClaw 2026.3.x\*

本文作者：直角漫步

本文链接：https://www.cnblogs.com/zhaoxxnbsp/p/19796149

版权声明：本作品采用知识共享署名-非商业性使用-禁止演绎 2.5 中国大陆 许可协议 进行许可。