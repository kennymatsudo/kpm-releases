# KPM - Planning Workbench

A developer's project cockpit for managing projects from planning through execution.

## Download

Download the latest version from the [Releases](https://github.com/kennymatsudo/kpm-releases/releases) page.

| Platform | Download |
|----------|----------|
| macOS (Apple Silicon) | `KPM-*-arm64.dmg` |
| macOS (Intel) | `KPM-*-x64.dmg` |
| Windows | `KPM-*-Setup.exe` |
| Linux | `KPM-*.AppImage` or `KPM-*.deb` |

## Installation

### macOS

1. Download the `.dmg` file for your Mac (arm64 for Apple Silicon, x64 for Intel)
2. Open the DMG and drag KPM to Applications
3. **First launch:** Right-click the app → **Open** → Click **Open** in the dialog

   > The app is not notarized, so macOS will show a warning on first launch. This is a one-time step.

### Windows

1. Download the `.exe` installer
2. Run the installer and follow the prompts

### Linux

**AppImage:**
```bash
chmod +x KPM-*.AppImage
./KPM-*.AppImage
```

**Debian/Ubuntu:**
```bash
sudo dpkg -i KPM-*.deb
```

## Auto-Updates

KPM checks for updates automatically. When a new version is available, you'll see a banner at the top of the app with options to download and install.

## Requirements

- **Claude Code CLI** - Install with `npm install -g @anthropic-ai/claude-code`
- **Anthropic API key** or Claude Max subscription

## Features

- **Plan View** - Visual canvas for breaking down work into hierarchical tasks
- **Workspace View** - Chat-first interface with Claude for planning and document generation
- **Jira Integration** - Import issues, sync status, and export new tickets
- **Confluence Sync** - Bidirectional sync between local docs and Confluence pages
- **Dev Sessions** - Launch Claude Code in git worktrees for isolated implementation
- **Document Generation** - Create test plans, weekly updates, and other artifacts with AI

## Issues

Report bugs and request features in [Issues](https://github.com/kennymatsudo/kpm-releases/issues).
