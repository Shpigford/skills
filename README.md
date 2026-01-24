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

| Skill | Description |
|-------|-------------|
| [build](#build) | Feature development pipeline - research, plan, track, implement |
| [conductor-setup](#conductor-setup) | Configure Rails projects for Conductor |
| [favicon](#favicon) | Generate favicon sets from source images |
| [issues](#issues) | Create, list, and view GitHub issues |
| [new-rails-project](#new-rails-project) | Create opinionated Rails 8 + React projects |
| [readme](#readme) | Generate comprehensive project documentation |

---

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

---

### issues

Interact with GitHub issues using the `gh` CLI. Create, list, and view issues with guided prompts.

**Actions:**
- **Create** - Open new issues with title, body, labels (guides you through bug reports vs features)
- **List** - View open issues with filters (all, assigned to me, by label)
- **View** - See details of a specific issue by number

**Requires:** GitHub CLI (`gh`) authenticated

**Example usage:**

```
/issues
```

---

### new-rails-project

Create a new Rails project with an opinionated modern stack:

- **Rails 8** with PostgreSQL (UUID primary keys, timestamptz)
- **Inertia.js + React 19** with TypeScript
- **Vite 5** for frontend bundling
- **Tailwind CSS 4**
- **Sidekiq 8** with Redis for background jobs
- **Redis** for sessions and caching

Includes testing setup (minitest, mocha, VCR) and code quality tools (RuboCop, Brakeman).

**Example usage:**

```
/new-rails-project my-app
```

## Compatibility

These skills work with any Agent Skills Standard-compatible tool:

- Claude Code (Anthropic)
- Cursor
- Gemini Code Assist (Google)
- GitHub Copilot (Microsoft)

## License

MIT
