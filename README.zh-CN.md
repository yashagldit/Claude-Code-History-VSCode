# Claude Code and Codex Assist — 适用于 VS Code、Cursor 等编辑器的聊天记录、差异与用量分析

[English](./README.md) | **简体中文** | [繁體中文](./README.zh-TW.md) | [日本語](./README.ja.md) | [한국어](./README.ko.md) | [Deutsch](./README.de.md) | [Français](./README.fr.md) | [Español](./README.es.md)

> **注意**：这是一个非官方扩展，并非由 Anthropic、OpenAI、SST/OpenCode、xAI/Grok 或 GitHub 开发，也与它们没有任何关联。

![40 秒了解 Claude Code and Codex Assist：会话历史、继续会话、配额追踪、差异、搜索以及跨 CLI 上下文](./assets/ccassist-promo.gif)

直接在 VS Code 中浏览 **Claude Code**、**Codex**、**OpenCode**、**Grok** 和 **GitHub Copilot** 的聊天记录 —— 查看文件差异、搜索所有对话、追踪 Token 用量和费用，无需离开编辑器即可继续以往的会话。它同时也是一个用量追踪器：一个仪表盘就能看到所有 AI 助手的按模型费用、配额燃尽情况和每周重置历史；如果你有多个 Claude 或 Codex 账号，还能一键切换。想知道是哪段 AI 对话改了某个文件？文件时间线就是 AI 编辑版的 git blame：选中一个文件，就能看到改动过它的每个会话和提示词，并打开确切的差异。

**🤖 支持全部五款助手：**
- **Claude Code** — `~/.claude/projects/`
- **Codex** — `~/.codex/sessions/`
- **OpenCode** — `~/.local/share/opencode/`
- **Grok** — `~/.grok/`
- **GitHub Copilot** — Copilot CLI 和 VS Code 聊天会话

五款助手的会话汇集在同一个列表中，用标识和图标加以区分。内置的 **MCP 服务器** 甚至能让各个助手彼此共享上下文 —— 在 Claude Code 中继续你上一个 Codex 会话，或者让 Grok 告诉你某个 Claude 会话改了什么。

**🌐 界面语言：** English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Deutsch | Français | Español

## 🎬 功能演示

### 🔍 全文搜索
在成千上万个会话中搜索每一条提示词和回复。结果按会话分组，并显示匹配的消息、所属项目和费用。高级面板可以选择搜索对象（全部、你自己或助手）、匹配方式（任意词、精确短语或正则表达式），以及是否包含工具输出和子代理记录。

![全文搜索](./assets/text-search.gif)

### ✅ 会话更改与审阅
每个回合都会显示它改动的文件及 +/- 行数，并支持查看差异、撤消和重新应用。打开 **查看更改**，即可在一处看到一次对话中的全部文件更改。

![会话更改与查看更改](./assets/session-changes.gif)

### ⏱️ 文件历史时间线
**AI 对话版的 git blame。** 打开任意文件，时间线会列出所有编辑过它的会话 —— 展开会话即可看到确切的提示词及其差异，涵盖 Claude Code、Codex、OpenCode、Grok 和 Copilot。

![文件历史时间线](./assets/timeline-demo.gif)

### 💬 对话视图
渲染后的对话记录，每个回合都有 **回合更改** 卡片，还有上下文窗口图、缓存命中率和费用。可在终端、桌面应用或 Codex VS Code 扩展中继续会话，也可导出为 Markdown。

<img src="./assets/conversation-view.png" alt="对话视图，显示按回合的文件更改和继续目标" width="420">

### 📊 配额燃尽与账号切换
Claude、Codex、Fable 和 Grok 的 5 小时及每周实时配额卡片，配合预测每个窗口何时耗尽的燃尽图、活动热图和逐日费用表。可以保存多个 Claude 和 Codex 账号，并在账户标签页、仪表盘的套餐标签页或 **切换 Claude / Codex 账号** 命令中随时切换；每个账号的套餐用量都单独追踪，配额历史绝不会混在一起。

<img src="./assets/account-quota.png" alt="账户标签页，显示配额卡片、燃尽图和活动热图" width="420">

### 📅 每周汇总
滚动 7 天汇总会话、Token、费用、编辑次数和活跃天数，并与上周对比，按工具和项目拆分。

<img src="./assets/weekly-digest.png" alt="每周汇总，显示总计、逐日 Token 和热门项目" width="420">

### 📚 统一会话浏览器
Claude Code、Codex、Grok、OpenCode、Copilot 和 Cursor 的会话集中在一个列表中，按项目分组，支持按模型筛选并显示每个文件夹的费用。

<img src="./assets/chat-history.png" alt="会话标签页按项目分组，并展开了模型筛选器" width="420">

### 🔌 ccassist MCP 服务器
本地 MCP 服务器让 Claude Code、Codex、Grok、OpenCode 和 Cursor 能读取你的会话历史，并接续彼此的工作。

<img src="./assets/history-mcp.png" alt="MCP 标签页，列出 CLI 代理可用的 ccassist 工具" width="420">

### 📍 状态栏中的配额
Claude、Fable、Codex 和 Grok 的配额百分比始终可见；悬停即可查看每个窗口及其重置时间。

<img src="./assets/usage-quota-statusbar.png" alt="状态栏配额指示器及悬停弹窗" width="555">


## 🌟 功能

### 会话与历史记录
- **统一历史记录**：涵盖 Claude Code、Codex、OpenCode、Grok 和 GitHub Copilot，按项目整理，并自动识别当前项目
- **快捷操作与键盘导航** —— 直接在会话行中置顶、继续或删除；用方向键移动、Enter 打开、Delete 删除
- **项目右键菜单** —— 右键点击项目标题即可置顶、隐藏、在文件管理器中显示，或在新窗口中打开
- **隐藏单个会话** —— 无需删除即可清理列表；隐藏的会话按项目归入“已隐藏”标签页，可一键取消隐藏，也可多选批量隐藏
- **丰富的对话记录渲染** —— 带语法高亮代码的 Markdown、可缩放和导出的 Mermaid 图表，以及使用 KaTeX 离线排版的 LaTeX 数学公式（复制渲染后的公式会得到 TeX 源码）
- **实时搜索筛选**，边输入边缩小列表范围
- **模型筛选、置顶项目以及会话置顶与重命名**，让庞大的历史记录保持整洁、易于浏览
- **继续** 任意对话：在终端、桌面应用或 VS Code 中继续，也可以复制命令到别处运行
- **分叉**：从任意消息分叉对话，探索另一种方案而不影响原会话 `Pro`
- **格式转换**：在 Claude 和 Codex 格式之间转换，并直接在目标助手中继续 `Pro`
- **自动刷新**：会话仍在变化时，保持最近会话的内容为最新
- **更简洁的历史列表界面**，视觉风格更精简，长会话列表也更易浏览

### 存档与 Markdown 同步
- **会话存档** —— Claude 和 Codex 最终都会清理旧的对话记录；存档会在独立文件夹中保存一份完整副本，并可在专门的 **已存档** 标签页中浏览。查看和还原已存档会话始终免费。存档需要 `Pro`
- **Markdown 导出**：导出完整会话，元数据可自定义 `Pro`
- **Markdown 同步** —— 导出的会话可以提交到 git、在设备之间迁移、连同文件更改一起导回，或作为原生会话继续（甚至可以跨操作系统）
- **批量操作** —— 选中多个会话一起导出或删除 `Pro`

### 文件更改与差异
- **GitHub 风格差异**，支持语法高亮和多文件
- **查看更改视图** —— 在一处查看一次对话中的所有文件更改
- 一键将更改 **应用、撤消或重新应用** 到工作区
- **文件历史时间线** —— AI 对话版的 git blame：时间线自动跟随当前编辑器，列出编辑过该文件的每个会话，深入任意会话即可阅读确切的提示词并打开其差异（也可以右键点击文件打开时间线）

### 搜索
- **直接文件搜索** —— 每次搜索都直接扫描你的会话文件，不会复制到单独的索引中，结果会显示扫描了多少个文件
- **高级面板** —— 点击搜索栏旁的按钮即可打开可选项：搜索全部消息、只搜你的提示词或只搜助手的回复；匹配任意词、精确短语或正则表达式
- **工具输出与子代理搜索** —— 可选择同时搜索工具输入/结果和子代理记录，找到主聊天消息中从未出现的细节
- **按会话分组的结果**，显示费用、Token 和消息数，并高亮匹配内容

### ccassist MCP 服务器 —— 在助手之间共享上下文
- **本地 MCP 服务器** —— 扩展可以托管一个轻量的本地 MCP 服务器，让 Claude Code、Codex、Grok、OpenCode 和 Cursor 在各自内部查询你的会话历史（仅限本机回环地址，默认关闭）
- **跨工具接续工作** —— 在 Claude Code 中说一句 *"继续我上一个 Codex 会话"*（反之亦然），代理就会拉取一份精炼的交接摘要：最近的回合、会话摘要以及改动内容
- **一键配置** —— 在侧边面板的 MCP 页面或命令面板中运行 **Set up ccassist (MCP + Skill)**；它会把服务器注册到每个 CLI，并安装一个 `ccassist` 技能，教代理何时以及如何使用它
- **七个工具** —— `search_sessions`、`list_recent_sessions`、`get_context` 和 `get_session` 用于查找和加载以往的工作，另有 `grep_sessions`（逐字扫描对话记录，包括工具输出）、`get_session_changes`（按文件的摘要或重建的差异）和 `get_file_sessions`（哪些会话改动过某个文件） `Pro`
- **隐私至上的设计** —— 所有数据都留在你的电脑上；服务器只绑定 localhost，`workspaceOnly` 设置还可以将其限制为当前工作区的会话

### 分析与费用追踪
- **仪表盘**：用量统计、活动时间线和费用趋势
- **配额追踪** —— 实时 Claude/Codex 配额卡片、燃尽图、每周重置历史和每周摘要，并在可用时按模型细分，包括 Sonnet、Opus 和 Fable
- **多个 Claude 和 Codex 账号** —— 每个账号只需登录保存一次，即可在侧边面板、仪表盘或命令面板中切换当前账号，并查看每个账号的套餐用量
- **模型用量图表**，展示一段时间内是哪些模型在驱动你的活动和费用
- **详细的费用分析**，覆盖所有受支持的 Claude、OpenAI、OpenCode、Grok 和 Copilot 模型，并包含缓存 Token 洞察
- **单会话分析** —— 上下文窗口用量随时间的变化（逐回合显示上下文占用了多少）、在时间线上标出的压缩事件、上下文峰值与模型上限的对比，以及缓存未命中的回合
- **状态栏配额指示器**，可快速打开仪表盘

## 💎 价格

日常使用免费，少数高级功能需要 Pro。

|   | 免费版 | Pro |
|---|---|---|
| 浏览近期会话 | ✓（最近 7 天） | ✓（无限制） |
| 搜索、差异、仪表盘 | ✓（近期） | ✓（无限历史） |
| 文件时间线 | ✓（最近 3 天） | ✓（所有会话） |
| Markdown 导出与批量操作 | — | ✓ |
| 会话存档 | — | ✓ |
| 会话分叉与格式转换 | — | ✓ |
| ccassist MCP 服务器 | ✓（最近 7 天，核心工具） | ✓（完整历史 + grep/差异工具） |
| 设备数 | 2 | 5 |

当前价格和退款政策请见 [ccassist.dev](https://ccassist.dev)。

## 🔒 隐私

聊天内容始终留在你的电脑上 —— 扩展读取受支持的本地助手历史记录文件夹，并将所有数据存储在本地 SQLite 数据库中。你可以用任意网络代理自行验证：聊天内容、文件内容和差异从不会被发送出去。

默认会发送的内容：匿名设备 ID、操作系统/扩展版本，以及汇总的用量计数（例如“打开了会话”“执行了搜索”）。错误报告包含错误消息和堆栈跟踪，但绝不包含聊天内容。两者都可以在扩展设置中关闭（`enableErrorReporting`、`enableUsageStatsSharing`）。

## 🚀 快速上手

**前提条件：** VS Code 1.80.0+，以及 Claude Code、Codex、OpenCode、Grok 和/或 GitHub Copilot 的已有历史记录。

1. 从 VS Code 扩展市场安装
2. 扩展会自动识别你的 Claude、Codex、OpenCode、Grok 和 Copilot 历史记录
3. 点击活动栏中的 CCAssist 图标即可开始浏览

点击任意会话即可查看对话及其文件更改；使用 **文件更改** 查看类似提交记录的差异摘要；打开 **仪表盘** 标签页查看费用和配额分析。

## ⌨️ 命令与快捷键

打开命令面板（`Ctrl+Shift+P`）并搜索 **CCAssist** —— 可以刷新会话、打开仪表盘、刷新 API 用量额度、打开侧边面板、切换 Claude / Codex 账号等。

| 快捷键 | 操作 |
|----------|--------|
| `Ctrl+Alt+;` | 最近文件更改（快速选择） |

其他操作（显示差异、应用更改、打开文件、查看文件更改、在时间线中显示）可通过右键菜单使用。

## ⚙️ 配置

通过 **设置 → 扩展 → Claude Code Assist** 进入，或在 VS Code 设置中搜索 "Claude History"。常用选项包括：

- **`claude-history.claudeDirectory`** —— 自定义 `.claude` 路径（留空时自动检测）
- **`claude-history.archiveDirectory`** / **`claude-history.export.directory`** —— 已存档和已导出会话的存储位置
- **`claude-history.autoRefreshEnabled`** / **`autoRefreshInterval`** —— 最近会话的自动刷新
- **`claude-history.dateFormat`** —— ISO 格式或系统区域格式
- **`claude-history.resume.defaultTargetClaude`** / **`defaultTargetCodex`** —— 会话默认在哪里继续
- **`claude-history.statusBar.showApiUsage`** —— 显示配额指示器
- **`claude-history.mcp.enabled`** / **`mcp.port`** / **`mcp.providers`** / **`mcp.workspaceOnly`** —— 托管 ccassist MCP 服务器、选择端口、选择公开哪些 CLI 的历史记录，并可选择仅限当前工作区
- **`claude-history.enableErrorReporting`** / **`enableUsageStatsSharing`** —— 开关匿名报告

## 🔧 故障排除

**"No Claude, Codex, OpenCode, Grok, or Copilot directory found"（未找到 Claude、Codex、OpenCode、Grok 或 Copilot 目录）** —— 请确认相应的助手至少使用过一次且目录存在，或在设置中指定自定义路径。

**会话无法加载** —— 点击 **刷新会话** 并检查目录路径。

**差异显示不正确** —— 扩展按相对于项目根目录的路径匹配文件；请确认该文件存在于当前工作区中。

**历史记录较多时的性能** —— 会话通过缓存增量加载；如果变慢，可使用 **清除项目缓存** 或重建搜索索引。

扩展通过 WebAssembly 使用 SQLite，因此同一个构建在 Windows、macOS（Intel 和 Apple Silicon）和 Linux 上表现完全一致。

## 📝 版本历史

详细的发布说明请见 [CHANGELOG.md](./CHANGELOG.md)。

## 📄 许可证

专有软件 —— 条款请见 [LICENSE](./LICENSE)。扩展可免费使用，但源代码并不开源。

## 联系与支持

有问题、建议，或者只是想交流？欢迎联系！

**📧 邮箱：** yash@ccassist.dev
**🐦 Twitter/X：** [@yashagl](https://x.com/yashagl)

## 🔗 链接

- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [GitHub 仓库](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) · [Codex](https://github.com/openai/codex) · [OpenCode CLI](https://opencode.ai/) · [Grok](https://grok.com/) · [GitHub Copilot](https://github.com/features/copilot)

---

**为 Claude Code、Codex、OpenCode、Grok 和 GitHub Copilot 提供完整的历史记录、文件更改追踪和会话管理，全面提升你的工作流。**
