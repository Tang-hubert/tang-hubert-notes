# AI Coding Framework

## Overview
Agentic software development methodology using OpenClaw as orchestrator with Codex/Claude Code CLI for actual coding tasks.

## Architecture

### Two-Layer Separation

| Layer | Location | Purpose |
|-------|----------|---------|
| OpenClaw Skills | `~/.npm-global/.../skills/` + `~/.openclaw/workspace/skills/` | ClawhHub tools |
| Worker Roles | `/home/clawuser/openclaw-workspace/workers/` | Hubert's enterprise assets |

### OpenClaw + Codex分工

- **主控 + 策劃**: brtclaw (OpenClaw)
- **尾端高階程式任務**: Codex/Claude Code CLI

OpenClaw's `sessions_spawn` does orchestration, Codex handles actual coding.

## Modular System Prompt Architecture

```
~/.openclaw/workspace/
├── SOUL.md         # Identity core
├── USER.md         # User data
├── AGENTS.md       # Structure carrier (3.4KB, lazy reference)
├── SKILLS.md       # CSO Trigger Index (2.8KB, lazy load)
├── WORKERS.md      # Smart Worker Discovery (3.2KB, lazy load)
└── RULES.md        # Behavior rules (4.9KB, lazy load)
```

**Loading Principle**:
- SOUL + USER + AGENTS: Every session
- SKILLS / WORKERS / RULES: Lazy load on demand

## Workers Lazy Loading

Workers are NOT in system prompt. They are only loaded when:
1. Hubert explicitly specifies
2. Task analysis requires domain expertise
3. Before subagent dispatch

**Discovery Process**: `ls` → keyword match → read profile

## Related Daily Entries
- [2026-04-03](../daily-learnings/2026/04/2026-04-03.md)
