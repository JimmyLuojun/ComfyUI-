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
