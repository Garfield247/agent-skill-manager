# agent-skill-manager

> 🧭 AI Agent 技能全生命周期管理、规范脚手架创建、脱敏审查与跨环境同步发布 Agent Skill。

## 🌟 核心特性 (Features)

- **标准化脚手架生成**：全自动生成符合工业标准的 `SKILL.md`（YAML frontmatter、核心铁律、分层架构规范、调试武器库与 Checklist）。
- **严格合规性审查**：强制脱敏审查、敏感字样检测、Mermaid 4 大防崩语法格式校验。
- **全自动建仓与发布**：GitHub API 自动化建仓、Description 与 Topics 标签自动维护、Conventional Commits 提交。
- **中央索引库双向联动**：自动同步登记至 `agent-skills` 注册表与全局 `GEMINI.md` 路由索引。

## 📦 安装与多 Agent 使用指南 (Installation & Multi-Agent Usage)

本项目遵循开放 Agent 规范，支持在 **Gemini / Antigravity**、**Anthropic Claude**、**Cursor / Codex** 等各类主流 Agent 环境中一键安装与激活：

### 1. Google Antigravity / Gemini Code Assist
- **全局安装（推荐）**：
  ```bash
  git clone git@github.com:Garfield247/agent-skill-manager.git ~/.gemini/config/skills/skill-manager
  ```
- **项目工作区局部引入**：
  ```bash
  mkdir -p .agents/skills
  git clone git@github.com:Garfield247/agent-skill-manager.git .agents/skills/skill-manager
  ```

### 2. Anthropic Claude (Claude Code / Claude Projects)
- **Claude Code (CLI 终端智能体)**：
  克隆至 Claude 全局技能库：
  ```bash
  mkdir -p ~/.claude/skills
  git clone git@github.com:Garfield247/agent-skill-manager.git ~/.claude/skills/skill-manager
  ```
  *或者在项目根目录的 `CLAUDE.md` 中追加引入：*
  ```markdown
  See detailed engineering specifications in: ~/.claude/skills/skill-manager/SKILL.md
  ```
- **Claude Projects (Web / 桌面端)**：
  直接将仓库中的 `SKILL.md` 内容复制并粘贴至 Project 的 **Project Knowledge (项目知识库)** 或 **Custom Instructions (自定义指令)** 中。

### 3. Cursor / GitHub Copilot / OpenAI Codex
- **Cursor (现代 MDC 规则体系)**：
  在项目根目录创建或链接规则：
  ```bash
  mkdir -p .cursor/rules
  # 克隆或软链接为 Cursor 专有规则文件
  git clone git@github.com:Garfield247/agent-skill-manager.git .cursor/rules/skill-manager
  ```
- **GitHub Copilot / Codex**：
  将本技能规范注入 Copilot 指令集：
  ```bash
  mkdir -p .github
  cat << 'EOF' >> .github/copilot-instructions.md
  # 引入本技能核心规则
  EOF
  cat path/to/SKILL.md >> .github/copilot-instructions.md
  ```

## 📄 开源协议 (License)
本项目采用 [MIT License](LICENSE) 授权。
