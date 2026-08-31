

# Claude Code and Codex Assist — History, Diff & Usage Analytics for VS Code, Cursor & more

> **Note**: This is an unofficial extension and is not made by or affiliated with Anthropic, OpenAI, SST/OpenCode, xAI/Grok, or GitHub.

Browse your **Claude Code**, **Codex**, **OpenCode**, **Grok**, and **GitHub Copilot** chat history right inside VS Code — view file diffs, search across every conversation, track token usage and cost, and resume past sessions without leaving the editor. It doubles as a usage tracker: a single dashboard shows cost per model, quota burn-down, and weekly reset history across all your AI assistants. Ever wondered which AI conversation changed a file? The File Timeline is git blame for AI edits: pick a file, see every session and prompt that touched it, and open the exact diff.

**🤖 Works with all five assistants:**
- **Claude Code** — `~/.claude/projects/`
- **Codex** — `~/.codex/sessions/`
- **OpenCode** — `~/.local/share/opencode/`
- **Grok** — `~/.grok/`
- **GitHub Copilot** — Copilot CLI and VS Code chat sessions

Sessions from all five appear in one unified list with badges and logos that tell them apart. A built-in **MCP server** even lets the assistants share context with each other — continue your last Codex session from Claude Code, or ask Grok what a past Claude session changed.

**🌐 UI languages:** English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Deutsch | Français | Español

## 🎬 Feature Demos

### 📊 Usage Analytics
Track subscription quota, model usage, weekly reset history, and token trends across Claude Code, Codex, OpenCode, Grok, and Copilot in a single dashboard.

![Usage Analytics](./assets/usage-analytics.gif)

### 📚 Chat History & Diff Viewer
Browse sessions with GitHub-style diffs and one-click file changes.

![Chat History & Diff Viewer](./assets/session-browser.gif)

### ⏱️ File History Timeline
**git blame, but for AI conversations.** Open any file and the timeline shows every session that edited it — expand a session to see the exact prompt and its diff, across Claude Code, Codex, OpenCode, Grok, and Copilot.

![File History Timeline](./assets/timeline-demo.gif)

### 🔍 Full-Text Search
Search across all conversations with instant, session-grouped results — including boolean operators (`AND` `OR` `NOT`), `exact:` phrases, `re:` regex queries, and `me:`/`ai:` scopes to search only your prompts or only the AI's replies.

![Full-Text Search](./assets/search-demo.gif)

### ✅ Review Changes
See every file change from a conversation in one place.

![Review Changes](./assets/review-changes.gif)


## 🌟 Features

### Sessions & History
- **Unified history** for Claude Code, Codex, OpenCode, Grok, and GitHub Copilot, organized by project with current-project detection
- **Quick actions & keyboard navigation** — pin, resume, or delete from a session row; move with arrow keys, open with Enter, remove with Delete
- **Project context menu** — right-click a project header to pin it, hide it, reveal it in your file manager, or open it in a new window
- **Hide individual sessions** — declutter the list without deleting anything; hidden sessions collect in the Hidden tab, grouped by project, with one-click unhide or bulk hide via multi-select
- **Rich transcript rendering** — markdown with syntax-highlighted code, Mermaid diagrams with zoom and export, and LaTeX math typeset offline with KaTeX (copying rendered math gives you the TeX source back)
- **Live search filter** to narrow the list as you type
- **Model filters, pinned projects, and pin & rename** help keep large histories tidy and easy to scan
- **Resume** any conversation in the terminal, desktop app, or VS Code — or copy the command to run elsewhere
- **Fork** a conversation from any message to explore an alternative without touching the original `Pro`
- **Format converter** between Claude and Codex, resuming straight into the target assistant `Pro`
- **Auto-refresh** keeps recent sessions up to date while they're still changing
- **Cleaner history list UI** with a more minimal visual style that keeps long session lists easier to scan

### Archiving & Markdown Sync
- **Session Archive** — Claude and Codex eventually clean up old transcripts; archiving keeps a full-fidelity copy safe in its own folder, browsable from a dedicated **Archived** tab. Viewing and restoring archived sessions is always free. `Pro` to archive
- **Markdown export** of full sessions with customizable metadata `Pro`
- **Markdown sync** — exported sessions can be committed to git, moved between devices, imported back with file changes intact, or resumed as a native session (even across operating systems)
- **Bulk actions** — select multiple sessions to export or delete them together `Pro`

### File Changes & Diffs
- **GitHub-style diffs** with syntax highlighting and multi-file support
- **Review Changes view** — see every file change from a conversation in one place
- **Apply, undo, or reapply** changes to your workspace with one click
- **File history timeline** — git blame for AI conversations: the timeline auto-follows the active editor and lists every session that edited the file, then drill into any session to read the exact prompt and open its diff (or right-click a file to open the timeline)

### Search
- **Indexed or direct search** — choose speed (SQLite full-text) or privacy (search files directly, nothing stored separately)
- **Search operators** — combine terms with `AND` / `OR` / `NOT`, match literal phrases with `exact:`, use regular expressions with `re:pattern`, or scope a search to just your prompts (`me:`) or just the assistant's replies (`ai:`). Pick a scope or match mode from the dropdown at the left of the search bar instead of typing anything — the placeholder tells you what the current selection searches
- **Session-grouped results** with cost, token, and message counts, plus highlighted matches

### ccassist MCP Server — share context between assistants
- **Local MCP server** — the extension can host a lightweight local MCP server so Claude Code, Codex, Grok, OpenCode, and Cursor can query your session history from inside any of them (loopback only, off by default)
- **Continue work across tools** — say *"continue my last Codex session"* in Claude Code (or vice versa) and the agent pulls a distilled handoff block: recent turns, session summary, and what changed
- **One-click setup** — run **Set up ccassist (MCP + Skill)** from the side panel's MCP page or the Command Palette; it registers the server with each CLI and installs a `ccassist` skill that teaches agents when and how to use it
- **Seven tools** — `search_sessions`, `list_recent_sessions`, `get_context`, and `get_session` for finding and loading past work, plus `grep_sessions` (literal transcript scan including tool outputs), `get_session_changes` (per-file summaries or reconstructed diffs), and `get_file_sessions` (which sessions touched a file) `Pro`
- **Private by design** — everything stays on your machine; the server binds to localhost only, and a `workspaceOnly` setting can restrict it to sessions from the current workspace

### Analytics & Cost Tracking
- **Dashboard** with usage statistics, activity timelines, and cost trends
- **Quota tracking** — live Claude/Codex quota cards, burn-down chart, weekly reset history, and weekly summary, with per-model breakdowns including Sonnet, Opus, and Fable where available
- **Model usage charts** to show which models are driving your activity and cost over time
- **Detailed cost analysis** across all supported Claude, OpenAI, OpenCode, Grok, and Copilot models, including cache-token insights
- **Per-session analytics** — context window usage over time (how full the context got, turn by turn), compaction events marked on the timeline, peak context vs. the model's limit, and cache-miss turns
- **Status bar quota indicator** with quick access to the dashboard

## 💎 Pricing

Free for everyday use. A few advanced features require Pro.

|   | Free | Pro |
|---|---|---|
| Browse recent sessions | ✓ (last 7 days) | ✓ (unlimited) |
| Search, diffs, dashboard | ✓ (recent) | ✓ (unlimited history) |
| File timeline | ✓ (last 3 days) | ✓ (all sessions) |
| Markdown export & bulk actions | — | ✓ |
| Session archiving | — | ✓ |
| Session forking & format conversion | — | ✓ |
| ccassist MCP server | ✓ (last 7 days, core tools) | ✓ (full history + grep/diff tools) |
| Devices | 2 | 5 |

See [ccassist.dev](https://ccassist.dev) for current pricing and refund policy.

## 🔒 Privacy

Chat content stays on your machine — the extension reads supported local assistant history folders and stores everything in a local SQLite database. You can verify with any network proxy: no chat text, file content, or diffs are ever sent.

What is sent by default: an anonymized device ID, OS/extension version, and aggregated usage counters (e.g. "session opened", "search ran"). Error reports include error messages and stack traces, never chat content. Both can be turned off in extension settings (`enableErrorReporting`, `enableUsageStatsSharing`).

## 🚀 Getting Started

**Prerequisites:** VS Code 1.80.0+ and an existing history from Claude Code, Codex, OpenCode, Grok, and/or GitHub Copilot.

1. Install from the VS Code Extensions marketplace
2. The extension auto-detects your Claude, Codex, OpenCode, Grok, and Copilot history
3. Click the CCAssist icon in the Activity Bar to start browsing, or press `Ctrl+Shift+Q` to open the side panel

Click any session to see the conversation and its file changes, use **File Changes** for a commit-style diff summary, and open the **Dashboard** tab for cost and quota analytics.

## ⌨️ Commands & Shortcuts

Open the Command Palette (`Ctrl/Cmd+Shift+P`) and search for **CCAssist** — refresh sessions, open the dashboard, refresh API usage quota, open the side panel, and more.

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd+Shift+]` | Next file change |
| `Ctrl/Cmd+Shift+[` | Previous file change |
| `Ctrl/Cmd+Shift+Q` | Open side panel |
| `Ctrl+Alt+;` | Recent file changes (quick pick) |

Additional actions (show diff, apply changes, open file, view file changes, show in timeline) are available via right-click context menus.

## ⚙️ Configuration

Access via **Settings → Extensions → Claude Code Assist**, or search "Claude History" in VS Code settings. Useful options include:

- **`claude-history.claudeDirectory`** — custom `.claude` path (auto-detected if empty)
- **`claude-history.archiveDirectory`** / **`claude-history.export.directory`** — where archived and exported sessions are stored
- **`claude-history.autoRefreshEnabled`** / **`autoRefreshInterval`** — auto-refresh for recent sessions
- **`claude-history.dateFormat`** — ISO or your system's regional format
- **`claude-history.resume.defaultTargetClaude`** / **`defaultTargetCodex`** — where sessions resume by default
- **`claude-history.statusBar.showApiUsage`** — show the quota indicator
- **`claude-history.mcp.enabled`** / **`mcp.port`** / **`mcp.providers`** / **`mcp.workspaceOnly`** — host the ccassist MCP server, choose its port, pick which CLI histories it exposes, and optionally scope it to the current workspace
- **`claude-history.enableErrorReporting`** / **`enableUsageStatsSharing`** — toggle anonymous reporting

## 🔧 Troubleshooting

**"No Claude, Codex, OpenCode, Grok, or Copilot directory found"** — make sure the relevant assistant has been used at least once and the directory exists, or set a custom path in settings.

**Sessions not loading** — click **Refresh Sessions** and verify your directory paths.

**Diffs not showing correctly** — the extension matches files by relative path from the project root; make sure the file exists in your current workspace.

**Performance with large history** — sessions load incrementally with caching; use **Clear Project Cache** or rebuild the search index if things slow down.

The extension uses SQLite via WebAssembly, so it works identically on Windows, macOS (Intel & Apple Silicon), and Linux from a single build.

## 📝 Version History

See [CHANGELOG.md](./CHANGELOG.md) for detailed release notes.

## 📄 License

Proprietary — see [LICENSE](./LICENSE) for terms. The extension is free to use but the source code is not open source.

## Contact & Support

Questions, suggestions, or just want to connect? Reach out!

**📧 Email:** yash@ccassist.dev
**🐦 Twitter/X:** [@yashagl](https://x.com/yashagl)

## 🔗 Links

- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [GitHub Repository](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) · [Codex](https://github.com/openai/codex) · [OpenCode CLI](https://opencode.ai/) · [Grok](https://grok.com/) · [GitHub Copilot](https://github.com/features/copilot)

---

**Enhance your workflow with comprehensive history, file-change tracking, and session management across Claude Code, Codex, OpenCode, Grok, and GitHub Copilot.**
