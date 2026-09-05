# Changelog

All notable changes to the Claude Code and Codex Assist extension will be documented in this file.

## [0.7.1] - 2026-09-05

### Added

- **Weekly Digest Tab** - A new side panel tab summarizes your last 7 days of AI coding: sessions, tokens, cost, active days, a day-by-day chart, and your top tools and projects, compared against the week before. Step back through earlier calendar weeks, and get a once-a-week reminder when a fresh digest is ready.
- **Share Card** - Turn today's, this week's, this month's, or a single project's usage into a shareable image you can copy or save. Everything is rendered locally from your own history; nothing is uploaded.
- **Branch and Worktree Filter** - Narrow the history list to sessions from a specific git branch or worktree, alongside the existing source and model filters.
- **Activity Summary per Turn** - Conversations now show what each turn did at a glance: commands run, files read, searches, and tools used, with collapsible detail rows and expand/collapse-all controls.
- **Reasoning Effort in Analytics** - Session analytics and the day-by-day dashboard breakdown now split usage by model and reasoning effort, including thinking tokens, for Claude and Codex sessions.
- **Inline Local Images** - Images referenced by local path in transcripts now render inline in the conversation view.


### Improved

- **Faster Startup and Sidebar** - The extension starts faster with a compiled code cache, the sidebar re-renders less and reuses more of its UI, redundant file watchers were removed, and live polling pauses while the window is unfocused.
- **Session Notices When Resuming** - Resuming a session that is already running in a terminal now tells you so and offers to fork instead.
- **Clearer System Events** - Conversation system events now offer a "show result" link, and task notifications are handled more consistently.

### Fixed

- **Streamed Message Token Totals** - Token usage for streamed assistant messages is no longer counted twice in conversation and analytics views.
- **Stale File Changes in Live Sessions** - Live session refreshes now keep previously loaded file changes instead of briefly dropping them.
- **Effort Grouping** - Reasoning effort values that differ only by case no longer split into separate rows in usage tables.
- **Experiment Toggles After Updates** - Turning an experiment on or off right after an in-place extension update now prompts for a window reload instead of failing silently.

## [0.7.0] - 2026-08-31

### Added

- **Revamped Side Panel** - The side panel has been redesigned with tab-based navigation, making it faster and cleaner to switch between history, account insights, settings, hooks, MCP, skills, memories, plans, and experiments.
- **Account Tab** - Check plan usage, quota burn-down, recent activity, daily usage, account status, and device details directly from the side panel.
- **Real-Time Hooks Tab** - Set up and manage live session status for Claude, Codex, and Grok, so the history list can show when an agent is working, waiting for permission, or finished.
- **Experiments Tab** - Try upcoming features and vote on whether they should stay, including a customizable quota health bar, hidden session tags, and quicker Account access from the status bar.
- **Activity in Other Projects** - When viewing one project, a banner now alerts you to active or unread sessions elsewhere and takes you back to the full list.
- **Per-Model Usage Breakdown** - Expand each day in the analytics dashboard to see usage and cost totals for individual models.

### Improved

- **More Complete File Change History** - File changes made through shell commands, PowerShell, loops, glob patterns, and subagents are detected more reliably across supported assistants.
- **Faster File Change Views** - Large sessions and large file changes now open with less processing and memory use, while unchanged sessions reuse previously loaded results.
- **Cleaner History Controls** - Project, source, model, sorting, grouping, and display controls are more compact and easier to navigate, with project actions available even when viewing a single project.
- **Cleaner Conversation Copying** - Copied messages keep useful formatting without carrying VS Code theme colors or backgrounds into other apps.

### Fixed

- **File Change Accuracy** - Reduced duplicate, incorrectly attributed, and missing file changes, including Windows paths, failed shell commands, and overlapping agent activity.
- **Codex Quota Cards** - Codex usage cards now adapt to the windows available on the current plan instead of showing empty statistics.

## [0.6.9] - 2026-08-21

### Added

- **Offline Premium Activation** - Premium can now be activated with a code from ccassist.dev, so firewalled or restricted editor environments can unlock Premium without the editor reaching the server.

### Improved
- **Faster Large History Scans** - Search and file-change discovery now do less unnecessary parsing, making large histories and shell-heavy sessions faster to process.
- **Lower Memory Use on Big Histories** - Session caches are now kept bounded so long-running use and very large histories stay more responsive.
- **Shell Edit File Cards** - File cards now better explain changes made by shell commands, including clearer badges, notes, and command context when an exact diff cannot be reconstructed.
- **More Accurate Shell-Generated Diffs** - More shell-based file writes and edits are detected and shown in the conversation instead of being hidden as plain terminal output.

## [0.6.8] - 2026-08-16


### Improved
- **More Reliable History Search** - History search now consistently searches the actual session files, so fresh installs and rebuilt indexes no longer miss message results.
- **Cleaner Onboarding Experience** - The welcome flow is simpler, more native to VS Code, localized, and works better when no sessions are found yet.

### Fixed
- **Search Box Consistency** - Fixed cases where clicking a recent search or searching immediately after typing could jump back to an older query.
- **Claude Session Discovery** - Fixed searches on machines where the writable index folder is separate from the real Claude history folder.

## [0.6.7] - 2026-08-13

### Added

- **Advanced Deep Search Options** - Deep search now has a clearer Advanced panel with labeled options for author scope, match mode, tool output, and subagent transcripts.
- **Tool Output and Subagent Search** - Deep search can now include tool inputs/results and subagent transcripts when you need to find details that are not in the main chat messages.
- **Priority Section Control** - You can now hide the Priority section from the history list.

### Improved
- **Clearer Deep Search Feedback** - Search results now show how many files were scanned and surface scan failures instead of looking like a clean “no results” response.
- **Better Priority Session Updates** - Sessions that appear in both Priority and date sections now keep active, unread, title, and live-status indicators in sync across both rows.

### Fixed
- **Deep Search Fallback Reliability** - Fixed deep search on machines where the search index directory falls back to an alternate location, including Windows setups where searches could incorrectly return zero results.
- **Deep Search Provider Resilience** - If one assistant source cannot be scanned, deep search now continues with the remaining available sources instead of failing the whole scan silently.

## [0.6.6] - 2026-08-08

### Added

- **Session File Sizes** - Session file size is now stored, backfilled for existing history, shown in the history list, and available as a sort option.
- **Smarter Project Session Loading** - Project groups can load more sessions on demand, with clearer progress when a project has more history than is currently shown.

### Improved
- **Faster Large Histories** - History loading, project grouping, search results, and session pagination are more efficient for users with many sessions.
- **Better Search Pagination** - Search and history results now report loaded vs. total sessions more clearly and load additional results more predictably.
- **More Reliable Project Search** - Project-filtered search and file timelines now match project paths more consistently, including paths with dots or encoded workspace names.
- **Smoother Conversation Scrolling** - Long conversation views scroll more predictably, with fewer jumps and less header flicker while reading.
- **More Stable OpenCode Refresh** - OpenCode session refresh and related parser behavior are more reliable during live updates.

## [0.6.4] - 2026-08-04

### NEW ccassist MCP
- **Local MCP Server** - ccassist can expose your local chat history to supported AI clients so they can search sessions, pull context, inspect changes, and continue work from past sessions. Off until you turn it on.
- **Guided MCP Setup** - The MCP page introduces itself on first visit and walks you through turning the server on, registering your CLIs, and installing the skill in one step. Reopen the walkthrough any time from the "?" button.

### Added
- **Cursor CLI Session Support** - Browse Cursor CLI sessions alongside Claude, Codex, OpenCode, Grok, and Copilot, including diffs, search, agents view, analytics, source filters, and live refresh.
- **Session Tags and Notes** - Add tags and notes to sessions, filter history by tags, search with `tag:`, and optionally include tags/notes in Markdown exports.
- **Session Read State** - History activity badges now remember which sessions you have opened, including across VS Code windows.

### Improved
- **Cleaner Long Conversations** - Completed work can collapse behind a concise “Worked for” summary, making large sessions easier to scan.
- **Staged Project Session Reveal** - Large project groups now reveal sessions progressively with clearer show-more controls, keeping the history list more responsive.
- **Better Session Conversion and Resume Registration** - Converted sessions are handled more reliably when moving between supported assistant formats.
- **Improved Message Rendering** - Conversation text, colors, and dynamic message details render more consistently.

### Fixed

- **Unread Activity Accuracy** - Read/unread indicators are more consistent when sessions update or are opened from another window.

## [0.6.3] - 2026-07-28

### Added
- **LaTeX Math Rendering** - Conversations now render LaTeX math with KaTeX. Copying rendered math gives you the TeX source back.
- **Hide Individual Sessions** - Hide single sessions from the history list, not just entire projects; unhide them anytime from the Hidden tab.

### Fixed
- **Sub-Agent Ordering** - Sub-agents in the agent thread rail now appear in the order they actually started.

## [0.6.2] - 2026-07-27

### Improved
- **Worktree-Aware Project Grouping** - Sessions from linked worktrees are now grouped more intelligently with their main project, making related work easier to find in the history list.
- **Branch and Worktree Labels** - History rows and conversation views can now show branch and worktree context so you can tell which checkout a session came from.

### Fixed
- **Project Matching Edge Cases** - Fixed cases where the same project could appear as separate groups because of different encoded paths or worktree locations.

## [0.6.1] - 2026-07-27

### Added
- **Skills Tab** - Browse installed agent skills from the side panel, search them, include or hide plugin skills, open bundled files, and copy the slash command for a skill.
- **Agent Memories Tab** - View saved agent memories from the side panel so reusable project and personal context is easier to find.
- **Mermaid Diagram Rendering** - Conversations can now render Mermaid diagrams with zoom and export support.
- **Large Session Partial Loading** - Very large sessions can now open by loading their most recent messages first, with clear warnings when earlier messages were skipped.
- **Search Operators** - History search now supports boolean operators (`AND`, `OR`, `NOT`), literal phrases with `exact:`, and regular expressions with `re:pattern` or `/pattern/`. Plain searches behave exactly as before.
- **Search By Author** - `me:` searches only your prompts and `ai:` only the assistant's replies, on their own or combined with any other operator.
- **Search Options Dropdown** - A dropdown at the left of the search bar picks the scope (all / your messages / assistant replies) and match mode (exact phrase / regex) without typing any syntax; the placeholder changes to describe what the current selection searches. `AND`, `OR`, and `NOT` can also be inserted from it. The typed operators still work for anyone who prefers them.

### Improved
- **Better Settings Organization** - Extension settings are now grouped into clearer sections, making configuration easier to scan.
- **Clearer Tool Output in Conversations** - Tool activity in conversations is easier to scan, making long assistant sessions more readable.
- **Sharper History Search Results** - Search matching now handles multi-term queries more consistently and highlights advanced operators more clearly.
- **Better Source Filtering** - History source filters are clearer and more reliable when switching between assistant sources and new side-panel collections.
- **Windows Live Status Support** - Live status support now works better on Windows instead of being hidden behind platform checks.

### Fixed
- **Deep Search Result Limits** - Deep search limits now apply by session count instead of raw match count, so one noisy session is less likely to crowd out other relevant sessions.
- **Search Box Typing Stability** - Fixed the history search box occasionally replacing what you typed with a stale, lowercased copy while results refreshed.

## [0.6.0] - 2026-07-21

### Added
- **Live Session Status** - A new real-time status mode can show when supported Claude, Codex, and Grok sessions are working, waiting for permission, or finished without waiting for the history list to refresh.
- **Live Hooks Controls** - You can now enable or disable live status from extension commands or the history view, with clear setup states for each supported assistant.
- **Live Status Trial and Pro Access** - Live status includes a free trial flow, clearer locked states, and upgrade messaging when the trial ends.

### Improved
- **Faster History Loading** - Session lists now appear faster with quicker indexing, lighter session reads, and better handling of large histories.
- **Smoother Session Activity Indicators** - New activity and live-state indicators are easier to notice and keep session rows more accurate while work is happening.
- **Cleaner Search Onboarding** - Search setup and indexing preferences are easier to understand, especially when choosing between faster startup and fuller search.
- **More Polished Conversation Scrolling** - Chat and conversation views now land in the expected position more consistently when opened.

### Fixed
- **Premium Center and Upgrade Flow Clarity** - Account, upgrade, and trial-related messages now behave more consistently across entry points.

## [0.5.7] - 2026-07-14

### Fixed
- **Codex Quota Display Accuracy** - Fixed cases where Codex quota windows could appear in the wrong slot when usage data included newer window details.

## [0.5.6] - 2026-07-11

### Added
- **Grok Usage Tracking** - Grok activity now appears in usage views, model breakdowns, quota charts, and status indicators alongside your other assistants.
- **Session Drilldowns in Usage Analytics** - Usage analytics now make it easier to drill into the sessions behind your activity so you can understand where time, tokens, and cost came from.

### Improved
- **Better Grok History and Search** - Grok sessions are parsed more completely, show richer session details, and work more reliably in history, search, conversation views, and file-change summaries.
- **More Reliable Copilot and Grok File Changes** - Copilot and Grok sessions now produce cleaner file-change information across session views and diffs.
- **More Useful Dashboard Views** - Usage charts, plan-window views, hourly/session rollups, and source filters are clearer and more consistent across supported assistants.
- **Broader Localization Coverage** - More dashboard, webview, and extension text is now localized consistently for supported languages.
- **Smoother Account and Pro Flows** - Device linking, subscription checks, upgrade prompts, and related error messages are more reliable and easier to understand.
- **Lightweight Local Search Storage** - Conversation message bodies are no longer saved to the extension's local SQLite search index.

### Fixed
- **Session Time Accuracy** - Usage analytics now handle session timing more consistently when building daily, hourly, and session-level summaries.
- **Search and Indexing Reliability** - Fixed edge cases that could make lightweight search or indexed search less consistent for newer session sources.
- **Safer Session Deletion** - If VS Code cannot move an explicitly deleted session to the system Trash, the operation now stops and leaves the original file untouched instead of falling back to permanent deletion.

## [0.5.5] - 2026-07-02

### Added
- **GitHub Copilot Session Support** - You can now browse and open GitHub Copilot sessions alongside Claude, Codex, OpenCode, and Grok history.
- **Fable Usage Tracking** - Claude API usage tracking now includes Fable usage and limits where available, including status bar and dashboard visibility.
- **Weekly Reset History** - The dashboard now shows a weekly reset history table so you can see when quota windows reset and how much quota was used or left unused.

### Improved
- **Faster Multi-Assistant History** - Session discovery, parsing, searching, and status bar updates are faster across Claude, Codex, OpenCode, Grok, and Copilot histories.
- **More Consistent Source Filtering** - Search and history filtering now apply source filters more reliably across supported assistants.
- **Cleaner Multi-Source Internals** - Shared source handling has been simplified, making resume, discovery, watching, and metadata behavior more consistent across assistants.

### Fixed
- **Search Source Filter Accuracy** - Fixed cases where session search could ignore the selected assistant/source filter.
- **Live Session Indicators** - Live indicators now handle Copilot sessions more consistently.

## [0.5.4] - 2026-06-23

### Improved
- **Faster History and Side Panel Rendering** - The side panel now caches more of its repeated UI work, helping history views feel snappier and more responsive.
- **Better Project Path Caching** - Project and session lookup work has been reduced in the side panel, improving performance when browsing larger histories.


## [0.5.2] - 2026-06-22

### Added
- **Grok Session Support** - You can now browse and work with Grok sessions alongside Claude, Codex, and OpenCode history across the extension.
- **Model Filter in History** - The history view now lets you filter sessions by the models they used, making large histories easier to narrow down.
- **Pinned Projects** - Projects can now be pinned so the workspaces you care about most stay easier to find in the history view.
- **Project Context Menu** - Project headers in the history view now have their own context menu for actions like pinning, hiding, revealing in your file manager, and opening in a new window.

### Improved
- **More Modern History List** - The history view has been refreshed with a cleaner, more minimal look while keeping project grouping and quick actions easy to scan.
- **Source Logos and Visuals** - Claude, Codex, OpenCode, and Grok sessions now have clearer source logos and badges across history, search results, and conversation views.
- **Localized Status and Dashboard UI** - More of the extension, especially status bar indicators and dashboard text, now adapts to the user’s language.
- **Markdown Sync and Restore Flow** - Markdown-based session sync and restore workflows are clearer and better integrated into the history UI.

### Fixed
- **History Filtering Reliability** - Fixed several source and model filtering edge cases so history and search results stay more consistent.


## [0.5.0] - 2026-06-13


### Added
- **Session Archive (Pro)** - Claude and Codex automatically clean up old session transcripts over time. You can now archive sessions to keep a full-fidelity copy safe from that cleanup, with a dedicated **Archived** tab to browse them across all your projects. Archived sessions can still be resumed, forked, and copied as commands. Viewing and restoring archived sessions stays free, so you never lose access to your backups.
- **Markdown Session Sync** - Export sessions to a portable Markdown format that you can commit to git and move between devices. Exported sessions can be imported back with their file changes and per-turn summaries intact, or resumed as a native Claude/Codex session — even when the original was created on another computer or operating system.
- **Markdown Sessions Tab** - A new **MD** tab in the history list shows your exported Markdown sessions, viewable just like regular sessions.
- **Bulk Session Actions (Pro)** - Select multiple sessions at once to export or delete them together, with a single confirmation.
- **Per-Model Usage Tracking** - The status bar and dashboard now break down your weekly API usage by model (Sonnet and Opus), giving you a clearer picture of where your quota is going.
- **In-App Help** - Added help buttons and explanations for the new Markdown and Archived session features so it's clear how each one works.


### Improved
- **History List Quick Actions** - Session rows now show hover quick-actions (pin, resume, delete) and full keyboard navigation — use the arrow keys, Home/End, Enter to open, and Delete to remove. Long titles show tooltips, and each tab has its own helpful empty state.
- **Conversation View Polish** - Code blocks now have a floating copy button on hover, you can expand or collapse all sections at once, and assistant messages reveal their timestamp and model on hover. Search matches use your theme's highlight colors.
- **Better Accessibility** - Improved keyboard navigation and screen-reader support for context menus and buttons throughout the history view.
- **Faster History Loading** - Session history loads and refreshes more quickly, with large lists staying responsive and background updates applied in place without losing your scroll position.
- **Configurable Export Location** - Exported sessions now land in a configurable folder, with smarter handling of nested directories.

### Fixed
- **Usage Charts Across Windows** - Fixed the dashboard usage burn-down charts so they stay consistent when you have multiple VS Code windows open at the same time.

## [0.4.81] - 2026-06-07

### Added
- **Date Format Setting** - A new setting lets you choose how dates and times appear throughout the extension: region-neutral ISO (e.g. 2026-06-05 14:30) or your system's own regional format.
- **Resume Destination Preferences** - You can now choose where sessions resume by default — terminal, desktop app, or VS Code extension — set separately for Claude and Codex, along with a per-CLI option to skip permission prompts.

### Improved
- **Consistent Date & Time Display** - Dates and times are now shown consistently across history, session analytics, exports, and the dashboard.
- **Complete Workflow File Changes** - File edits made inside multi-agent workflows are now rolled up into the conversation turn that started them, so workflow file-change summaries are complete.

## [0.4.80] - 2026-05-31

### Added
- **Multi-Agent Workflow View** - Conversations that run multi-agent workflows now show them clearly, with an execution timeline, individual agent cards, and final outputs so you can follow complex runs step by step.
- **Question Prompts in Chat** - Conversations now display the questions asked during a session along with the available options, recommendations, and the answer that was chosen.
- **Workflow Stats in Session Analytics** - Session analytics now include a workflow summary showing how many workflows ran, how many agents they spawned, tool activity, and token usage.
- **Cache Efficiency in Session Analytics** - Session analytics now flag cache misses caused by idle gaps, showing how many tokens had to be re-created and the estimated extra cost.
- **Day-by-Day Usage Breakdown** - The dashboard now includes a day-by-day usage breakdown that fills in automatically in the background, with quick options to recalculate recent days or run a full rebuild.

### Improved
- **Cleaner History List** - The Claude/Codex/OpenCode source badges in the history list are now smaller and more subtle, making session lists easier to scan.
- **Native Session Fork** - The Fork button now uses Claude's built-in fork, creating a true fork of your session that leaves the original untouched.
- **More Accurate Sub-Agent File Changes** - File edits made by sub-agents are now correctly credited to the conversation turn that triggered them in file-change summaries.
- **Faster Conversation Loading** - Long workflow and agent transcripts now load on demand, so opening busy conversations feels snappier.
- **Latest Model Support** - Added usage and cost tracking for the newest Claude Opus model.

### Fixed
- **Resume Command on Windows** - Fixed the copied resume command on Windows so it runs correctly whether you paste it into Command Prompt, PowerShell 5.1, or PowerShell 7.
- **More Reliable Diff Reconstruction** - Fixed a case where rebuilding file changes that contained repeated text could behave unpredictably.

## [0.4.72] - 2026-05-21

### Added
- **Resume in Claude/Codex Desktop Apps** - You can now resume supported sessions directly in Claude Desktop or Codex Desktop or thier VSCode Extension, in addition to terminal-based resume options.
- **Session Deletion from History** - You can now delete sessions directly from the history view and move their files to the system Trash.
- **Right-Click Session Menu** - Session rows now support a context menu for common actions like resume, copy command, rename, pin, copy session ID, and delete.
- **Live Session Indicators** - Active sessions are now easier to spot in history with live indicators for supported sources.

### Improved
- **Faster Pin and Session Actions** - Pinning, unpinning, renaming, and similar session actions now update more quickly without forcing heavier history reloads.
- **OpenCode and Branding Coverage** - More parts of the extension now consistently reflect OpenCode support and naming.

### Fixed
- **Error Handling and Suppression** - Fixed several noisy or non-actionable errors so they are handled more gracefully and reported less aggressively.
- **Session Action Reliability** - Fixed edge cases where history actions could resolve the wrong session file or behave inconsistently when another chat was open.

## [0.4.71] - 2026-05-11

### Fixed
- **Startup and Database Stability** - Fixed several startup-time and database-handling issues that could cause slower launches, repeated failures, or unreliable recovery after database problems.
- **Session Analytics Accuracy** - Fixed an issue where some nested agent costs could be counted incorrectly in session analytics.
- **Background Indexing Reliability** - Fixed race conditions that could affect indexing, session lookups, and related background updates while the extension was still initializing.
- **Missing File Handling** - Fixed cases where opening files referenced by older sessions could produce noisy failures instead of a clearer message when the file no longer exists.
- **Session Analytics Window Reopen** - Fixed a panel lifecycle issue that could affect reopening the session analytics view after it had been closed.


## [0.4.70] - 2026-05-10

### Added
- **OpenCode Session Support** - You can now browse and work with OpenCode sessions alongside Claude and Codex history across the extension.
- **OpenCode Session Analytics and History Views** - OpenCode sessions now appear properly in conversation views, analytics, file history, and search results.

### Improved
- **Live Session Updates** - OpenCode session refresh behavior is now smoother and more reliable while conversations are still changing.
- **Child Session Handling** - Related child sessions are now handled more cleanly, making complex multi-session workflows easier to follow.
- **Dashboard Filtering and Charts** - Dashboard views now better separate usage by source, including OpenCode, and chart interactions feel clearer.

### Fixed
- **Session Discovery Reliability** - Fixed a range of session lookup and parsing edge cases so newer session types appear more consistently.
- **Database and Refresh Stability** - Fixed several reliability issues around background reads, transactions, and live refresh behavior.

## [0.4.64] - 2026-05-01

### Fixed
- **History Refresh Reliability** - Fixed a history view caching issue so refreshed or newly indexed sessions appear more reliably without needing extra manual refreshes.

## [0.4.63] - 2026-04-27

### Added
- **Claude/Codex Source Filter** - Added a source filter in history so you can quickly switch between Claude sessions, Codex sessions, or both.
- **Sub-Agent Stats in Session Analytics** - Session analytics now include more detail about sub-agent activity, including usage and duration.

### Improved
- **History Refresh Behavior** - The refresh button now behaves more predictably and is better tuned for quick refreshes versus deeper scans.
- **Cleaner Session Lists** - History and session views now do a better job of excluding internal subagent session files from normal chat browsing.
- **Session Conversion Flow** - Converting a session now gives smoother follow-up actions for resuming or copying the next command.

### Fixed
- **Subagent Session Noise** - Fixed cases where Codex subagent session files could show up where regular chat sessions were expected.
- **Time and Cost Accuracy** - Fixed some analytics calculations so time and usage details are represented more accurately.

## [0.4.62] - 2026-04-20

### Added
- **Reload Conversation** - Added a refresh action in the chat view so you can reload the current conversation without reopening it.

- **Live Agent Conversation Updates** - Agent conversations now update more naturally while work is still in progress, making long-running agent tasks easier to follow.
- **Search and Review Progress Feedback** - Deep search and Review Changes now show clearer progress while results and diffs are being prepared.

### Improved
- **Clearer Agent Details** - Agent conversations now show better status, metadata, and message counts where available.
- **Better Chat Context Markers** - Chats now surface important session events, such as summaries and context compaction, in a cleaner way.
- **Conversation Recap** - Added recap display support based on latest Claude Code update
- **Improved Session Analytics** - Session analytics now include more detail about activity patterns inside a conversation.
- **More Helpful Missing File Handling** - When a linked file cannot be opened directly, the extension now helps you locate it through Quick Open.


## [0.4.61] - 2026-04-14

### Added
- **API Analytics Dashboard** - Added a richer analytics dashboard with new charts and usage views to help you understand Claude and Codex activity over time.
- **Project Group Expand and Collapse** - Project groups in the history view can now be expanded and collapsed, making large histories easier to browse.
- **Better Agent Task Details** - Agent conversations now show clearer task details, including status, duration, and tool usage where available.

### Improved
- **Dashboard Navigation and Charts** - The dashboard now has cleaner tab navigation and more visual breakdowns for usage patterns, rate-limit activity, and daily trends.
- **Large File Handling** - Search and indexing now handle large files more safely, reducing the chance of slowdowns or noisy failures.


## [0.4.51] - 2026-04-06

### Improved
- **Better Windows Compatibility** - File matching, search, and session handling now work more reliably across Windows-style paths and mixed path formats.
- **More Reliable Forking and Resume Actions** - Session forking and resume flows now handle more path and launch cases correctly, helping these actions work more consistently.
- **More Dependable Usage Insights** - Usage and aggregate statistics are now more accurate and consistent across the extension.

### Fixed
- **Cross-Platform File History Matching** - Fixed cases where file history, search, or timeline results could miss matches because of path-format differences between platforms.
- **Analytics Consistency** - Fixed several gaps in aggregate stats so reported activity better reflects the actual session data.

## [0.4.5] - 2026-04-01

### Added
- **Session Analytics View** - Added a dedicated session analytics view so you can inspect a chat in more detail and better understand how a session progressed.
- **Session Duration in Chat Details** - Chats now show session duration in the metadata area for better context at a glance.

### Improved
- **Smarter File Timeline Loading** - The File Timeline now behaves more efficiently during rapid file switching, helping it feel smoother and less distracting.
- **Clearer Session Titles** - Session naming is more reliable, including better handling of AI-generated titles where available.

### Fixed
- **More Accurate Session Totals** - Fixed some cases where session usage totals could miss activity from related agent work.
- **File Timeline Stability** - Fixed cases where the file timeline could keep loading unnecessarily or react poorly when the view was not active.


## [0.4.4] - 2026-03-30

### Added
- **New File Timeline View** - Added a dedicated File Timeline view so you can quickly see which sessions changed the current file and jump straight into the relevant chat or diff.
- **Task Progress in Chats** - Chats now show task progress more clearly, making it easier to follow longer workflows and multi-step sessions.
- **More File Timeline Actions** - You can now refresh the file timeline, open the related chat, view diffs, and resume a session directly from the timeline.

### Improved
- **Faster, Smoother Chat Loading** - Session loading is now more consistent and responsive, especially when switching quickly between files or chats.
- **Better Side Panel Workflow** - The side panel is easier to use, with cleaner search controls, better prompt grouping, and more polished history browsing.
- **More Flexible Chat Opening** - Opening chats now works more smoothly across the side panel and editor, giving you more control over how sessions are viewed.
- **Cleaner Conversation Flow** - Long conversations with task updates now feel easier to read without interrupting your place in the chat.

### Fixed
- **More Reliable Session Opening** - Fixed cases where older or delayed session loads could override the chat you actually wanted to open.
- **Better Diff and Timeline Consistency** - Fixed a few cases where file history and diff actions could feel out of sync across views.
- **Cleaner Chat Navigation** - Fixed small chat-view issues so navigation controls appear more appropriately depending on where the chat is opened.

## [0.4.2] - 2026-03-24

### Added
- **Open Exported Chats in the Extension** - You can now reopen supported exported Markdown chat files directly inside the extension.
- **Clearer Per-Prompt Change Summaries** - Each prompt now gives a clearer summary of what changed, making it easier to follow the flow of a conversation.
- **Easier Undo and Reapply** - Undoing or reapplying changes is now smoother, especially when a prompt affected multiple files.

### Improved
- **More Accurate Change Views** - File changes and diffs are now shown more clearly and more consistently across chats.
- **Better History Browsing** - Search, grouping, and timeline views in the side panel are easier to scan and navigate.
- **More Reliable Session Details** - Session information now stays more consistent when opening and switching between chats.
- **More Reliable Usage Insights** - Usage and analytics information is now more dependable across different session types.
- **Smoother Upgrade Prompts** - Upgrade messages now feel more consistent and integrated throughout the extension.

### Fixed
- **Codex Chat History Accuracy** - Fixed some cases where child or forked Codex chats could appear incorrectly in history.
- **Multi-File Change Display** - Fixed cases where changes across multiple files were not shown as clearly as they should be.
- **History Reliability Across Views** - Fixed issues that could cause history and search results to behave inconsistently in different parts of the extension.
- **Chat Rendering Cleanup** - Fixed a few export and rendering edge cases so chat output appears cleaner and more reliable.

## [0.4.0] - 2026-03-16

### Added
- **Refreshed Chat View UI** - Replaced the older chat view with a new conversation view experience in the side panel, while keeping a toggle to switch back to the old session view if preferred.
- **Codex-Aware Session Forking** - Expanded session forking to better support Codex conversations and preserve more session metadata when branching from existing chats.

### Improved
- **Session Titles and History Labels** - Improved title resolution for both Claude and Codex sessions, including better handling of newer session formats and cleaner labels in the history UI.
- **Search and Session Discovery** - Improved search base-directory handling, adaptive reparsing, filtering, and session sorting so large histories and mixed Claude/Codex setups stay more accurate and responsive.
- **Conversation View Usability** - Improved message copy behavior, session metadata display, diff access, and conversation-level interactions across the new viewer and side panel.

### Fixed
- **Workspace and Project Resolution** - Fixed several session discovery edge cases related to chat-path handling and project/workspace matching.
- **History View Presentation** - Fixed inconsistencies in date formatting, session item styling, and message rendering in the side panel and search results.

### Documentation
- **Website and Onboarding Content Refresh** - Updated the landing and upgrade pages with a new How It Works section, refreshed marketing content, and improved deployment metadata such as headers, sitemap, robots, and security contact information.

## [0.3.92] - 2026-03-10

### Added
- **Additional Chat Directories** - Added configurable `claudeChatDirectories` and `codexChatDirectories` settings, plus settings UI actions to save and validate custom history paths for both Claude and Codex sessions.
- **Session Title Resolution from Codex Index** - Added support for reading Codex session titles from `session_index.jsonl` before falling back to legacy sources.
- **Session Recovery on Large Files** - Added a **Show All** action so hidden messages in capped large sessions can be displayed on demand.

### Improved

- **Codex Tool Parsing Coverage** - Expanded Codex command parsing for additional write/read/list patterns (including heredoc writes, sed ranges, and `find -name`), improving extracted file change details in chat history.
- **History Refresh Responsiveness** - Updated side panel refresh flow to refresh the history list immediately while reparsing to avoid stale content during long refreshes.

### Fixed
- **File Link Handling in Chat View** - Improved markdown file link parsing so local/relative links with line anchors now open in the editor correctly.
- **Latest Session Resolution** - Improved latest-session selection to include configured additional chat roots and apply consistent project filtering.

## [0.3.91] - 2026-03-05

### Fixed
- **Show Latest Chat** - Fixed `showLatestChat` not displaying the correct latest session for the current workspace. Now scans the filesystem directly instead of relying on potentially stale database queries
- **Codex Workspace Filtering** - Fixed Codex sessions from unrelated workspaces being selected as the "latest" session. Both the side panel and status bar file navigator now filter Codex sessions by workspace when not in "All Projects" mode
- **Empty Project Path Fallback** - Fixed sessions with no `cwd` in messages throwing parse errors. The parser now derives `projectPath` from the JSONL file's directory path when `cwd` is missing

## [0.3.9] - 2026-02-25
### Added
- **Recent File Changes Quick View** - New Quick Pick experience for quickly browsing recent session file changes (Claude + Codex) with per-file aggregated diffs, session navigation, refresh, open-in-chat, and resume actions
- **Quick View Keyboard Shortcut** - Added `Ctrl+Alt+;` (or `Cmd+Alt+;` on Mac) to open Recent File Changes Quick View from anywhere
- **Session ID Search Support** - Added session ID fragment search in both the Quick View session jump input and the History page search box

### Improved
- **Status Bar File Changes UX** - Clicking the status bar file-change item now opens the Recent File Changes Quick View and preserves the currently displayed session/file selection
- **History and Chat Tips Discoverability** - Added shortcut guidance for the Recent File Changes Quick View in status-bar onboarding tip and chat Tips section
- **Quick View Session Context** - Quick View now defaults to All Projects and shows the current session project name in the header for clearer context while browsing

### Fixed
- **Windows WSL Claude Directory Path Handling** - Fixed search index rebuild failures when `claudeDirectory` is configured as a quoted WSL UNC path (for example `"\\\\wsl$\\Ubuntu\\home\\user\\.claude"`), by sanitizing pasted paths before saving and before index/database path creation

## [0.3.8] - 2026-02-16

### Added
- **Review Changes Filtering and Search** - Added powerful filtering and search capabilities in the Review Changes experience to quickly locate specific files and changes
- **Email OTP Authentication Flow** - Added email OTP support in authentication for more reliable sign-in and account linking

### Improved
- **Review Changes and Session Browsing UX** - Improved parser, renderer, side panel, and timeline integration to better surface and navigate code changes
- **Authentication Session Handling** - Improved auth refresh and user/device synchronization logic across extension companion services

## [0.3.7] - 2026-02-12

### Improved
- **API Usage Tracking Reliability** - Refined usage counter, status indicator, and related service logic for more consistent quota and usage display
- **Search and Database Services** - Improved SQLite/database service behavior for better stability and result handling

## [0.3.6] - 2026-02-08

### Added
- **Codex Image Display** - Images in Codex chats are now rendered in the chat view (instead of showing raw content)

### Improved
- **API Usage Analytics UI** - Improved analytics display of API usage
- **Codex Chat Rendering** - Better Codex chat display and formatting in the viewer
- **Tool Result Rendering** - Richer rendering for tool outputs (no longer just `exec_command`)

## [0.3.5] - 2026-02-02

### Added
- **API Usage Quota Tracking** - New Claude/Codex plan usage section in the analytics dashboard with live quota cards, burn-down chart, and weekly summary insights
- **API Usage Status Bar Indicator** - Optional status bar quota indicator with a quick link to the dashboard and a refresh command
- **Session Format Converter** - Convert sessions between Claude and Codex formats directly from the chat view, then resume in the target assistant



## [0.3.4] - 2026-01-25

### 🎉 Extension Renamed
- **Claude Code and Codex Assist** - The extension has been renamed from "Claude Code Assist" to "Claude Code and Codex Assist" to reflect support for both AI assistants. All features now work seamlessly with both Claude Code and Codex sessions!

### Added
- **Syntax Highlighting in Diffs** - Review Changes view now includes syntax highlighting for code diffs, making it easier to read and understand file changes. Highlights are based on file extensions and use highlight.js
- **Expand/Collapse Hidden Lines** - Added interactive expand/collapse buttons for hidden lines in diff views (both inline and side-by-side), giving you better control over viewing context
- **File Change Statistics** - Sessions now display detailed file change metrics including number of files changed, total additions, and total deletions for better overview of session activity

### Improved
- **Undo Functionality** - Enhanced undo operations with content validation to ensure changes are applied correctly and safely
- **Project Grouping** - Improved project grouping logic in the side panel for better session organization
- **Session File Change Tracking** - More accurate tracking of file modifications with database-backed statistics and automatic UI synchronization

## [0.3.3] - 2026-01-21

### Added
- **Codex Support** - The extension now works with both Claude and Codex conversations! Browse your Codex sessions right alongside your Claude chats. Visual badges help you quickly identify which AI assistant you were using
- **Review Changes View** - New dedicated view that shows all file changes from a conversation in one organized place. Perfect for reviewing what changed before applying updates to your workspace
- **Undo Changes** - Made a mistake? No problem! Easily undo any file changes with a single click
- **Better Session Organization** - Sessions are now sorted more intelligently, making it easier to find what you're looking for

### Improved
- **File Change Tracking** - Enhanced tracking now works across both Claude and Codex sessions
- **Search Experience** - Search results now include both Claude and Codex conversations for comprehensive history browsing

## [0.3.2] - 2026-01-08

### Added
- **Useful Tips Section** - A new tips bar at the bottom of the chat view displays helpful usage tips. Click the refresh button to see different tips and learn shortcuts, features, and productivity tricks
- **Tips Toggle in Settings** - Control whether the tips section is displayed via a new "Show Tips" option in extension settings
- **Copy Resume Command** - New option to copy the full resume command (including `cd` to project directory) to clipboard for pasting in any terminal
- **Web Dashboard Access** - Pro users can now open the online dashboard directly from the extension to view detailed analytics synced from the extension

### Improved
- **Streamlined Markdown Export** - Exporting sessions to Markdown now auto-saves to `~/[Project]/claude-chats/` folder and opens the file automatically. Only prompts for location if the file already exists
- **Enhanced Error Handling** - More robust error handling across database operations and file handling with better recovery mechanisms

## [0.3.1] - 2025-12-23

### Fixed
- Slow onboarding experience for first-time users - significantly improved initial loading performance when using the extension for the first time

## [0.3.0] - 2025-12-22

### Added
- **Welcome Guide for New Users** - Interactive welcome screen appears when you first use the extension, showing you all the cool features you can use
- **Advanced Search Option** - New search mode that works directly with your chat files for faster results and better privacy
- **Richer Session Information** - Sessions now display more useful details when you search, making it easier to find what you're looking for

### Improved
- **Better File History View** - When viewing file changes over time, you now see clearer diffs and better formatting

### Fixed
- Sessions not loading properly on Windows computers
- Errors when viewing certain search results

## [0.2.98] - 2025-12-17

### Added
- **Session Pinning** - Pin important sessions to keep them at the top of your session list for quick access
- **Custom Session Titles** - Rename sessions with custom titles to better organize your work
- **Session Management Commands** - New commands to rename sessions, delete custom titles, and toggle pin status
- **Enhanced Export Preferences** - More control over metadata inclusion when exporting sessions to Markdown
- **Fork Session Enhancements** - Improved session forking with better summaries and automatic token count estimation


### Improved
- **Title Extraction** - Significantly improved automatic title generation by reading the last portion of JSONL files for recent summaries
- **Session Loading** - Enhanced logic to automatically skip empty or broken sessions from the database


### Fixed
- Improved reliability when loading sessions with missing or corrupt data
- Better handling of edge cases in JSONL file parsing
- More graceful error recovery in database operations

## [0.2.94] - 2025-12-13

### Added
- **Plan View** - Browse and manage your Claude Code plans directly in VS Code! View all plans from `~/.claude/plans/`, navigate between them, and access plan content with a dedicated interface
- **Plan Export to Markdown** - Export individual plans to beautifully formatted Markdown files for easy sharing and documentation
- **Plan Actions** - Copy plan content to clipboard, open plans in VS Code editor, or export them with one click
- **Enhanced Demo Showcase** - Improved demo experience with video playback support and fullscreen viewing capabilities

## [0.2.92] - 2025-12-07

### Added
- **Markdown Export** - Export your Claude Code sessions to Markdown format.
- **Enhanced Session Handling** - Improved session management in the side panel with better organization and navigation of chat conversations.

### Improved

- **Error Handling** - Enhanced JSON parsing error handling with more informative error messages and better recovery mechanisms.
- **Status Bar** - Optimized usage display in the VS Code status bar for clearer and more concise information.

## [0.2.9] - 2025-12-04

### Changed
- **License Update** - Transitioned from Apache-2.0 to a proprietary End-User License Agreement (EULA)
  - The extension remains free to use for personal and commercial purposes
  - Source code is now proprietary and confidential
  - Clear terms for usage rights, restrictions, and intellectual property protection
  - EULA includes data collection transparency, warranty disclaimers, and liability limitations
  - Governed by the laws of India
- **Contact Information** - Added email (yashagl10@gmail.com) and Twitter/X (@yashagl) to contact details

### Documentation
- Updated README.md with new license information and enhanced contact section
- Added comprehensive EULA covering software usage, restrictions, data privacy, and user rights
- Clarified that the extension is free to use but not open source

## [0.2.8] - 2025-11-25

### Added
- **Session Resume** - Resume your Claude conversations directly from the extension! View any past session and click the play button (▶️) to open it in your terminal, or copy the command (📋) to resume it elsewhere
- **Session Fork** - Create a new conversation starting from any point in your chat history. Click the 🔀 Fork button next to any message to branch off and explore alternative approaches without losing your original conversation
- **Session-Grouped Search** - Search results are now organized by session with collapsible groups, making it easier to find conversations and see all matches within each session at a glance

### Improved
- **Search Experience** - Enhanced search interface with better organization and navigation through your chat history
- **Session Navigation** - Smoother workflow for browsing and managing your Claude conversation history

## [0.2.7] - 2025-11-21

### Added
- **Engagement Distribution Analytics** - New visualization in the dashboard showing your usage patterns and engagement distribution across different features
- **Enhanced Search Results** - Search results now display session file paths, making it easier to identify and navigate to the right conversations

### Improved
- **Search Performance** - Significantly faster and more accurate search with improved indexing and query processing
- **Search Experience** - Better context and navigation with file path display in search results
- **Performance** - Significantly faster session loading and file operations for a more responsive experience
- **Session Management** - Smoother and more efficient session browsing and navigation
- **Overall Responsiveness** - Reduced loading times and improved interface responsiveness throughout the extension

## [0.2.6] - 2025-11-04

### Added
- **Agent and Task Tool Support** - Enhanced chat message handling to support new agent and task tool features, providing better visualization of agent-based operations and task execution


### Enhanced
- **File Handling** - Added existence checks for JSONL files to prevent parsing errors and improved error suppression for malformed entries
- **Message Rendering** - Significantly improved rendering of tool results and file changes with better formatting, tooltips, and interactive elements
- **Error Handling** - Enhanced error handling across file changes and message rendering with more informative error messages and graceful fallbacks


## [0.2.5] - 2025-10-28

### Enhanced
- **Usage Statistics** - Integrated detailed usage tracking methods for file search, chat history events, and file timeline interactions
- **Message Rendering** - Improved formatting for tool results including Bash output and GitHub-style code views
- **Tool Result Pairing** - Enhanced message renderer to better pair commands with their outputs for clearer visualization

### Fixed
- **Session Metadata** - Improved metadata extraction and inference for summary-only sessions
- **Database Corruption** - Enhanced error handling for database corruption with better recovery mechanisms
- **Empty Content Handling** - Better handling of empty search queries and message content
- **Image Support** - Added support for rendering image content in messages with ability to open in VS Code
- **Timeline Events** - Added proper error handling for tool result content with improved timeline event categorization

## [0.2.4] - 2025-10-23

### Added
- **File History Timeline** - View complete modification history for any file across all your chat sessions. Select a file to see a visual timeline showing when it was changed, what operations were performed (read, write, edit, multiedit), and which sessions modified it. Click any operation to view the diff or navigate to the conversation
- **Right-Click Context Menu** - New "Show in Claude History Timeline" option in file explorer and editor context menus. Right-click any file to instantly view its complete modification history across all Claude sessions. Can be disabled in settings via `claude-history.contextMenu.showFileTimeline`

### Enhanced
- **Message Rendering** - Improved display of tool results with better formatting and pairing of commands with their outputs
- **File Search Mode** - Replaced multi-file search with single-file timeline view for clearer navigation of file history
- **Session Title Extraction** - Improved logic for extracting meaningful titles from conversations
- **Search Service** - Enhanced file path queries and search capabilities with better metadata handling
- **Parser Robustness** - Improved line handling for malformed or incomplete JSONL entries

### Fixed
- **Database Error Handling** - Better detection and recovery from database corruption with clear user feedback
- **Empty Content Handling** - Graceful handling of empty search queries and missing message content
- **Message Rendering** - More reliable display of complex tool results and timeline events
- **Parser Stability** - Improved error recovery when processing summary-only or incomplete sessions

## [0.2.3] - 2025-10-04

### Added
- **Image Content Support** - View images directly within chat messages; click to open them in VSCode for detailed inspection
- **Enhanced Session Metadata** - Automatic metadata extraction for sessions that only contain summaries
- **Timeline Event Types** - Improved message timeline with better categorization and visual indicators

### Enhanced
- **Error Handling** - Robust database corruption detection and recovery with helpful user feedback
- **Message Rendering** - Better display of tool results with improved formatting and interactive elements
- **Empty Content Handling** - Graceful handling of empty search queries and message content
- **Session Processing** - Improved inference of session details from incomplete data

### Fixed
- **Database Stability** - Added safeguards against corrupted databases with automatic error reporting
- **Search Reliability** - Better handling of edge cases in search queries and empty content
- **Tool Result Display** - Improved rendering of complex tool outputs and error messages

## [0.2.1] - 2025-09-26

### 🍎 **CRITICAL FIX FOR MAC USERS**
**✅ Extension now works on macOS!** - Fixed critical compatibility issue that prevented the extension from starting on Mac devices.

### Fixed
- **Cross-Platform Compatibility** - Migrated from native sqlite3 to sql.js (WebAssembly) to eliminate architecture-specific native module issues
- **Mac Installation Issues** - Resolved "slice is not valid mach-o file" errors that prevented extension activation on macOS
- **Windows Compatibility** - Extension now uses a single universal binary that works across all platforms and architectures
- **Universal Architecture Support** - Works on Intel x64, Apple Silicon (M1/M2/M3), and ARM64 without native module compilation

### Enhanced
- **Single Distribution File** - One .vsix file works on Windows, macOS, and Linux across all architectures
- **Database Performance** - Maintains full SQLite compatibility with improved cross-platform reliability
- **WebAssembly Backend** - Modern WASM-based SQLite implementation for consistent performance across platforms

### Technical Details
- Replaced sqlite3 native module with sql.js WebAssembly implementation
- Updated esbuild configuration to handle WASM file bundling
- Fixed transaction management for synchronous sql.js API
- Added proper WASM file location handling for VS Code extension environment

## [0.2.0] - 2025-09-10

### Added
- **Undo Functionality** - Added comprehensive undo capabilities for edit operations
- **Multi-Edit Operations Enhancement** - Improved handling and processing of multi-file edit operations
- **Dashboard Button Toggle** - Added configurable dashboard button visibility in settings panel
- **Usage Counter Service** - Integrated comprehensive feature usage tracking and analytics
- **Search and Cost Tracking Enhancements** - Enhanced search capabilities with improved cost analysis and tracking features

### Enhanced
- **Side Panel Dashboard Display** - Made dashboard button display conditional based on user settings
- **Edit Operation Management** - Improved reliability and user experience of edit and undo operations

### Fixed
- **Multi-Edit Reliability** - Resolved issues with complex multi-file edit scenarios
- **Dashboard Integration** - Fixed dashboard button display consistency with user preferences

## [0.1.9] - 2025-09-08

### Added (Summary)
- **SQLite Database Backend** - Migrated from Lunr.js to SQLite for enhanced search performance and data persistence (SQLiteSearchService.ts:24)
- **Advanced Cost Tracking** - Comprehensive cost calculation and analysis with token usage breakdown (CostCalculator.ts:130)
- **Dashboard Analytics** - Complete dashboard with usage statistics, activity timelines, and cost trends (DashboardService.ts:129)
- **Leaderboard Integration** - Optional community leaderboard with anonymous usage comparison (LeaderboardService.ts:86)
- **Enhanced Search Capabilities** - File-based search, content indexing, and detailed session tracking (SearchIndexManager.ts)
- **Database-Driven Session Management** - Improved session loading with filtering, sorting, and pagination

### Enhanced
- **Search Performance** - SQLite-based full-text search with improved query speed and accuracy
- **Cost Analysis** - Model-specific cost breakdown with cache token tracking and deduplication
- **Session Analytics** - Daily usage statistics, activity heatmaps, and efficiency metrics
- **Data Persistence** - Robust data storage with incremental updates and file watching
- **Token Usage Tracking** - Detailed tracking of input, output, cache creation, and cache read tokens

### Fixed
- **Memory Usage** - Optimized database operations with proper connection management
- **File Change Processing** - Improved efficiency in detecting and processing file modifications
- **Error Handling** - Enhanced error reporting and recovery mechanisms

### 2025-09-06  
- **Dashboard and Leaderboard Enhancements** - Enhanced dashboard and leaderboard functionalities with billing window and data clearing features 
- **Leaderboard Data Synchronization** - Implemented leaderboard data synchronization and user verification features

### 2025-09-05
- **Leaderboard Settings and Data Sharing** - Implemented leaderboard settings and data sharing functionality 

### 2025-09-04
- **SearchIndexManager Enhancements** - Enhanced file change detection and processing efficiency in SearchIndexManager

### 2025-09-03
- **DashboardService Implementation** - Added DashboardService and related functionalities for analytics

### 2025-09-02
- **Search and Database Services Refactor** - Refactored search and database services for improved performance and clarity; removed unnecessary data storage 

### 2025-09-01
- **Enhanced Search Functionality** - Enhanced search functionality with file search capabilities and detailed session tracking 

### 2025-08-31
- **SearchIndexManager Introduction** - Introduced SearchIndexManager for managing search index and file watching

## [0.1.7] - 2025-08-26

### Added
- **AI Thinking Display** - Added comprehensive handling and display of AI thinking content with collapsible blocks
- **Enhanced Message Rendering** - Improved rendering system for different content types including thinking blocks
- **Thinking Content Styling** - Added specialized CSS styles for AI thinking display with VS Code theme integration

### Fixed
- **Content Type Handling** - Better detection and rendering of thinking content vs tool uses
- **Error Reporting** - Improved error handling in status bar file navigator

## [0.1.6] - 2025-08-26

### Added
- **StatusBarFileNavigator** - New status bar component for enhanced file navigation and session monitoring
- **File Reapply Functionality** - Ability to reapply file changes and individual edits directly from the interface
- **Loading State Management** - Improved loading indicators for better user experience during file navigation
- **Enhanced Navigation Commands** - New command palette options for file navigation operations

### Improved
- **Unified Diff Renderer** - Refactored to support selectable line numbers and enhanced gap handling
- **Diff Generation Performance** - Streamlined diff generation to use unified diff renderer exclusively
- **Parser Terminology** - Updated summary headers to reflect enhanced parser capabilities
- **Code Maintainability** - Consolidated return statements and improved code readability
- **File Change Tracking** - Better handling of file modifications and state management

### Fixed
- **Diff Display Consistency** - Removed priority checks for more reliable diff generation
- **User Interface Responsiveness** - Enhanced status bar integration with better state management

## 2025-08-25

### Added
- **StatusBarFileNavigator** - New status bar component for enhanced file navigation and session monitoring
- **Session Monitoring** - Real-time tracking of active sessions and file states

### Improved
- **File Navigation Experience** - Streamlined navigation through chat history and file changes
- **User Interface Integration** - Better integration with VS Code status bar functionality

## 2025-08-24

### Added
- **File Reapply Functionality** - Ability to reapply file changes and individual edits directly from the interface
- **Enhanced Gap Handling** - Improved detection and handling of missing content in diffs
- **Selectable Line Numbers** - Interactive line number selection in diff displays

### Improved
- **Unified Diff Renderer** - Refactored to support advanced diff features and better performance
- **Diff Generation Performance** - Streamlined diff generation to use unified diff renderer exclusively
- **Parser System** - Enhanced parser terminology and consolidated code structure
- **Code Maintainability** - Improved readability with consolidated return statements and cleaner architecture

## [0.1.3] - 2025-08-16

### Fixed
- **Core Functionality** - Resolved critical bugs affecting extension stability and performance
- **Search Operations** - Fixed various issues with search indexing and result retrieval


### Improved
- **Search Index Management** - Optimized search command structure and index handling
- **User Interface** - Better loading indicators and enhanced user experience
- **Cross-Platform Compatibility** - Improved file handling across different operating systems
- **Performance Optimization** - Streamlined search service architecture for faster results



## [0.1.2] - 2025-08-15 

### Added
- **Universal Search** 🔍 - Search across all your chat history with powerful full-text search
- **Smart Search Results** - Click any search result to instantly jump to that conversation
- **File Content Search** - Find conversations by searching within file changes and code snippets
- **Quick Search Commands** - New command palette options for faster searching and index management
- **Enhanced Message Display** - Better formatting for tool results and code outputs
- **Search Index Export/Import** - Backup and restore your search index for data portability
- **Cross-Platform Support** - Improved compatibility across Windows, macOS, and Linux

### Improved
- **Faster Search Performance** - Compressed search index for quicker results
- **Better Loading Experience** - Added loading indicators so you know when searches are running
- **Smoother Navigation** - Enhanced interface responsiveness and visual feedback
- **More Reliable File Handling** - Better error handling and stability across different systems
- **Automatic Index Updates** - Your search index stays current as you use Claude

## 2025-08-14

### Added
- **Enhanced Cross-Platform Compatibility**: Improved support for different operating systems with better path handling
- **Periodic Device Connectivity**: Added automatic device ping functionality for better service reliability

### Fixed
- Temporary file handling issues
- Path normalization problems across different platforms
- File system compatibility issues

## 2025-08-13

### Added
- **First Official Release**: Initial stable release of Claude Code Assist
- **Device Services**: Integrated device management and pricing information
- **Enhanced Message Rendering**: Improved display of chat messages with compact tool formats
- **Cost Calculation**: Added detailed cost tracking and analysis features

### Fixed
- Message display formatting
- Tool output rendering
- Performance optimizations

## 2025-08-12

### Added
- **File Change Refresh**: New functionality to refresh and update file change displays
- **Individual Diff Support**: Added support for viewing individual file differences
- **Title Extraction**: Automatic extraction of meaningful titles from user messages
- **Enhanced Search**: Improved search functionality within chat sessions
- **Native Diff Support**: Integrated native VS Code diff viewer support

### Improved
- User interface responsiveness
- Search accuracy and speed
- File change tracking and display

## 2025-08-11

### Changed
- **Major Code Restructure**: Comprehensive refactoring for improved performance and maintainability
- **Enhanced Architecture**: Better organized codebase for future development
- **Improved Performance**: Faster loading times and more responsive interface

### Fixed
- Memory usage optimizations
- Code organization and structure improvements

## 2025-08-10

### Added
- **Package Metadata Updates**: Enhanced extension information and compatibility details
- **Cost Calculation Features**: Advanced cost tracking and analysis capabilities
- **Enhanced Session Management**: Improved loading and history management
- **Better Documentation**: Added comprehensive guides and documentation

### Improved
- Session loading performance
- History browsing experience
- User documentation and help resources

### Fixed
- Removed debugging output for cleaner user experience
- Code cleanup and optimization

## 2025-08-09

### Added
- **Enhanced File Reconstruction**: Improved ability to reconstruct file states from chat history
- **Advanced Patch Generation**: Better handling of file changes and modifications
- **Improved Parser System**: More robust parsing of chat history files

### Improved
- File change tracking accuracy
- Diff generation reliability
- Error handling and recovery

## 2025-08-08

### Added
- **Enhanced Diff Rendering**: Improved visual display of file differences with better styling
- **Gap Detection**: Advanced algorithm for detecting and handling missing content
- **Robust Parsing**: More reliable parsing of complex chat histories

### Improved
- Visual design of diff displays
- User interface styling and layout
- Performance of diff generation

## 2025-08-07

### Added
- **File Changes Panel**: Dedicated panel for viewing all file modifications
- **Robust Parser System**: Advanced parsing capabilities for complex scenarios
- **Enhanced User Interface**: Modern and intuitive interface design
- **File State Management**: Comprehensive tracking of file changes over time

### Improved
- File change visualization
- User experience and interface design
- Performance and reliability

## 2025-08-06

### Added
- **Unified Diff Renderer**: Standardized diff display system for consistent viewing experience
- **Chat Panel Refactoring**: Improved chat display and interaction

### Improved
- Code organization and maintainability
- Diff display consistency
- Performance optimizations

## 2025-08-05

### Added
- **Overhauled User Interface**: Complete redesign of the side panel with modern styling
- **Session Caching**: Improved performance with intelligent caching system
- **Path Normalization**: Better handling of file paths across different systems
- **Enhanced Error Handling**: More robust error detection and recovery

### Improved
- User experience with cleaner, more intuitive interface
- Performance with caching mechanisms
- Reliability with better error handling

## 2025-08-04

### Added
- **Enhanced Diff Rendering**: Improved display of file differences with line number context
- **Fallback Handling**: Better error recovery when displaying diffs
- **Multiple Diff Strategies**: Various algorithms for optimal diff display

### Improved
- Diff accuracy and readability
- Error handling and recovery
- Visual presentation of changes

## 2025-08-03

### Added
- **GitHub-Style Diffs**: Professional diff display similar to GitHub's interface
- **File Changes View**: Comprehensive view of all file modifications
- **Enhanced Diff Utilities**: Improved tools for processing and displaying changes

### Improved
- Visual presentation of file changes
- User experience with familiar diff styling
- Performance of diff generation

## 2025-08-02

### Added
- **Initial Release**: First version of Claude Code Assist
- **Basic Chat Viewing**: Core functionality to view Claude chat history
- **File Diff Support**: Basic diff viewing capabilities
- **Native Integration**: Full integration with VS Code interface
- **Search Functionality**: Basic search through chat history
- **Project Structure**: Organized extension architecture

### Features
- View Claude CLI chat history directly in VS Code
- Browse conversations by project
- See file changes and modifications
- Search through chat content
- Integrated diff viewer for file changes
- Tree view navigation of chat sessions
