# Claude Code and Codex Assist — 適用於 VS Code、Cursor 等編輯器的對話紀錄、差異檢視與用量分析

[English](./README.md) | [简体中文](./README.zh-CN.md) | **繁體中文** | [日本語](./README.ja.md) | [한국어](./README.ko.md) | [Deutsch](./README.de.md) | [Français](./README.fr.md) | [Español](./README.es.md)

> **注意**：這是非官方擴充功能，並非由 Anthropic、OpenAI、SST/OpenCode、xAI/Grok 或 GitHub 製作，也與它們沒有任何關係。

![40 秒看懂 Claude Code and Codex Assist：工作階段紀錄、繼續工作階段、配額追蹤、差異、搜尋與跨 CLI 上下文](./assets/ccassist-promo.gif)

直接在 VS Code 中瀏覽你的 **Claude Code**、**Codex**、**OpenCode**、**Grok** 與 **GitHub Copilot** 對話紀錄 — 不必離開編輯器，就能查看檔案差異、搜尋所有對話、追蹤 Token 用量與費用，以及繼續過去的工作階段。它同時也是用量追蹤工具：單一儀表板就能顯示所有 AI 助理的各模型費用、配額消耗趨勢與每週重設歷史記錄；如果你有多個 Claude 或 Codex 登入帳號，也能一鍵切換。想知道是哪段 AI 對話改了某個檔案嗎？檔案時間軸就是 AI 編輯版的 git blame：選一個檔案，就能看到所有改動過它的工作階段與提示，並開啟確切的差異。

**🤖 支援全部五種助理：**
- **Claude Code** — `~/.claude/projects/`
- **Codex** — `~/.codex/sessions/`
- **OpenCode** — `~/.local/share/opencode/`
- **Grok** — `~/.grok/`
- **GitHub Copilot** — Copilot CLI 與 VS Code 聊天工作階段

五種助理的工作階段都會出現在同一份清單中，並以標籤與圖示區分來源。內建的 **MCP 伺服器** 甚至能讓這些助理彼此共享上下文 — 在 Claude Code 中接續你上一個 Codex 工作階段，或問 Grok 某個過去的 Claude 工作階段改了什麼。

**🌐 介面語言：** English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Deutsch | Français | Español

## 🎬 功能示範

### 🔍 全文搜尋
在數千個工作階段中搜尋每一則提示與回覆。結果依工作階段分組，並附上相符訊息、專案與費用。進階面板可讓你選擇搜尋對象（全部、你自己或助理）、比對方式（任一字詞、精確短語或正則表達式），以及是否包含工具輸出與子代理對話紀錄。

![全文搜尋](./assets/text-search.gif)

### ✅ 工作階段變更與審查
每個回合都會顯示它改動的檔案與 +/- 行數，並提供差異、復原與重新套用。開啟 **審查變更**，即可在同一處查看一段對話的所有檔案變更。

![工作階段變更與審查變更](./assets/session-changes.gif)

### ⏱️ 檔案歷程時間軸
**AI 對話版的 git blame。** 開啟任一檔案，時間軸就會列出所有編輯過它的工作階段 — 展開工作階段即可看到確切的提示與對應差異，涵蓋 Claude Code、Codex、OpenCode、Grok 與 Copilot。

![檔案歷程時間軸](./assets/timeline-demo.gif)

### 💬 對話檢視
渲染後的對話紀錄，每個回合附有 **回合變更** 卡片，另有上下文視窗圖表、快取命中率與費用。可在終端機、桌面版 App 或 Codex VS Code 擴充功能中繼續，或匯出為 Markdown。

<img src="./assets/conversation-view.png" alt="對話檢視，顯示每回合的檔案變更與繼續目標" width="420">

### 📊 配額消耗趨勢與帳戶切換
Claude、Codex、Fable 與 Grok 的即時 5 小時與每週配額卡片、預測每個時段何時耗盡的消耗趨勢圖、活動熱度圖，以及每日費用表。可保存多個 Claude 與 Codex 登入帳號，並從帳戶分頁、儀表板的方案分頁，或 **切換 Claude / Codex 帳號** 命令切換；每個帳戶的方案用量分開追蹤，配額歷史記錄不會混在一起。

<img src="./assets/account-quota.png" alt="帳戶分頁，顯示配額卡片、消耗趨勢圖與活動熱度圖" width="420">

### 📅 每週彙整
以滾動 7 天彙整工作階段、Token、費用、編輯次數與活躍天數，並與上週比較，依工具與專案細分。

<img src="./assets/weekly-digest.png" alt="每週彙整，顯示總計、每日 Token 與熱門專案" width="420">

### 📚 統一的工作階段瀏覽器
Claude Code、Codex、Grok、OpenCode、Copilot 與 Cursor 的工作階段集中在同一份清單，依專案分組，可依模型篩選，並顯示每個資料夾的費用。

<img src="./assets/chat-history.png" alt="依專案分組的工作階段分頁，並開啟了模型篩選器" width="420">

### 🔌 ccassist MCP 伺服器
本機 MCP 伺服器讓 Claude Code、Codex、Grok、OpenCode 與 Cursor 讀取你的工作階段紀錄，並接手彼此的工作。

<img src="./assets/history-mcp.png" alt="MCP 分頁，列出 CLI 代理可使用的 ccassist 工具" width="420">

### 📍 狀態列中的配額
Claude、Fable、Codex 與 Grok 的百分比隨時可見；滑鼠移上去即可查看每個時段及其重設時間。

<img src="./assets/usage-quota-statusbar.png" alt="狀態列配額指示器與滑鼠懸停視窗" width="555">


## 🌟 功能

### 工作階段與紀錄
- **統一紀錄**：涵蓋 Claude Code、Codex、OpenCode、Grok 與 GitHub Copilot，依專案整理，並自動偵測目前專案
- **快速操作與鍵盤導覽** — 直接在工作階段列上釘選、繼續或刪除；用方向鍵移動、Enter 開啟、Delete 移除
- **專案右鍵選單** — 在專案標題上按右鍵即可釘選、隱藏、在檔案總管中顯示，或在新視窗中開啟
- **隱藏個別工作階段** — 不刪除任何東西也能讓清單更清爽；隱藏的工作階段會集中在「隱藏」分頁並依專案分組，可一鍵取消隱藏，或透過多選批次隱藏
- **豐富的對話紀錄渲染** — 具語法醒目提示程式碼的 Markdown、可縮放與匯出的 Mermaid 圖表，以及用 KaTeX 離線排版的 LaTeX 數學式（複製渲染後的數學式會取得 TeX 原始碼）
- **即時搜尋篩選**，邊打字邊縮小清單範圍
- **模型篩選、釘選專案，以及釘選與重新命名**，讓龐大的紀錄保持整齊、容易瀏覽
- **繼續** 任何對話，可在終端機、桌面版 App 或 VS Code 中進行 — 或複製命令到其他地方執行
- 從任一訊息 **分支** 對話，探索其他做法而不影響原始對話 `Pro`
- Claude 與 Codex 之間的 **格式轉換**，並直接在目標助理中繼續 `Pro`
- **自動重新整理**，讓仍在變動中的近期工作階段保持最新
- **更簡潔的紀錄清單介面**，以更精簡的視覺風格讓長長的工作階段清單更容易瀏覽

### 封存與 Markdown 同步
- **工作階段封存** — Claude 與 Codex 最終會清除舊的對話紀錄；封存會將完整副本安全保存在專屬資料夾中，並可從獨立的 **已封存** 分頁瀏覽。檢視與還原封存的工作階段永遠免費。封存需要 `Pro`
- 完整工作階段的 **Markdown 匯出**，可自訂中繼資料 `Pro`
- **Markdown 同步** — 匯出的工作階段可提交到 git、在裝置間移動、連同檔案變更一起匯入回來，或以原生工作階段繼續（即使跨作業系統也可以）
- **批次操作** — 選取多個工作階段一起匯出或刪除 `Pro`

### 檔案變更與差異
- **GitHub 風格差異**，具語法醒目提示並支援多檔案
- **審查變更檢視** — 在同一處查看一段對話的所有檔案變更
- 一鍵將變更 **套用、復原或重新套用** 到你的工作區
- **檔案歷程時間軸** — AI 對話版的 git blame：時間軸會自動跟隨目前的編輯器，列出所有編輯過該檔案的工作階段，再深入任一工作階段閱讀確切的提示並開啟其差異（也可以在檔案上按右鍵開啟時間軸）

### 搜尋
- **直接搜尋檔案** — 每次搜尋都直接掃描你的工作階段檔案；不會複製到另外的索引，結果也會顯示掃描了多少個檔案
- **進階面板** — 點一下搜尋列旁的按鈕即可開啟選項：搜尋全部、只搜你的提示，或只搜助理的回覆；比對任一字詞、精確短語或正則表達式
- **工具輸出與子代理搜尋** — 可開啟搜尋工具輸入／結果與子代理對話紀錄，找出從未出現在主要對話訊息中的細節
- **依工作階段分組的結果**，附費用、Token 與訊息數，並醒目標示相符內容

### ccassist MCP 伺服器 — 在助理之間共享上下文
- **本機 MCP 伺服器** — 擴充功能可架設輕量的本機 MCP 伺服器，讓 Claude Code、Codex、Grok、OpenCode 與 Cursor 在各自環境中查詢你的工作階段紀錄（僅限本機迴路，預設關閉）
- **跨工具接續工作** — 在 Claude Code 中說 *「continue my last Codex session」*（反之亦然），代理就會取回一段精簡的交接內容：近期回合、工作階段摘要，以及改了哪些東西
- **一鍵設定** — 從側邊面板的 MCP 頁面或命令選擇區執行 **Set up ccassist (MCP + Skill)**；它會把伺服器註冊到每個 CLI，並安裝一個 `ccassist` 技能，教代理何時以及如何使用它
- **七個工具** — `search_sessions`、`list_recent_sessions`、`get_context` 與 `get_session` 用於尋找與載入過去的工作，另有 `grep_sessions`（逐字掃描對話紀錄，包含工具輸出）、`get_session_changes`（各檔案摘要或重建後的差異）與 `get_file_sessions`（哪些工作階段改動過某個檔案）`Pro`
- **隱私優先的設計** — 一切都留在你的電腦上；伺服器只綁定 localhost，並可透過 `workspaceOnly` 設定限制只開放目前工作區的工作階段

### 分析與費用追蹤
- **儀表板**，提供用量統計、活動時間軸與費用趨勢
- **配額追蹤** — 即時 Claude/Codex 配額卡片、消耗趨勢圖、每週重設歷史記錄與每週摘要，並在可取得時依模型細分，包括 Sonnet、Opus 與 Fable
- **多個 Claude 與 Codex 帳戶** — 每個登入帳號只需保存一次，即可從側邊面板、儀表板或命令選擇區切換使用中的帳戶，並查看各帳戶的方案用量
- **模型用量圖表**，顯示隨時間推移哪些模型帶動了你的活動與費用
- **詳細的費用分析**，涵蓋所有支援的 Claude、OpenAI、OpenCode、Grok 與 Copilot 模型，包含快取 Token 分析
- **單一工作階段分析** — 上下文視窗用量隨時間的變化（逐回合查看上下文用到多滿）、在時間軸上標示的壓縮事件、上下文峰值與模型上限的對比，以及快取未命中的回合
- **狀態列配額指示器**，可快速開啟儀表板

## 💎 價格

日常使用完全免費。少數進階功能需要 Pro。

|   | 免費版 | Pro |
|---|---|---|
| 瀏覽近期工作階段 | ✓（最近 7 天） | ✓（無限制） |
| 搜尋、差異、儀表板 | ✓（近期） | ✓（完整紀錄） |
| 檔案時間軸 | ✓（最近 3 天） | ✓（所有工作階段） |
| Markdown 匯出與批次操作 | — | ✓ |
| 工作階段封存 | — | ✓ |
| 工作階段分支與格式轉換 | — | ✓ |
| ccassist MCP 伺服器 | ✓（最近 7 天、核心工具） | ✓（完整紀錄 + grep/差異工具） |
| 裝置數 | 2 | 5 |

目前的價格與退款政策請參閱 [ccassist.dev](https://ccassist.dev)。

## 🔒 隱私

對話內容只會留在你的電腦上 — 擴充功能會讀取受支援助理的本機紀錄資料夾，並將所有資料存放在本機的 SQLite 資料庫中。你可以用任何網路代理工具驗證：絕不會傳送任何對話文字、檔案內容或差異。

預設會傳送的內容：匿名化的裝置 ID、作業系統／擴充功能版本，以及彙總的用量計數（例如「開啟了工作階段」、「執行了搜尋」）。錯誤報告包含錯誤訊息與堆疊追蹤，絕不包含對話內容。兩者都可以在擴充功能設定中關閉（`enableErrorReporting`、`enableUsageStatsSharing`）。

## 🚀 開始使用

**事前準備：** VS Code 1.80.0 以上版本，以及既有的 Claude Code、Codex、OpenCode、Grok 和／或 GitHub Copilot 紀錄。

1. 從 VS Code 擴充功能市集安裝
2. 擴充功能會自動偵測你的 Claude、Codex、OpenCode、Grok 與 Copilot 紀錄
3. 點選活動列中的 CCAssist 圖示開始瀏覽

點選任一工作階段即可查看對話與其檔案變更；使用 **檔案變更** 取得類似 commit 的差異摘要；開啟 **儀表板** 分頁查看費用與配額分析。

## ⌨️ 命令與快速鍵

開啟命令選擇區（`Ctrl+Shift+P`）並搜尋 **CCAssist** — 可重新整理工作階段、開啟儀表板、重新整理 API 用量配額、開啟側邊面板、切換 Claude / Codex 帳號等。

| 快速鍵 | 動作 |
|----------|--------|
| `Ctrl+Alt+;` | 最近檔案變更（快速選擇） |

其他動作（顯示差異、套用變更、開啟檔案、檢視檔案變更、在時間軸中顯示）可從右鍵選單使用。

## ⚙️ 設定

透過 **設定 → 擴充功能 → Claude Code Assist** 存取，或在 VS Code 設定中搜尋「Claude History」。實用選項包括：

- **`claude-history.claudeDirectory`** — 自訂 `.claude` 路徑（留空則自動偵測）
- **`claude-history.archiveDirectory`** / **`claude-history.export.directory`** — 封存與匯出工作階段的存放位置
- **`claude-history.autoRefreshEnabled`** / **`autoRefreshInterval`** — 近期工作階段的自動重新整理
- **`claude-history.dateFormat`** — ISO 或你系統的地區格式
- **`claude-history.resume.defaultTargetClaude`** / **`defaultTargetCodex`** — 工作階段預設的繼續位置
- **`claude-history.statusBar.showApiUsage`** — 顯示配額指示器
- **`claude-history.mcp.enabled`** / **`mcp.port`** / **`mcp.providers`** / **`mcp.workspaceOnly`** — 架設 ccassist MCP 伺服器、選擇連接埠、挑選要開放哪些 CLI 的紀錄，並可選擇限定在目前工作區
- **`claude-history.enableErrorReporting`** / **`enableUsageStatsSharing`** — 開關匿名回報

## 🔧 疑難排解

**「找不到 Claude、Codex、OpenCode、Grok 或 Copilot 目錄」** — 請確認相關助理至少使用過一次且目錄存在，或在設定中指定自訂路徑。

**工作階段無法載入** — 點選 **重新整理工作階段** 並確認目錄路徑。

**差異顯示不正確** — 擴充功能會依專案根目錄的相對路徑比對檔案；請確認檔案存在於目前的工作區中。

**紀錄量很大時的效能** — 工作階段會搭配快取逐步載入；如果變慢，請使用 **清除專案快取** 或重建搜尋索引。

擴充功能透過 WebAssembly 使用 SQLite，因此同一個版本在 Windows、macOS（Intel 與 Apple Silicon）和 Linux 上的運作完全相同。

## 📝 版本紀錄

詳細的版本說明請參閱 [CHANGELOG.md](./CHANGELOG.md)。

## 📄 授權

專有軟體 — 條款請參閱 [LICENSE](./LICENSE)。擴充功能可免費使用，但原始碼並未開源。

## 聯絡與支援

有問題、建議，或只是想打聲招呼？歡迎與我聯絡！

**📧 Email：** yash@ccassist.dev
**🐦 Twitter/X：** [@yashagl](https://x.com/yashagl)

## 🔗 連結

- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [GitHub 儲存庫](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) · [Codex](https://github.com/openai/codex) · [OpenCode CLI](https://opencode.ai/) · [Grok](https://grok.com/) · [GitHub Copilot](https://github.com/features/copilot)

---

**透過完整的對話紀錄、檔案變更追蹤與工作階段管理，提升你在 Claude Code、Codex、OpenCode、Grok 與 GitHub Copilot 上的工作流程。**
