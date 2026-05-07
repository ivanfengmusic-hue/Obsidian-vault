---
source: 今日头条 - 小胖有事说
url: https://m.toutiao.com/is/X8o6bNMNWeY/
date: 2026-05-07
tags: [AI/工具, Claude/教程, 已读]
---

# Claude Code 全面教程笔记

> 60分钟视频教程，Claude Code 从入门到精通

## 核心要点

- **安装与登录**：`npm i -g @anthropic-ai/claude-code` → 浏览器 OAuth 登录
- **两种模式**：交互式 REPL（`claude`）vs 打印模式（`claude -p "xxx"`）
- **核心能力**：自主读写文件、执行命令、Git 操作、管理 MCP 服务
- **Claude Code 是一个全功能的终端编码助手**，支持子代理、工作树隔离、代码审查等功能

## 常用命令速查

| 用途 | 命令 |
|------|------|
| 交互模式 | `claude` |
| 一次性任务 | `claude -p "你的任务" --max-turns 10` |
| 继续上次会话 | `claude -c` |
| 代码审查 | `claude -p "审查当前diff"` |
| 结构化输出 | `claude -p "任务" --output-format json` |
| 切换模型 | `/model opus`（交互模式中） |

## 关键技巧

- **权限控制**：用 `--allowedTools "Read,Edit"` 限制能力范围
- **上下文管理**：交互模式用 `/compact` 压缩上下文，超过 70% 时质量下降
- **CLAUDE.md**：项目级记忆文件，存架构、命令规范、代码标准
- **子代理**：在 `.claude/agents/` 定义专用代理（如安全审查、数据库专家）
- **MCP 集成**：给 Claude 连数据库、GitHub、浏览器等外部工具

## 注意事项

- 记得看官方文档：`claude doctor` 检查安装状态
- 防止无限循环：打印模式必须加 `--max-turns`
- 费用控制：可用 `--max-budget-usd` 和 `--model haiku`

## 我的思考

Claude Code 把 AI 编码助手从聊天工具变成了真正的终端开发助手，能自主完成任务、审查代码、管理 Git 流程。配合 MCP 可以扩展能力边界，适合做自动化工作流。
