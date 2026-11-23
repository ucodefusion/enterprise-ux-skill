# Enterprise UX Skill

Reusable enterprise UI/UX design and review guidance. Start with [SKILL.md](SKILL.md).

## Installation by AI agent

From your project root, run the command for your agent. These commands clone the complete skill into a new directory; if it already exists, review changes before updating it with `git pull` inside that directory.

| Agent | Project-level directory | Personal directory |
|---|---|---|
| OpenAI Codex | `.agents/skills/` | `~/.agents/skills/` |
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |
| Cursor | `.cursor/skills/` | `~/.cursor/skills/` |
| GitHub Copilot (VS Code) | `.github/skills/` | `~/.copilot/skills/` |
| Gemini CLI | `.gemini/skills/` | `~/.gemini/skills/` |
| OpenCode | `.opencode/skills/` | `~/.config/opencode/skills/` |

### Codex

```bash
mkdir -p .agents/skills
git clone https://github.com/ucodefusion/enterprise-ux-skill.git .agents/skills/enterprise-ux-skill
```

### Claude Code

```bash
mkdir -p .claude/skills
git clone https://github.com/ucodefusion/enterprise-ux-skill.git .claude/skills/enterprise-ux-skill
```

### Cursor

```bash
mkdir -p .cursor/skills
git clone https://github.com/ucodefusion/enterprise-ux-skill.git .cursor/skills/enterprise-ux-skill
```

### GitHub Copilot

```bash
mkdir -p .github/skills
git clone https://github.com/ucodefusion/enterprise-ux-skill.git .github/skills/enterprise-ux-skill
```

### Gemini CLI

```bash
mkdir -p .gemini/skills
git clone https://github.com/ucodefusion/enterprise-ux-skill.git .gemini/skills/enterprise-ux-skill
```

### OpenCode

```bash
mkdir -p .opencode/skills
git clone https://github.com/ucodefusion/enterprise-ux-skill.git .opencode/skills/enterprise-ux-skill
```

For personal installation, substitute the personal directory above. Restart or refresh the agent if necessary. Ask: **Use enterprise-ux-skill to audit this screen and propose improvements before editing.** Gemini CLI also supports `gemini skills install https://github.com/ucodefusion/enterprise-ux-skill`.

For other agents, clone the repository anywhere accessible and explicitly ask the agent to read `SKILL.md` and its referenced files. For chat-only assistants, upload the Markdown files and ask the assistant to apply them; native automatic discovery is not guaranteed.

## Documentation

- [Codex](https://developers.openai.com/codex/skills/)
- [Claude Code](https://code.claude.com/docs/en/skills)
- [Cursor](https://cursor.com/docs/skills)
- [GitHub Copilot](https://code.visualstudio.com/docs/agent-customization/agent-skills)
- [Gemini CLI](https://geminicli.com/docs/cli/skills/)
- [OpenCode](https://opencode.ai/docs/skills/)

No runtime dependencies are required. Agent-specific installation and discovery have not been tested locally.
