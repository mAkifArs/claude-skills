# My Claude Code Skills

A collection of custom skills for Claude Code.

## Usage

Clone this repo to your Claude skills directory:

```bash
git clone https://github.com/YOUR_USERNAME/claude-skills ~/.claude/skills
```

## Available Skills

| Skill | Command | Description |
|-------|---------|-------------|
| Create React App | `/create-react-app` | Scaffold a React + TypeScript app with Vite |
| Create Next.js App | `/create-next-app` | Scaffold a Next.js app with TypeScript + Tailwind |
| Setup Tailwind | `/setup-tailwind` | Add Tailwind CSS to existing project |
| Quick API | `/quick-api` | Create Express.js API with TypeScript |
| React Best Practices | `/react-bp` | Review, reference, and refactor React code |

## Adding New Skills

Create a `.md` file with YAML frontmatter:

```yaml
---
name: skill-name
description: What it does
invocation: /skill-name
---

# Instructions for Claude...
```
