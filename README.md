# KPM

A planning workbench for developers.

## The Problem KPM Solves

- **Context resets every time you switch tools.** Research in one place, plan in another, track in a third, code in a fourth. Each transition starts cold.
- **Trackers are too coarse for real work.** "Add user auth" is one Jira ticket, but actually implementing it means figuring out eight separate things. Jira tracks the ticket — not the thinking underneath it.
- **AI doesn't know your project.** Every chat session starts from scratch — no awareness of your plan, your docs, or what you've already decided.
- **Planning files don't belong in your repo.** Task breakdowns and working notes end up in random markdown files, cluttering `.gitignore` or risking accidental commits.
- **Working on multiple things means juggling branches.** Switching between features means stashing, checking out, re-orienting. Context gets lost every time.

KPM gives you a single place where your plan, your docs, your Jira tickets, and your code all live together. Everything stays connected so nothing gets re-explained or lost.

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

## Features

### Shared Context Across Everything

This is the core idea. Your plan, your project documents, your Jira tickets, and your code are all accessible from every part of KPM. When you're chatting with Claude about an approach, it can read your plan and your code. When you kick off a dev session, Claude Code already has your task breakdown and project docs. Context flows between steps instead of getting copy-pasted or lost.

### AI-Driven Workflow

Claude can handle most of what you'd otherwise do manually — explore your codebase, create plan items, break features into tasks, set dependencies, update statuses, start dev sessions. You work through a chat interface and approve the changes Claude proposes. Or skip the chat and do it all by hand. Both work.

### Visual Planning

Break work into projects, features, and tasks. View them on a canvas, in a tree, or on a kanban board. Drag to organize, set dependencies, group related items. Your breakdown stays in KPM's database — connected to your repos but not cluttering them.

### Development Sessions

Start a dev session and KPM sets up an isolated git worktree, launches Claude Code, and feeds it everything relevant — the task, sub-tasks, code references, and your project docs. Claude starts working in its own branch while your main repo stays clean.

Run multiple sessions at once across different features. Each gets its own terminal, branch, and worktree.

### Agent Teams

Switch to **thorough mode** and Claude doesn't just implement — it gets reviewed. After writing the code, a team of specialized agents runs automatically:

- **Design** — architecture, API contracts, pattern adherence
- **Test** — coverage gaps, regressions, flaky patterns
- **Security** — injection, auth issues, input validation
- **Synthesizer** — deduplicates across reviewers, classifies severity, prioritizes fixes
- **Readability** — naming, structure, clarity

If critical issues are found, Claude fixes them and the reviewers run again. Reviewer prompts are customizable per-project.

### Jira Sync

Import issues from Jira, break them down at whatever granularity you actually need, then sync status back when you're done. You can also export new plan items to Jira as tickets — so work that starts in KPM can flow back into your team's tracker without manual re-entry. KPM handles conflict detection so nothing gets overwritten. Jira stays the team's source of truth — KPM is yours.

### Confluence Sync

Link documents to Confluence pages. Edit locally in markdown, push when ready. Bidirectional sync with conflict resolution.

### Inbox

Capture thoughts quickly from anywhere in the app. KPM enhances your notes in the background — expanding shorthand, categorizing items — so they're ready to act on when you come back to them.

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

1. **Link your repos** and create a project
2. **Explore** — chat with Claude about the codebase, read code, understand scope
3. **Plan** — break work down into features and tasks, manually or through chat
4. **Build** — start dev sessions that run Claude Code in isolated worktrees
5. **Ship** — review changes, sync status back to Jira

## Issues

Report bugs and request features in [Issues](https://github.com/kennymatsudo/kpm-releases/issues).
