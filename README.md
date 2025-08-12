# Claude History Viewer

A powerful VS Code extension that transforms your Claude Code chat history into an intuitive, organized interface. Browse conversations, review file changes, and track your development journey with ease.

![Claude History Viewer Demo](./assets/AppVideo.gif)

*See Claude History Viewer in action - browse sessions, view diffs, and track your development workflow*

## 🌟 Features

### Smart Session Organization
- **Sidepanel Interface**: Clean, intuitive sidebar panel for browsing chat sessions
- **Project-Based Filtering**: Automatically organizes sessions by project with smart current-project detection
- **Latest Chat Priority**: Recent conversations are highlighted and easily accessible
- **Auto-Refresh**: Automatically updates recent sessions (configurable time window)

### Advanced File Change Tracking
- **GitHub-Style Diffs**: Beautiful, readable diff views showing exactly what changed
- **Multi-Diff Support**: View changes across multiple files simultaneously
- **Native VS Code Integration**: Leverages VS Code's built-in diff viewer
- **Apply Changes**: One-click application of changes to your current workspace
- **File Operations**: Track Read, Write, Edit, and MultiEdit operations from Claude Code

### Powerful Search & Navigation
- **Full-Text Search**: Search across all chat history with instant results
- **Session Navigation**: Jump directly to specific conversations
- **Context-Aware Results**: Search results maintain conversation context
- **Quick Access**: Command palette integration for rapid access

## 🚀 Getting Started

### Prerequisites
- VS Code 1.80.0 or later
- Claude Code CLI installed and configured
- Existing Claude Code chat history (stored in `~/.claude/projects/`)

### Installation
1. Install from the VS Code Extensions marketplace
2. The extension automatically detects your Claude directory
3. Click the Claude History icon in the Activity Bar to start browsing

### Quick Start
1. **Open the Extension**: Click the Claude History icon in VS Code's Activity Bar
2. **Browse Sessions**: Use the "Latest Chat" tab for recent conversations or "Chat History" for all sessions
3. **View Changes**: Click any session to see the conversation and file changes
4. **Review Diffs**: Use "File Changes" to see a commit-style summary with diffs
5. **Search History**: Use Ctrl+Shift+P → "Claude History: Search History" to find specific conversations

## 📋 Main Commands

| Command | Description |
|---------|-------------|
| `Claude History: Open Modern Session Browser` | Focus the main browser panel |
| `Claude History: Search History` | Search across all chat messages |
| `Claude History: View File Changes` | Open detailed file changes panel |
| `Claude History: Show Diff (VS Code Native)` | View file changes in native diff |
| `Claude History: Apply Changes to Workspace` | Apply selected changes to current files |
| `Claude History: Refresh Sessions` | Reload session data |
| `Claude History: Clear Project Cache` | Clear internal caches (troubleshooting) |

## ⚙️ Configuration

### Settings
- **`claude-history.claudeDirectory`**: Custom path to .claude directory (auto-detected if empty)
- **`claude-history.autoRefreshEnabled`**: Enable automatic refresh for recent sessions (default: true)
- **`claude-history.autoRefreshInterval`**: Time window in hours for auto-refresh (default: 2 hours)

### Customization
Access settings via:
- File → Preferences → Settings → Extensions → Claude History Viewer
- Or search for "Claude History" in VS Code settings

## 🔧 Troubleshooting

### Common Issues

**"No Claude directory found"**
- Ensure Claude Code CLI is installed and has been used at least once
- Check that `~/.claude/projects/` directory exists
- Manually set the Claude directory in extension settings

**Sessions not loading**
- Click "Refresh Sessions" in the panel
- Check if your Claude directory path is correct in settings
- Verify that JSONL files exist in your Claude projects folders

**Diffs not showing correctly**
- Ensure the files exist in your current workspace
- The extension tries to match files by relative path from project root
- For missing files, you'll be prompted to create them

**Performance issues with large history**
- The extension loads sessions incrementally
- Use "Load More Sessions" to expand history as needed
- Clear project cache if experiencing slowdowns

### Data Privacy
- **100% Local**: All data processing happens locally on your machine
- **No External Calls**: The extension never sends data to external servers
- **Read-Only by Default**: Only reads your existing Claude history files
- **Workspace Integration**: Only accesses your current VS Code workspace for file operations

## 🏗️ Architecture Overview

The extension is built with a modular architecture:

- **Data Layer**: JSONL parsers for reading Claude Code chat history
- **UI Layer**: Modern webview panels with GitHub-style interfaces  
- **Services**: File watching, incremental parsing, and project mapping
- **Utilities**: Diff rendering, file operations, and search functionality

## 📝 Version History

See [CHANGELOG.md](./claude-history-viewer/changelog.md) for detailed release notes.

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](./claude-history-viewer/CONTRIBUTING.md) for development setup and guidelines.

## 📄 License

Apache-2.0 © [yashagldit](https://github.com/yashagldit)

## 🔗 Links

- [GitHub Repository](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code)

---

**Enhance your Claude Code development workflow with rich history visualization and seamless file change tracking.**