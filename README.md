# .llm/ — Your AI Workspace

A portable, model-swappable AI workspace. Drop it into any project, answer a few questions, and every LLM you use will know who you are, how you work, and what the project looks like.

## Setup (5 minutes)

1. **Copy** the `llm/` folder from this repo into your project root and rename it to `.llm/`
2. **Move** the right bootstrap file from `.llm/00_boot/bootstrap/` to your project root (see table below)
3. **Start a conversation** with your LLM and say: `start session`
4. **Answer the setup questions** — the LLM will walk you through filling in your profile
5. **Delete** the bootstrap setup instructions (they're one-time only)
6. **Done** — say `start session` at the start of every conversation from now on

## Bootstrap files

Copy **one** file from `.llm/00_boot/bootstrap/` to the correct location:

| Tool           | Copy to (project root)            |
| -------------- | --------------------------------- |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Claude Code    | `CLAUDE.md`                       |
| Cursor         | `.cursor/rules/llm.md`            |
| Windsurf       | `.windsurfrules`                  |
| Generic/Other  | `AGENTS.md`                       |

## What's inside

```
.llm/
  00_boot/         How the LLM starts up — loading order, keywords, session behaviour
  01_profile/      Who you are, your rules, your preferences
  02_state/        What's happening now — current focus, next steps
  03_plans/        Structured plans for work in progress
  04_overview/     Auto-generated project tree + tech stack (LLM fills this)
  05_experience/   Lessons learned, important facts, decisions
  06_history/      Tiered: exchanges → sessions → timeline
  07_skills/       Reusable workflows you can teach the LLM
  08_knowledge/    Reference docs you want the LLM to know about
  09_archive/      Old stuff you don't need active but want to keep
```

## How it works

- You say `start session` → the LLM reads your profile, checks what's active, scans your project
- Files are the source of truth — not chat history, not model memory
- When you switch models, the new one reads the same files and picks up where you left off
- The LLM writes exchange logs and session summaries so nothing gets lost

## Prompt keywords

| Keyword           | What it does                                      |
| ----------------- | ------------------------------------------------- |
| `start session`   | Load workspace, scan project, get up to speed     |
| `restart session` | Re-read everything mid-conversation               |
| `push`            | Commit + push + update project overview           |
| `checkpoint`      | Save full state, prepare for conversation restart |
| `status`          | Show current branch, changes, what's next         |
| `end session`     | Wrap up, write summary, update state              |

## Key principles

- **Files are truth.** Not chat history, not model memory.
- **Model-agnostic.** Works with any LLM that can read files.
- **Portable.** Copy the folder, copy one bootstrap file, done.
- **Private.** Everything stays local. No cloud sync required.
