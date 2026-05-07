---
source: 公众号 - 小胖有事说
url: https://mp.weixin.qq.com/s/0Se4i8RHrtQc-wgGmUkfvw
date: 2026-05-07
tags: [AI/工具, Claude/教程, 已读]
---

# 全网最全！60分钟全面掌握Claude Code

> 作者 | 小胖有事说
> 原文是一篇CC完整图文攻略，配套60分钟视频教程

## 核心要点

CC vs 对话式AI：CC是自主的 Agent 程序（LLM Loop），自己做计划、调工具、看结果、下一步，循环往复直到任务完成。**不一定要用 Claude 模型，可以换其他模型。**

CC 凭什么好：
1. **本地运行** — 直接读写本地文件、执行终端命令
2. **Harness 工程更好** — 大模型之外的设计决定了 Agent 表现差异

## 上手安装

### 安装（推荐在终端/IDE里装）
- 官网复制命令：`https://code.claude.com/docs/zh-CN/overview`
- 或让 IDE Agent 直接帮你装
- 验证：`claude --version`

### 配置模型（重点）
- 最佳方案：订阅 Claude 会员，`/login`
- 省钱方案：用 **cc switch** 管理多个模型 API（国产大模型等）
  - 下载：https://github.com/farion1231/cc-switch/releases
  - ⚠️ **必须在打开 claude 之前先打开 cc switch**，否则切不动

### 三种权限模式（Shift+Tab 切换）
| 模式 | 说明 |
|------|------|
| **Plan Mode** | CC 先给计划等你确认 |
| **默认模式** | 智能判断哪些问你、哪些直接做 |
| **Accept Edits** | 改文件不问，跑命令会问 |
| **危险模式** | `--dangerously-skip-permissions`（一路绿灯） |

### 交互方式
- **@文件** — 精准给上下文（省 token）
- **贴图片** — 利用多模态能力
- **斜杠命令** `/` — `/model` 切换模型，`/btw` 顺便问一句不污染上下文
- **换行**：Mac `Option+Enter`，Win `Ctrl+Enter`
- **指令越长越省 token** — 越短它越要自己探索

## 掌控 CC

### 后悔药（回滚）
- 双击 `ESC` 或 `/rewind` → 可选回滚对话/文件/两者
- **真正靠谱的是 Git** — 每做完一步让 CC 存档一步

### 上下文管理
- 上下文**超过 60% 就 `/compact`**
- `/context` 查看详细占比
- `/clear` 彻底清空
- `/resume` 恢复历史对话，`-c` / `--continue` 继续上次

## 个性化：让 CC 越用越懂你

### CLAUDE.md（第一优先级，全部注入）
- **全局** `~/.claude/CLAUDE.md` — 个人习惯、永远用中文等
- **项目级** 根目录 — `/init` 自动生成，团队共享
- **文件夹级** 子文件夹

### Auto Memory（第二优先级，按需注入）
- `/memory` 手动开启 → CC 后台记录你的偏好/反馈/项目进度
- `Ctrl+O` 显示具体内容
- 说「忘掉这个」就删了

### 自建参考文档（第三层）
- 把不同功能记忆拆成独立文档，在 claude.md 里写何时参考哪个
- 本质：在合适时间向大模型注入压缩过的上下文

## 高级扩展

| 能力 | 说明 |
|------|------|
| **Skill** | 装技能包——按需调用的「外接大脑」。`/skill` 或 CC 主动调用。用 find-skill 找，skill creator 做 |
| **MCP** | 连接外部工具（NotebookLM、Figma 等），但占 token 较多 |
| **CLI 工具** | 2025 最火趋势——飞书 CLI、opencli（查社媒、下图片） |
| **SubAgent** | 派分身并行干活，主 Agent 拿结果。`/agent` 手动创建或自动派生 |
| **Hook** | 条件反射——完成任务后发提示音、提交前自动格式化等 |
| **插件** | Skill+SubAgent+Hook+MCP 打包。`/plugin` 管理 |

## 速查命令

| 命令 | 用途 |
|------|------|
| `/model` | 切换高中低档模型 |
| `/btw` | 顺便问一句（不污染主上下文） |
| `/compact` | 压缩上下文 |
| `/context` | 查看上下文占比 |
| `/rewind` | 回滚 |
| `/init` | 项目初始化生成 CLAUDE.md |
| `/memory` | 开启/管理 Auto Memory |
| `/agent` | 创建子代理 |
| `/plugin` | 插件管理 |
| `/help` | 所有命令清单 |
| `!` | 进入 bash 模式直接跑命令 |
| `Ctrl+B` | 后台运行不阻塞对话 |

## 我的思考

这篇把 CC 从安装到高级扩展讲得很系统，四个关卡逻辑清晰：
1. 上手 → 2. 掌控 → 3. 个性化 → 4. 高级扩展

最关键的不是某个功能，而是**习惯跟 AI 协作的方式**——从一问一答到构建系统、组织 AI 让它自己去干。
