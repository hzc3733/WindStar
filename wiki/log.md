# Wiki 操作日志

---

## [2026-05-16] ingest | 批量摄入提示工程核心资料与B站教程

### 处理文件清单

**Articles（5 篇）：**
- `raw/01-articles/提示设计策略  _  Gemini API.md` — Google Gemini 中文指南
- `raw/01-articles/Prompt Engineering in 2025_ Complete Guide for ChatGPT, Claude, and Gemini.md` — PromptBuilder 指南
- `raw/01-articles/The Complete Guide to AI Prompt Engineering in 2025-2026.md` — Espo.ai 指南
- `raw/01-articles/The Complete Prompt Engineering Guide (2025).md` — BrilliantPrompts 指南
- `raw/01-articles/Prompting best practices-Anthropic.md` — Anthropic 官方最佳实践

**Papers（2 篇）：**
- `raw/02-papers/Goolge-Prompt-Engineering-whitepaper.pdf` — Google 官方白皮书（65 页）
- `raw/02-papers/5C Prompt Contracts .pdf` — 5C 提示契约研究论文

**Transcripts（1 篇）：**
- `raw/03-transcripts/2026-05-13-把B站视频转成本地AI知识库！新手也能3分钟上手.md` — B站视频教程

### 创建的来源摘要（8 个）

| 文件 | 描述 |
|------|------|
| [[摘要-bilibili-llm-wiki-intro]] | B站视频转本地AI知识库的实操教程 |
| [[摘要-gemini-api-prompting-strategies]] | Gemini API 提示设计策略 |
| [[摘要-prompt-engineering-2025-guide-promptbuilder]] | Prompt Engineering 2025 完整指南 |
| [[摘要-ai-prompt-engineering-2025-2026-espo]] | AI 提示工程 2025-2026 指南 |
| [[摘要-complete-prompt-engineering-guide-2025]] | 完整提示工程指南 2025 |
| [[摘要-anthropic-prompting-best-practices]] | Anthropic 提示最佳实践 |
| [[摘要-google-prompt-engineering-whitepaper]] | Google 提示工程白皮书 |
| [[摘要-5c-prompt-contracts-paper]] | 5C Prompt Contracts 论文 |

### 创建的概念页面（5 个）

| 页面 | 类型 | 核心内容 |
|------|------|----------|
| [[LLM_Wiki]] | 核心理念 | Karpathy提出的知识管理理念 |
| [[Prompt_Engineering]] | 核心概念 | 提示工程总览、七大要素、技术分类 |
| [[5C_Framework]] | 框架 | 5C 提示契约框架详解 |
| [[Chain_of_Thought]] | 技术 | 思维链技术、Zero-shot/Few-shot CoT |
| [[Few_Shot_Prompting]] | 技术 | 少样本提示最佳实践 |
| [[Context_Engineering]] | 范式 | 从提示工程到上下文工程的转变 |

### 创建的实体页面（7 个）

| 页面 | 描述 |
|------|------|
| [[Obsidian]] | 本地双链笔记软件，LLM Wiki 知识库核心 |
| [[Bilibili_Web_Clipper]] | B站专用网页剪藏扩展 |
| [[Karpathy_LLM_Wiki_Vault]] | 基于Karpathy理念的开源知识库模板 |
| [[Google]] | Google 公司及其 AI 产品 |
| [[Anthropic]] | Anthropic 公司及其安全研究 |
| [[Gemini]] | Google Gemini 模型家族特性 |
| [[Claude]] | Anthropic Claude 模型家族特性 |

### 冲突与发现

**知识冲突（已标注）：**
- 在 [[5C_Framework]] 页面中记录了「5C vs 复杂 DSL 之争」的知识冲突

**重要发现：**
1. **提示长度悖论**：研究表明 150-300 词是最佳长度，超过 3,000 tokens 性能显著下降
2. **CoT 悖论**：现代推理模型（GPT-5, Claude 4, Gemini 3）内部自动推理，显式 CoT 反而可能有害
3. **5C 效率优势**：平均仅需 54 tokens 输入，比 DSL 节省 6 倍以上
4. **Gemini 简化趋势**：Gemini 3 不再需要复杂提示工程，建议使用简化提示
5. **Context Engineering 范式**：行业正在从单个提示优化转向系统上下文管理

### 更新文件
- [[index.md]] — 重新组织了总目录结构
- [[log.md]] — 记录本次操作（本条目）

### 归档操作
所有 8 个源文件已移动至 `raw/09-archive/` 目录。

---

## [2026-05-16] query | 基于 5C Framework 设计 Markdown 笔记提示词

- **查询**: 根据 5C Framework 设计撰写 Markdown 格式知识笔记的提示词
- **引用**: [[5C_Framework]]
- **输出**: 已创建 synthesis 文件 [[5c-prompt-markdown-note-taking]]
- **更新**: [[index.md]] 已注册新 synthesis

---

## [2026-05-16] ingest | 批量摄入 Hermès Agent 工具文档与 PDF 书籍

### 处理文件清单

**Articles（6 篇）：**
- `raw/01-articles/工具说明书.md` — Hermès Agent 工具使用说明书（16 大类工具）
- `raw/01-articles/技能使用说明书.md` — Hermès Agent 技能使用说明书（80 个技能）
- `raw/01-articles/《思考致富》2016版 拿破仑·希尔(美).pdf` — 成功学经典著作
- `raw/01-articles/你是你吃出来的：吃对少生病，病了这样吃.pdf` — 营养健康指南
- `raw/01-articles/财富阶梯.pdf` — 财富投资策略指南
- `raw/01-articles/老子的N維傳訊 德道經原文重現重譯 (呂尚) .pdf` — 道家经典重译

### 创建的来源摘要（6 个）

| 文件 | 描述 |
|------|------|
| [[摘要-hermes-agent-gong-ju-shuo-ming-shu]] | Hermès Agent 16 大类工具完整说明 |
| [[摘要-hermes-agent-ji-neng-shi-yong-shuo-ming-shu]] | Hermès Agent 80 个技能分类详解 |
| [[摘要-si-kao-zhi-fu-2016-ban]] | 拿破仑·希尔《思考致富》2016版 |
| [[摘要-cai-fu-jie-ti]] | 《财富阶梯》PDF |
| [[摘要-ni-shi-ni-chi-chu-lai-de]] | 《你是你吃出来的》营养指南 |
| [[摘要-lao-zi-de-n-wei-chuan-xun]] | 《老子的N維傳訊》 |

### 创建的实体页面（3 个）

| 页面 | 类型 | 描述 |
|------|------|------|
| [[Hermes_Agent]] | 实体 | 多平台AI Agent，16大类工具+80技能 |
| [[Claude_Code]] | 实体 | Anthropic官方AI编程Agent |
| [[拿破仑希尔]] | 人物 | 成功学之父，《思考致富》作者 |

### 创建的概念页面（2 个）

| 页面 | 类型 | 描述 |
|------|------|------|
| [[财富思维]] | 概念 | 通过思考方式实现财务自由的理念 |
| [[营养学]] | 概念 | 食物与人体健康关系的科学 |

### 更新文件
- [[index.md]] — 新增 6 个 Sources、3 个 Entities、2 个 Concepts
- [[log.md]] — 记录本次操作（本条目）

### 归档操作
所有 6 个源文件已移动至 `raw/09-archive/` 目录。

---

*最后更新：2026-05-16*