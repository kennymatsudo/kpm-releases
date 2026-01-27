# KPM - Planning Workbench

A developer's project cockpit for managing work from discovery through execution.

## The Problem KPM Solves

**Planning files don't belong in source code.** Where do project breakdowns, working notes, and task lists live? A separate folder loses the connection to code. Files in the repo risk accidental commits and clutter `.gitignore`.

**Context resets between workflow phases.** Discovery happens in one tool, planning in another, execution in a third. Each phase starts cold—you re-explain, re-establish context, lose the thread.

**Jira operates at the wrong level.** Org trackers optimize for stakeholder visibility. Developers need granularity that matches how they actually think about code. "Add user auth" in Jira is actually 8 things you need to track.

KPM is a **context continuity layer** that keeps your thinking connected across discovery, planning, and execution.

## Download

Download the latest version from the [Releases](https://github.com/kennymatsudo/kpm-releases/releases) page.

**Requirements:** macOS on Apple Silicon (M1/M2/M3/M4)

## Installation

1. Download the `.dmg` file from the latest release
2. Open the DMG and drag KPM to Applications
3. **First launch:** Right-click the app > **Open** > Click **Open** in the dialog

   > The app is not notarized, so macOS will show a warning on first launch. This is a one-time step.

## Requirements

- **Claude Code CLI** - Install with `npm install -g @anthropic-ai/claude-code`
- **Anthropic API key** or Claude Max subscription

## Core Features

### Plan View
Visual canvas for breaking down work into a three-level hierarchy: Project > Feature > Task. Drag cards to organize, set dependencies, track status. Your breakdown lives in KPM's database—connected to repos but not inside them.

### Workspace View
Chat-first interface with Claude for discovery and planning. Claude has context about your project, your plan, and your code. Ask questions, explore approaches, draft plans—context accumulates instead of resetting.

### Development Sessions
When a task is ready for implementation, Claude can propose a dev session. KPM creates an isolated git worktree, spawns Claude Code in a terminal, and passes all the context (task description, code refs, sub-tasks). Work stays sandboxed until you're ready to merge.

### Jira Integration
Import issues from Jira, sync status back when ready. KPM is your local source of truth while working; Jira remains the team's source of truth.

### Confluence Sync
Bidirectional sync between local documents and Confluence pages. Draft locally, push when ready.

## Use Cases

### Breaking Down a Large Feature
You have "Implement OAuth" in Jira. That's actually: research providers, set up routes, handle token refresh, write tests, handle edge cases. Break it down in KPM, track your real progress, update Jira once when done.

### Exploring Before Planning
You need to understand how the auth system works before you can plan changes. Use Workspace to explore with Claude—read code, ask questions, take notes. When you understand the scope, draft a plan. Your discoveries become actionable tasks.

### Parallel Implementation Tracks
Working on multiple independent features? Each can have its own dev session running in an isolated worktree. Switch between terminals, keep work separate until ready to review.

## Example Workflows

### Workflow 1: Discovery to Execution

```
1. Create project in KPM, link your repo
2. Open Workspace, explore the codebase with Claude
   "What's the current auth flow? Where are tokens validated?"
3. When you understand the scope, ask Claude to draft a plan
4. Review the draft, promote it to real plan items
5. Work through tasks—mark complete as you go
```

### Workflow 2: Jira-Driven Development

```
1. Import Jira issue into KPM
2. Break it down into sub-tasks (Jira doesn't need this granularity)
3. For each task, discuss implementation with Claude in Workspace
4. When ready, start a dev session—Claude Code implements in isolated worktree
5. Review changes, commit, push
6. Sync final status back to Jira
```

### Workflow 3: Parallel Feature Development

```
1. Three features to implement, all independent
2. Create plan items for each
3. Start dev session on Feature A—runs in its own worktree/branch
4. While Claude works on A, start session on Feature B
5. Switch between terminals, review progress
6. Each feature stays isolated until you're ready to merge
```

## How It Fits Together

```
┌─────────────────────────────────────────────────────────────────┐
│                     Organization Level                          │
│                   Jira / Linear (team source of truth)          │
└─────────────────────────────────────────────────────────────────┘
                              ↑ sync when ready
┌─────────────────────────────────────────────────────────────────┐
│                     Developer Level                             │
│                        KPM (this tool)                          │
│  • Discovery & exploration    • Progress tracking               │
│  • Planning & breakdown       • Jira/Confluence sync            │
└─────────────────────────────────────────────────────────────────┘
                              ↑ direct access
┌─────────────────────────────────────────────────────────────────┐
│                       Code Level                                │
│                   Claude Code + IDE + Repos                     │
└─────────────────────────────────────────────────────────────────┘
```

## Issues

Report bugs and request features in [Issues](https://github.com/kennymatsudo/kpm-releases/issues).
