# Skills

Agent Skills for AI coding assistants. These skills follow the [Agent Skills Standard](https://github.com/anthropics/agent-skills-standard) and work with Claude Code, Cursor, Gemini Code Assist, GitHub Copilot, and other compatible tools.

## Installation

```bash
npx skills add Shpigford/skills
```

Or manually:

```bash
git clone https://github.com/Shpigford/skills.git ~/.skills/shpigford
```

## Available Skills

### readme

Creates comprehensive README.md documentation for projects. Performs deep codebase exploration before writing, covering:

- Local development setup (step-by-step)
- Architecture overview with directory structure and data flow
- Environment variables reference
- Deployment instructions (auto-detects platform)
- Troubleshooting common issues

**Triggers:** "write readme", "create readme", "document this project", "project documentation"

**Example usage:**

```
Write a readme for this project
```

```
Create comprehensive documentation for this codebase
```

## Compatibility

These skills work with any Agent Skills Standard-compatible tool:

- Claude Code (Anthropic)
- Cursor
- Gemini Code Assist (Google)
- GitHub Copilot (Microsoft)

## License

MIT
