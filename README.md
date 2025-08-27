# Claude Code Assist

> **Note**: This is an unofficial extension and is not made by or affiliated with Anthropic.

A powerful VS Code extension that enhances your development workflow with Claude Code integration. Browse chat history, review file changes, apply modifications from previous sessions, and manage your coding workflow with comprehensive history visualization.

![Claude Code Assist Demo](./assets/AppVideo.gif)

*See Claude Code Assist in action - browse sessions, view diffs, apply changes, and enhance your development workflow*

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
- **Lunr.js Search Engine**: Fast, intelligent full-text search powered by Lunr.js
- **Advanced Search Index**: Compressed, cached search index for lightning-fast results
- **Smart Query Processing**: Intelligent search with relevance scoring and context awareness
- **Search Highlighting**: Visual highlighting of search terms in results
- **Session Navigation**: Jump directly to specific conversations
- **Quick Access**: Command palette integration for rapid access

### Status Bar Navigation
- **Real-Time File Monitoring**: Status bar integration showing current file change status
- **Quick Navigation**: Navigate between file changes using keyboard shortcuts
- **Loading State Indicators**: Visual feedback during file operations
- **Seamless Workflow**: Integrated navigation without leaving your editor

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
5. **Search History**: Use the search functionality within the extension's side panel
6. **Navigate Files**: Use status bar buttons or keyboard shortcuts (`Ctrl+Shift+]` / `Ctrl+Shift+[`) to navigate between file changes
7. **Quick Access**: Press `Ctrl+Shift+Q` to quickly open the Claude chat side panel

## 📋 Main Commands

### Available in Command Palette (Ctrl+Shift+P)

| Command | Description |
|---------|-------------|
| `Claude Assist: Refresh Sessions` | Reload session data and rebuild search index |
| `Claude Assist: Clear Project Cache` | Clear internal caches (troubleshooting) |
| `Claude Assist: Open Settings` | Access extension settings and configuration |
| `Claude Assist: Open Claude Chat Side Panel` | Open the Claude chat side panel |

### Keyboard Shortcuts

| Shortcut | Command | Description |
|----------|---------|-------------|
| `Ctrl+Shift+]` / `Cmd+Shift+]` | Navigate Next | Navigate to next file change in history |
| `Ctrl+Shift+[` / `Cmd+Shift+[` | Navigate Previous | Navigate to previous file change in history |
| `Ctrl+Shift+Q` / `Cmd+Shift+Q` | Open Side Panel | Open Claude chat side panel |

### Context Menu Commands
Additional commands are available through right-click context menus and the extension's interface:
- Show File Diff
- Apply Changes to Workspace  
- Open File in Editor
- View File Changes


## ⚙️ Configuration

### Settings
- **`claude-history.claudeDirectory`**: Custom path to .claude directory (auto-detected if empty)
- **`claude-history.autoRefreshEnabled`**: Enable automatic refresh for recent sessions (default: true)
- **`claude-history.autoRefreshInterval`**: Time window in hours for auto-refresh (default: 2 hours)
- **`claude-history.enableErrorReporting`**: Enable anonymous error reporting for debugging (default: true)
- **`claude-history.searchIndexCacheSize`**: Maximum size for search index cache in MB (default: 50)

### Customization
Access settings via:
- File → Preferences → Settings → Extensions → Claude Code Assist
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
- The extension loads sessions incrementally with intelligent caching
- Search index is automatically compressed and optimized for large datasets  
- Use "Load More Sessions" to expand history as needed
- Clear project cache if experiencing slowdowns
- Rebuild search index if search performance degrades

**Search not returning expected results**
- Ensure search index has been built (automatic on first use)
- Try rebuilding the search index via "Refresh Sessions"
- Check search query syntax - supports partial matches and fuzzy search
- Clear search cache if results seem outdated

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

See [CHANGELOG.md](./CHANGELOG.md) for detailed release notes.

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for development setup and guidelines.

## ☕ Support the Project

If you find Claude Code Assist helpful and want to support its development, consider supporting me on Polar! You can choose your own amount and help maintain and improve this extension.

**[💝 Support on Polar](https://buy.polar.sh/polar_cl_RdBqIIesUrrdeMywzxK5e6oSKjn3LSzSvALAq4CQDKp)** - Choose your own amount

### 🎁 Supporter Benefits
- **Repository Access**: Supporters get access to the private development repository
- **Collaborator Status**: Become a collaborator and help shape the future of the extension
- **Early Access**: Get early access to new features and beta releases
- **Direct Communication**: Priority support and direct feedback channel


## 📄 License

Apache-2.0 © [yashagldit](https://github.com/yashagldit)

## � Contact & Support

Have questions, suggestions, or want to connect? Reach out to me on Twitter!

**[🐦 Follow me on Twitter/X: @yashagl](https://x.com/yashagl)**

I'm always happy to help with issues, discuss new features, or chat about development!

## �🔗 Links

- [GitHub Repository](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code)
- [Twitter/X: @yashagl](https://x.com/yashagl)

---

**Enhance your development workflow with comprehensive history visualization, file change tracking, and intelligent session management.**