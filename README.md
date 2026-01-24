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

---

### build

Feature development pipeline for building major features. Manages a 4-phase workflow:

1. **Research** - Deep exploration of a feature idea
2. **Implementation** - Create phased implementation plan
3. **Progress** - Set up progress tracking
4. **Phase execution** - Implement each phase with tracking

**Subcommands:**

```
/build research [name]        Deep research on a feature idea
/build implementation [name]  Create phased implementation plan
/build progress [name]        Set up progress tracking
/build phase [n] [name]       Execute implementation phase n
/build status [name]          Show status and next steps
```

**Example workflow:**

```
/build research chat-interface
/build implementation chat-interface
/build progress chat-interface
/build phase 1 chat-interface
```

---

### conductor-setup

Configure a Rails project to work with [Conductor](https://conductor.app), the Mac app for parallel coding agents. Creates:

- `conductor.json` - Project configuration
- `bin/conductor-setup` - Setup script for worktrees
- `script/server` - Server script with port/Redis isolation
- Updates Rails config files to use `ENV['REDIS_URL']`

**Example usage:**

```
Set up this project for Conductor
```

---

### favicon

Generate a complete set of favicons from a source image. Auto-detects project type (Rails, Next.js, Vite, static HTML, etc.) and places files in the correct location.

**Generates:**
- `favicon.ico` (multi-resolution: 16x16, 32x32, 48x48)
- `favicon-96x96.png`
- `apple-touch-icon.png` (180x180)
- `web-app-manifest-192x192.png`
- `web-app-manifest-512x512.png`
- `site.webmanifest`
- `favicon.svg` (if source is SVG)

**Requires:** ImageMagick v7+ (`brew install imagemagick`)

**Example usage:**

```
/favicon logo.png
```

```
/favicon assets/icon.svg
```

## Compatibility

These skills work with any Agent Skills Standard-compatible tool:

- Claude Code (Anthropic)
- Cursor
- Gemini Code Assist (Google)
- GitHub Copilot (Microsoft)

## License

MIT
