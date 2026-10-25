# Claude Code and Codex Assist — Verlauf, Diffs & Nutzungsanalyse für VS Code, Cursor & mehr

[English](./README.md) | [简体中文](./README.zh-CN.md) | [繁體中文](./README.zh-TW.md) | [日本語](./README.ja.md) | [한국어](./README.ko.md) | **Deutsch** | [Français](./README.fr.md) | [Español](./README.es.md)

> **Hinweis**: Dies ist eine inoffizielle Extension. Sie wurde nicht von Anthropic, OpenAI, SST/OpenCode, xAI/Grok oder GitHub entwickelt und steht in keiner Verbindung zu diesen Unternehmen.

![Claude Code and Codex Assist in 40 Sekunden: Sitzungsverlauf, Fortsetzen, Kontingent-Tracking, Diffs, Suche und CLI-übergreifender Kontext](./assets/ccassist-promo.gif)

Durchsuche deinen Chatverlauf aus **Claude Code**, **Codex**, **OpenCode**, **Grok** und **GitHub Copilot** direkt in VS Code: Datei-Diffs ansehen, alle Unterhaltungen durchsuchen, Token-Verbrauch und Kosten verfolgen und frühere Sitzungen fortsetzen, ohne den Editor zu verlassen. Gleichzeitig ist die Extension ein Nutzungs-Tracker: Ein einziges Dashboard zeigt Kosten pro Modell, Kontingent-Burndown und den Verlauf der wöchentlichen Resets für alle deine KI-Assistenten. Und wenn du mehr als ein Claude- oder Codex-Login nutzt, wechselst du mit einem Klick zwischen ihnen. Schon mal gefragt, welche KI-Unterhaltung eine Datei geändert hat? Die Datei-Zeitachse ist git blame für KI-Änderungen: Wähle eine Datei, sieh jede Sitzung und jeden Prompt, der sie berührt hat, und öffne genau das passende Diff.

**🤖 Funktioniert mit allen fünf Assistenten:**
- **Claude Code** — `~/.claude/projects/`
- **Codex** — `~/.codex/sessions/`
- **OpenCode** — `~/.local/share/opencode/`
- **Grok** — `~/.grok/`
- **GitHub Copilot** — Copilot CLI und Chat-Sitzungen in VS Code

Sitzungen aus allen fünf erscheinen in einer gemeinsamen Liste, mit Badges und Logos, die sie unterscheidbar machen. Ein integrierter **MCP-Server** lässt die Assistenten sogar Kontext miteinander teilen: Setze deine letzte Codex-Sitzung aus Claude Code heraus fort oder frag Grok, was eine frühere Claude-Sitzung geändert hat.

**🌐 Sprachen der Oberfläche:** English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Deutsch | Français | Español

## 🎬 Funktionen in Aktion

### 🔍 Volltextsuche
Durchsuche jeden Prompt und jede Antwort über Tausende Sitzungen. Die Treffer sind nach Sitzung gruppiert, mit passender Nachricht, Projekt und Kosten. Im erweiterten Bereich wählst du, wen du durchsuchst (alle, dich selbst oder den Assistenten), wie gesucht wird (beliebige Wörter, exakte Phrase oder Regex) und ob Tool-Ausgaben und Subagenten-Transkripte einbezogen werden.

![Volltextsuche](./assets/text-search.gif)

### ✅ Sitzungsänderungen & Änderungen prüfen
Jeder Turn zeigt die Dateien, die er berührt hat, mit +/- Zählern, Diff, Rückgängig und erneut Anwenden. Unter **Änderungen prüfen** siehst du alle Dateiänderungen einer Unterhaltung an einem Ort.

![Sitzungsänderungen und Änderungen prüfen](./assets/session-changes.gif)

### ⏱️ Datei-Zeitachse
**git blame, aber für KI-Unterhaltungen.** Öffne eine beliebige Datei, und die Zeitachse zeigt jede Sitzung, die sie bearbeitet hat. Klapp eine Sitzung auf, um den genauen Prompt und sein Diff zu sehen – über Claude Code, Codex, OpenCode, Grok und Copilot hinweg.

![Datei-Zeitachse](./assets/timeline-demo.gif)

### 💬 Chat-Ansicht
Gerendertes Transkript mit einer Karte **Turn-Änderungen** pro Turn, Kontextfenster-Graph, Cache-Trefferquote und Kosten. Setze die Sitzung im Terminal, in der Desktop-App oder in der Codex-Extension für VS Code fort, oder exportiere sie als Markdown.

<img src="./assets/conversation-view.png" alt="Chat-Ansicht mit Dateiänderungen pro Turn und Zielen zum Fortsetzen" width="420">

### 📊 Kontingent-Burndown & Kontowechsel
Live-Karten für das 5-Stunden- und Wochenkontingent von Claude, Codex, Fable und Grok, Burndown-Charts, die vorhersagen, wann jedes Fenster erschöpft ist, eine Aktivitäts-Heatmap und eine Kostentabelle Tag für Tag. Speichere mehrere Claude- und Codex-Logins und wechsle zwischen ihnen im Konto-Tab, im Plan-Tab des Dashboards oder mit dem Befehl **Claude-/Codex-Konto wechseln**. Die Plan-Nutzung wird für jedes Konto getrennt erfasst, sodass sich der Kontingentverlauf verschiedener Konten nie vermischt.

<img src="./assets/account-quota.png" alt="Konto-Tab mit Kontingentkarten, Burndown-Chart und Aktivitäts-Heatmap" width="420">

### 📅 Wochenrückblick
Eine gleitende 7-Tage-Zusammenfassung von Sitzungen, Tokens, Kosten, Änderungen und aktiven Tagen im Vergleich zur Vorwoche, aufgeteilt nach Tool und Projekt.

<img src="./assets/weekly-digest.png" alt="Wochenrückblick mit Summen, Tokens pro Tag und Top-Projekten" width="420">

### 📚 Gemeinsamer Sitzungsbrowser
Sitzungen aus Claude Code, Codex, Grok, OpenCode, Copilot und Cursor in einer Liste, nach Projekt gruppiert, mit Filtern pro Modell und Kosten pro Ordner.

<img src="./assets/chat-history.png" alt="Sitzungen-Tab nach Projekt gruppiert, mit geöffnetem Modellfilter" width="420">

### 🔌 ccassist MCP-Server
Ein lokaler MCP-Server erlaubt Claude Code, Codex, Grok, OpenCode und Cursor, deinen Sitzungsverlauf zu lesen und die Arbeit des jeweils anderen fortzusetzen.

<img src="./assets/history-mcp.png" alt="MCP-Tab mit den ccassist-Tools, die CLI-Agenten zur Verfügung stehen" width="420">

### 📍 Kontingent in der Statusleiste
Die Prozentwerte für Claude, Fable, Codex und Grok sind immer sichtbar. Fahr mit der Maus darüber, um jedes Fenster mit seiner Reset-Zeit zu sehen.

<img src="./assets/usage-quota-statusbar.png" alt="Kontingentanzeige in der Statusleiste mit Hover-Popup" width="555">


## 🌟 Funktionen

### Sitzungen & Verlauf
- **Gemeinsamer Verlauf** für Claude Code, Codex, OpenCode, Grok und GitHub Copilot, nach Projekt geordnet und mit Erkennung des aktuellen Projekts
- **Schnellaktionen & Tastaturnavigation** – Sitzungen direkt aus der Zeile anheften, fortsetzen oder löschen; mit den Pfeiltasten bewegen, mit Enter öffnen, mit Entf entfernen
- **Kontextmenü für Projekte** – Rechtsklick auf einen Projektkopf, um das Projekt anzuheften, auszublenden, im Dateimanager anzuzeigen oder in einem neuen Fenster zu öffnen
- **Einzelne Sitzungen ausblenden** – die Liste aufräumen, ohne etwas zu löschen; ausgeblendete Sitzungen landen nach Projekt gruppiert im Tab „Ausgeblendet“, lassen sich per Klick wieder einblenden oder per Mehrfachauswahl gesammelt ausblenden
- **Ausführliches Transkript-Rendering** – Markdown mit Syntax-Highlighting für Code, Mermaid-Diagramme mit Zoom und Export sowie LaTeX-Formeln, offline gesetzt mit KaTeX (beim Kopieren gerenderter Formeln bekommst du den TeX-Quelltext zurück)
- **Live-Suchfilter**, der die Liste schon beim Tippen eingrenzt
- **Modellfilter, angeheftete Projekte sowie Anheften & Umbenennen** halten auch große Verläufe übersichtlich
- **Fortsetzen** jeder Unterhaltung im Terminal, in der Desktop-App oder in VS Code – oder den Befehl kopieren und anderswo ausführen
- **Forken** einer Unterhaltung ab einer beliebigen Nachricht, um eine Alternative auszuprobieren, ohne das Original anzutasten `Pro`
- **Formatkonverter** zwischen Claude und Codex, mit direktem Fortsetzen im Ziel-Assistenten `Pro`
- **Automatische Aktualisierung** hält neue Sitzungen aktuell, solange sie sich noch ändern
- **Aufgeräumtere Verlaufsliste** mit einem minimalistischeren Stil, der auch lange Sitzungslisten leichter erfassbar macht

### Archivierung & Markdown-Sync
- **Sitzungsarchiv** – Claude und Codex räumen alte Transkripte irgendwann auf; die Archivierung bewahrt eine vollständige Kopie in einem eigenen Ordner auf, durchsuchbar über einen eigenen Tab **Archiviert**. Archivierte Sitzungen ansehen und wiederherstellen ist immer kostenlos. Archivieren mit `Pro`
- **Markdown-Export** ganzer Sitzungen mit anpassbaren Metadaten `Pro`
- **Markdown-Sync** – exportierte Sitzungen lassen sich in git committen, auf andere Geräte übertragen, samt Dateiänderungen wieder importieren oder als native Sitzung fortsetzen (sogar betriebssystemübergreifend)
- **Massenaktionen** – mehrere Sitzungen auswählen und gemeinsam exportieren oder löschen `Pro`

### Dateiänderungen & Diffs
- **Diffs im GitHub-Stil** mit Syntax-Highlighting und Unterstützung für mehrere Dateien
- **Ansicht „Änderungen prüfen“** – alle Dateiänderungen einer Unterhaltung an einem Ort
- **Anwenden, rückgängig machen oder erneut anwenden** von Änderungen in deinem Workspace mit einem Klick
- **Datei-Zeitachse** – git blame für KI-Unterhaltungen: Die Zeitachse folgt automatisch dem aktiven Editor und listet jede Sitzung auf, die die Datei bearbeitet hat. Von dort gehst du in jede Sitzung, liest den genauen Prompt und öffnest sein Diff (oder öffnest die Zeitachse per Rechtsklick auf eine Datei)

### Suche
- **Direkte Dateisuche** – jede Suche durchsucht deine Sitzungsdateien direkt; nichts wird in einen separaten Index kopiert, und die Ergebnisse zeigen, wie viele Dateien durchsucht wurden
- **Erweiterter Bereich** – ein Klick neben der Suchleiste öffnet wählbare Optionen: alle durchsuchen, nur deine Prompts oder nur die Antworten des Assistenten; beliebige Wörter, eine exakte Phrase oder einen regulären Ausdruck suchen
- **Suche in Tool-Ausgaben und Subagenten** – Tool-Eingaben/-Ergebnisse und Subagenten-Transkripte zuschalten, um Details zu finden, die nie in den eigentlichen Chat-Nachrichten auftauchen
- **Nach Sitzung gruppierte Ergebnisse** mit Kosten, Tokens und Nachrichtenanzahl sowie hervorgehobenen Treffern

### ccassist MCP-Server – Kontext zwischen Assistenten teilen
- **Lokaler MCP-Server** – die Extension kann einen schlanken lokalen MCP-Server bereitstellen, damit Claude Code, Codex, Grok, OpenCode und Cursor aus jedem dieser Tools heraus deinen Sitzungsverlauf abfragen können (nur Loopback, standardmäßig aus)
- **Arbeit toolübergreifend fortsetzen** – sag in Claude Code *„setz meine letzte Codex-Sitzung fort“* (oder umgekehrt), und der Agent holt sich einen kompakten Übergabeblock: letzte Turns, Zusammenfassung der Sitzung und was sich geändert hat
- **Einrichtung per Klick** – führe **Set up ccassist (MCP + Skill)** auf der MCP-Seite der Seitenleiste oder über die Befehlspalette aus; der Server wird bei jeder CLI registriert, und ein `ccassist`-Skill wird installiert, der Agenten beibringt, wann und wie sie ihn nutzen
- **Sieben Tools** – `search_sessions`, `list_recent_sessions`, `get_context` und `get_session` zum Finden und Laden früherer Arbeit, dazu `grep_sessions` (wörtlicher Scan der Transkripte inklusive Tool-Ausgaben), `get_session_changes` (Zusammenfassungen pro Datei oder rekonstruierte Diffs) und `get_file_sessions` (welche Sitzungen eine Datei berührt haben) `Pro`
- **Privat by Design** – alles bleibt auf deinem Rechner; der Server bindet sich nur an localhost, und mit der Einstellung `workspaceOnly` lässt er sich auf Sitzungen des aktuellen Workspace beschränken

### Analysen & Kosten-Tracking
- **Dashboard** mit Nutzungsstatistiken, Aktivitätsverläufen und Kostentrends
- **Kontingent-Tracking** – Live-Kontingentkarten für Claude/Codex, Burndown-Chart, Verlauf der wöchentlichen Resets und Wochenzusammenfassung, mit Aufschlüsselung nach Modell inklusive Sonnet, Opus und Fable, sofern verfügbar
- **Mehrere Claude- und Codex-Konten** – jedes Login einmal speichern, das aktive Konto in der Seitenleiste, im Dashboard oder über die Befehlspalette wechseln und die Plan-Nutzung pro Konto sehen
- **Modellnutzungs-Charts** zeigen, welche Modelle deine Aktivität und Kosten im Zeitverlauf treiben
- **Detaillierte Kostenanalyse** über alle unterstützten Modelle von Claude, OpenAI, OpenCode, Grok und Copilot, inklusive Einblicken in Cache-Tokens
- **Analysen pro Sitzung** – Kontextfenster-Auslastung im Zeitverlauf (wie voll der Kontext Turn für Turn wurde), Compaction-Ereignisse auf der Zeitachse markiert, maximaler Kontext im Vergleich zum Modelllimit und Turns ohne Cache-Treffer
- **Kontingentanzeige in der Statusleiste** mit Schnellzugriff aufs Dashboard

## 💎 Preise

Kostenlos für den Alltag. Einige erweiterte Funktionen erfordern Pro.

|   | Free | Pro |
|---|---|---|
| Aktuelle Sitzungen ansehen | ✓ (letzte 7 Tage) | ✓ (unbegrenzt) |
| Suche, Diffs, Dashboard | ✓ (aktuelle) | ✓ (unbegrenzter Verlauf) |
| Datei-Zeitachse | ✓ (letzte 3 Tage) | ✓ (alle Sitzungen) |
| Markdown-Export & Massenaktionen | — | ✓ |
| Sitzungsarchivierung | — | ✓ |
| Sitzungen forken & Formatkonvertierung | — | ✓ |
| ccassist MCP-Server | ✓ (letzte 7 Tage, Basis-Tools) | ✓ (gesamter Verlauf + grep-/Diff-Tools) |
| Geräte | 2 | 5 |

Aktuelle Preise und die Rückerstattungsrichtlinie findest du auf [ccassist.dev](https://ccassist.dev).

## 🔒 Datenschutz

Chat-Inhalte bleiben auf deinem Rechner. Die Extension liest die lokalen Verlaufsordner der unterstützten Assistenten und speichert alles in einer lokalen SQLite-Datenbank. Du kannst das mit jedem Netzwerk-Proxy überprüfen: Chat-Texte, Dateiinhalte oder Diffs werden nie gesendet.

Standardmäßig gesendet werden: eine anonymisierte Geräte-ID, Betriebssystem- und Extension-Version sowie aggregierte Nutzungszähler (z. B. „Sitzung geöffnet“, „Suche ausgeführt“). Fehlerberichte enthalten Fehlermeldungen und Stack-Traces, aber nie Chat-Inhalte. Beides lässt sich in den Einstellungen der Extension abschalten (`enableErrorReporting`, `enableUsageStatsSharing`).

## 🚀 Erste Schritte

**Voraussetzungen:** VS Code 1.80.0+ und ein vorhandener Verlauf aus Claude Code, Codex, OpenCode, Grok und/oder GitHub Copilot.

1. Installiere die Extension aus dem VS Code Extensions Marketplace
2. Die Extension erkennt deinen Verlauf aus Claude, Codex, OpenCode, Grok und Copilot automatisch
3. Klicke in der Aktivitätsleiste auf das CCAssist-Symbol und leg los

Klicke auf eine Sitzung, um die Unterhaltung und ihre Dateiänderungen zu sehen. Unter **Dateiänderungen** findest du eine Diff-Übersicht im Commit-Stil, und der Tab **Dashboard** liefert Analysen zu Kosten und Kontingent.

## ⌨️ Befehle & Tastenkürzel

Öffne die Befehlspalette (`Ctrl+Shift+P`) und suche nach **CCAssist**: Sitzungen aktualisieren, Dashboard öffnen, API-Nutzungskontingent aktualisieren, Seitenleiste öffnen, Claude-/Codex-Konto wechseln und mehr.

| Tastenkürzel | Aktion |
|----------|--------|
| `Ctrl+Alt+;` | Letzte Dateiänderungen (Schnellauswahl) |

Weitere Aktionen (Diff anzeigen, Änderungen anwenden, Datei öffnen, Dateiänderungen ansehen, in der Zeitachse anzeigen) erreichst du über die Kontextmenüs per Rechtsklick.

## ⚙️ Konfiguration

Zu finden unter **Einstellungen → Erweiterungen → Claude Code Assist**, oder suche in den VS Code-Einstellungen nach „Claude History“. Nützliche Optionen:

- **`claude-history.claudeDirectory`** – eigener `.claude`-Pfad (wird automatisch erkannt, wenn leer)
- **`claude-history.archiveDirectory`** / **`claude-history.export.directory`** – wo archivierte und exportierte Sitzungen gespeichert werden
- **`claude-history.autoRefreshEnabled`** / **`autoRefreshInterval`** – automatische Aktualisierung für aktuelle Sitzungen
- **`claude-history.dateFormat`** – ISO oder das regionale Format deines Systems
- **`claude-history.resume.defaultTargetClaude`** / **`defaultTargetCodex`** – wo Sitzungen standardmäßig fortgesetzt werden
- **`claude-history.statusBar.showApiUsage`** – Kontingentanzeige einblenden
- **`claude-history.mcp.enabled`** / **`mcp.port`** / **`mcp.providers`** / **`mcp.workspaceOnly`** – den ccassist MCP-Server bereitstellen, seinen Port festlegen, auswählen, welche CLI-Verläufe er freigibt, und ihn optional auf den aktuellen Workspace beschränken
- **`claude-history.enableErrorReporting`** / **`enableUsageStatsSharing`** – anonyme Berichte ein- oder ausschalten

## 🔧 Fehlerbehebung

**„No Claude, Codex, OpenCode, Grok, or Copilot directory found“** – stelle sicher, dass der jeweilige Assistent mindestens einmal benutzt wurde und das Verzeichnis existiert, oder lege in den Einstellungen einen eigenen Pfad fest.

**Sitzungen werden nicht geladen** – klicke auf **Sitzungen aktualisieren** und prüfe deine Verzeichnispfade.

**Diffs werden nicht korrekt angezeigt** – die Extension ordnet Dateien über den relativen Pfad ab dem Projektstamm zu; stelle sicher, dass die Datei in deinem aktuellen Workspace existiert.

**Performance bei großem Verlauf** – Sitzungen werden inkrementell und mit Caching geladen; wenn es langsam wird, nutze **Projektcache leeren** oder baue den Suchindex neu auf.

Die Extension nutzt SQLite über WebAssembly und funktioniert daher mit ein und demselben Build identisch unter Windows, macOS (Intel & Apple Silicon) und Linux.

## 📝 Versionsverlauf

Ausführliche Release Notes findest du in [CHANGELOG.md](./CHANGELOG.md).

## 📄 Lizenz

Proprietär – die Bedingungen findest du in [LICENSE](./LICENSE). Die Extension ist kostenlos nutzbar, der Quellcode ist jedoch nicht Open Source.

## Kontakt & Support

Fragen, Vorschläge oder einfach Lust auf Austausch? Melde dich!

**📧 E-Mail:** yash@ccassist.dev
**🐦 Twitter/X:** [@yashagl](https://x.com/yashagl)

## 🔗 Links

- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [GitHub-Repository](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) · [Codex](https://github.com/openai/codex) · [OpenCode CLI](https://opencode.ai/) · [Grok](https://grok.com/) · [GitHub Copilot](https://github.com/features/copilot)

---

**Bring deinen Workflow voran – mit umfassendem Verlauf, Tracking von Dateiänderungen und Sitzungsverwaltung für Claude Code, Codex, OpenCode, Grok und GitHub Copilot.**
