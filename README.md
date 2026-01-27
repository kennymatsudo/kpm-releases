# KPM

A planning workbench for developers.

## The Problem KPM Solves

- **Context resets every time you switch tools.** Research, plan, track, and code all live in different places — each transition starts cold.
- **Trackers are too coarse for real work.** Jira tracks tickets, not the eight sub-problems underneath them.
- **AI doesn't know your project.** Every chat session starts from scratch with no awareness of your plan, docs, or decisions.
- **Planning files don't belong in your repo.** Task breakdowns end up in random markdown files, cluttering `.gitignore` or risking accidental commits.
- **Working on multiple things means juggling branches.** Switching features means stashing, checking out, and re-orienting every time.

KPM gives you one place where your plan, docs, Jira tickets, and code all live together — nothing gets re-explained or lost.

## Download

Get the latest version from the [Releases](https://github.com/kennymatsudo/kpm-releases/releases) page.

**Requirements:** macOS on Apple Silicon (M1/M2/M3/M4)

## Getting Started

1. Download the `.dmg` from the latest release
2. Drag KPM to Applications
3. **First launch:** Right-click the app > **Open** > Click **Open** in the dialog

**You'll also need:**
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code/overview) — `npm install -g @anthropic-ai/claude-code`
- An Anthropic API key or Claude Max subscription

## How It Fits In

```
 Your Team's Tracker (Jira / Linear)
          ^
          | sync when ready
          |
 KPM — your working space
   explore, plan, break down, track
          ^
          | direct access
          |
 Your Code (repos, Claude Code, IDE)
```

KPM sits between your code and your team's tracker. Work at whatever level of detail you need, then surface results upward when ready.

## Typical Workflow

### 1. Link Your Repos

Connect your existing repositories to a project.

- KPM gets read access — it never modifies your repos directly
- Claude can explore your codebase and reference specific files throughout every phase

### 2. Explore

Chat with Claude about your codebase to understand scope before committing to a plan.

- Ask questions, navigate files, take notes — freeform discovery
- Create documents directly in KPM: architecture overviews, research notes, design specs, meeting notes
- Claude drafts documents from your conversation; you review changes in a diff view before accepting
- Documents live as markdown files in your project folder, outside your repo

### 3. Plan

Translate exploration into structured work.

- Break features into tasks manually, or let Claude propose a breakdown you review and approve
- Set dependencies, group related items, organize on a canvas, tree, or kanban board
- Sync plan items bidirectionally with Jira — import issues to break down, or export new items as tickets
- Conflict detection keeps both systems in sync without overwriting

### 4. Build

Start a dev session in one of two ways:

- **From the project** — launch with full context on your plan, docs, and repos. You work directly in the repo and pick what to work on.
- **From a plan item** — click a task and KPM sets up an isolated git worktree, launches Claude Code, and injects the ticket details, sub-tasks, and code references. Claude works in its own branch while your main repo stays clean.

Run multiple sessions in parallel — each gets its own terminal, branch, and worktree.

### 5. Ship

Review changes, commit, and sync status back to Jira.

- Generate stakeholder artifacts — weekly updates, test plans — directly from completed work

## Features

### Shared Context Across Everything

Your plan, documents, Jira tickets, and code are all accessible from every part of KPM.

- Claude can read your plan and code while you chat about an approach
- Dev sessions launch with your task breakdown and project docs already loaded
- Context flows between steps instead of getting copy-pasted or lost

### AI-Driven Workflow

Claude handles what you'd otherwise do manually.

- Explore your codebase, create plan items, break features into tasks, set dependencies, update statuses, start dev sessions
- Work through a chat interface and approve the changes Claude proposes

### Visual Planning

Break work into projects, features, and tasks with multiple views.

- Canvas, tree, or kanban board
- Drag to organize, set dependencies, group related items
- Breakdown stays in KPM's database — connected to your repos but not cluttering them

### Project Documents

Create and manage working documents within your project.

- Architecture docs, research notes, design specs, and more
- Claude drafts and updates documents; you review changes in a diff view before accepting
- Stored as markdown in your project folder, synced to Confluence when needed
- Accessible to Claude across every phase of your workflow

### Development Sessions

KPM sets up an isolated git worktree, launches Claude Code, and feeds it everything relevant.

- Task, sub-tasks, code references, and project docs are injected automatically
- Claude works in its own branch while your main repo stays clean
- Run multiple sessions at once — each gets its own terminal, branch, and worktree

### Agent Teams

Switch to **thorough mode** and Claude doesn't just implement — it gets reviewed. After writing the code, a team of specialized agents runs automatically:

- **Design** — architecture, API contracts, pattern adherence
- **Test** — coverage gaps, regressions, flaky patterns
- **Security** — injection, auth issues, input validation
- **Synthesizer** — deduplicates across reviewers, classifies severity, prioritizes fixes
- **Readability** — naming, structure, clarity

If critical issues are found, Claude fixes them and the reviewers run again. Reviewer prompts are customizable per-project.

### Jira Sync

Bidirectional sync between KPM plan items and Jira tickets.

- Import issues from Jira and break them down at whatever granularity you need
- Export new plan items back to Jira as tickets
- Conflict detection prevents overwrites — Jira stays the team's source of truth

### Confluence Sync

Link documents to Confluence pages.

- Edit locally in markdown, push when ready
- Bidirectional sync with conflict resolution

### Inbox

Capture thoughts quickly from anywhere in the app.

- KPM enhances notes in the background — expanding shorthand, categorizing items
- Ready to act on when you come back to them

## Issues

Report bugs and request features in [Issues](https://github.com/kennymatsudo/kpm-releases/issues).
