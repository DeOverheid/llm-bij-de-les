# .llm/ — Your AI Workspace

A portable, model-swappable AI workspace. Create your persona once, drop it into any project, and every LLM you use will know who you are, how you work, and what the project looks like.

## Key principles

- **Files are truth.** Not chat history, not model memory.
- **Model-agnostic.** Works with any LLM that can read files.
- **Portable.** Copy the folder, copy one bootstrap file, done.
- **Private.** Everything stays local. No cloud sync required.

## How it works

- **File-based** — profile, rules, and project state are stored in plain markdown files, read every session.
- **Persistent defaults** — your preferences and instructions are set once and applied automatically, every time.
- **No reliance on context or memory** — nothing important lives in chat history or model recall.
- **Stored exchanges and decisions** — every session is logged, every decision is recorded for future reference.
- **Quick project scan** — on startup, the LLM reads your state and project overview to get oriented in seconds.
- **Deeper dive if needed** — tiered history means the LLM only digs into detail when the summaries aren't enough.
- **Weight tracking** — every exchange gets an internal weight; the running total tells both you and the LLM when the conversation is getting too long and it's time to checkpoint.
- **Self-correcting** — the LLM logs lessons learned and updates its own rules when things go wrong. But you're always free to grab a hammer and drive a point home — corrections from the user are final and non-negotiable.

## Benefits

- **No need to repeat yourself** — tell the LLM once how you work, it remembers across every conversation.
- **Persistence** — nothing is lost between sessions, even if you close the chat or switch tools.
- **Model-agnostic** — swap between Claude, GPT, Gemini, or local models without losing context.
- **Consistency** — every model follows the same rules, reads the same files, behaves the same way.
- **Better memory** — structured logs beat model recall; the LLM can find exactly what happened and when.
- **No need to re-read every time** — tiered history means the LLM reads summaries first, skips what's irrelevant.

## Setup (5 minutes)

1. **Copy** the `llm/` folder from this repo into your project root. Optionally rename it to `.llm/` if you want it hidden from your file tree.
2. **Move** the right bootstrap file from `llm/00_boot/bootstrap/` to your project root (see table below)
3. **Start a conversation** with your LLM and say: `start session`
4. **Answer the setup questions** — the LLM will walk you through filling in your profile
5. **Done** — say `start session` at the start of every conversation from now on

## Bootstrap files

Copy **one** file from `.llm/00_boot/bootstrap/` to your **project root**:

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

## Prompt keywords

| Keyword           | What it does                                      |
| ----------------- | ------------------------------------------------- |
| `start session`   | Load workspace, scan project, get up to speed     |
| `restart session` | Re-read everything mid-conversation               |
| `end session`     | Wrap up, write summary, update state              |
| `push`            | Commit + push + update project overview           |
| `checkpoint`      | Save full state, prepare for conversation restart |
| `status`          | Show current branch, changes, what's next         |
| `plan:`           | Outline approach, ask for approval, then execute  |
| `explain:`        | Give a thorough, longer explanation               |
| `advise:`         | Review context, list options with pros/cons       |
| `check:`          | Verify something — report only, don't change      |
| `undo`            | Revert the last change (confirm first)            |
