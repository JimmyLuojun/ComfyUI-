# Project Instructions

> ComfyUI入门学习项目

## Guidelines

### 用户背景

- ComfyUI 初学者，对 AI 绘图工作流、节点概念不熟悉
- Conda / Python 环境管理初学者
- 硬件：MacBook Pro M4 Pro 24GB + Crucial X9 2TB（exFAT）

### 概念解释规则

遇到新概念或重要概念时，在正文之后附加一段简短解释：

- 如果回复是**中文**，用**英文**补充该概念的英文名称和一句话解释
- 如果回复是**英文**，用**中文**补充一句话解释

示例格式（中文回复）：

> **VAE（变分自编码器 / Variational Autoencoder）**— 负责在像素空间和潜空间之间转换图像的模型组件，相当于 ComfyUI 内部处理结果和最终图片之间的"翻译器"。

示例格式（英文回复）：

> **Variational Autoencoder（VAE，变分自编码器）**— a model component that converts images between pixel space and latent space; think of it as the "translator" between what ComfyUI processes internally and the final image you see.

解释要求：
- 必须同时写出中文名称和英文名称
- 一句话说清楚"它是什么、用来干什么"
- 用类比或比喻，不用堆砌术语
- 不需要展开成段落，点到即止

### IProyal 流量节省规则

Claude Code 会话本身（API 调用 + 文件传输）消耗 IProyal Residential IP 流量。以下行为会加速消耗，需要主动避免：

- **不要读入不必要的大文件**：只读任务需要的部分，用 `offset` + `limit` 参数定位具体行数，不要整文件读入
- **不要把大命令输出直接返回上下文**：日志、安装过程等长输出，只摘取关键行，不要完整展示
- **会话尽量聚焦**：一个会话只做一件事，避免在同一会话里积累过多上下文
- **大文件下载/安装不需要特殊处理**：pip install、git clone 等终端命令走 VeeeVPN，不消耗 IProyal 配额，正常执行即可

## Shared Memory

**Always write new instructions, rules, and memory to `AGENTS.md` only.**

Never modify `CLAUDE.md` or `GEMINI.md` directly - they only import `AGENTS.md`.
This ensures Claude Code, Codex CLI, and Gemini CLI share the same context consistently.

## Project Structure

- `.claude/agents/` - Custom subagents for specialized tasks
- `.claude/skills/` - Claude Code skills (slash commands)
- `.claude/rules/` - Modular rules auto-loaded into context
- `.codex/skills/` - Codex CLI skills
- `.codex/prompts/` - Codex CLI custom slash commands
- `.gemini/skills/` - Gemini CLI skills
- `.gemini/commands/` - Gemini CLI custom slash commands (TOML)
- `.mcp.json` - MCP server configuration
