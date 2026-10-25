# Claude Code and Codex Assist — Historique, diffs et analyse d’utilisation pour VS Code, Cursor et plus

[English](./README.md) | [简体中文](./README.zh-CN.md) | [繁體中文](./README.zh-TW.md) | [日本語](./README.ja.md) | [한국어](./README.ko.md) | [Deutsch](./README.de.md) | **Français** | [Español](./README.es.md)

> **Remarque** : cette extension n’est pas officielle. Elle n’est ni conçue par Anthropic, OpenAI, SST/OpenCode, xAI/Grok ou GitHub, ni affiliée à ces entreprises.

![Claude Code and Codex Assist en 40 secondes : historique des sessions, reprise, suivi du quota, diffs, recherche et contexte partagé entre CLI](./assets/ccassist-promo.gif)

Parcourez votre historique de chat **Claude Code**, **Codex**, **OpenCode**, **Grok** et **GitHub Copilot** directement dans VS Code : consultez les diffs de fichiers, recherchez dans toutes vos conversations, suivez votre consommation de tokens et vos coûts, et reprenez d’anciennes sessions sans quitter l’éditeur. L’extension fait aussi office de suivi d’utilisation : un seul tableau de bord affiche le coût par modèle, la consommation du quota et l’historique des réinitialisations hebdomadaires pour tous vos assistants IA, et si vous utilisez plusieurs comptes Claude ou Codex, vous passez de l’un à l’autre en un clic. Vous vous êtes déjà demandé quelle conversation IA avait modifié un fichier ? La chronologie de fichier, c’est git blame pour les modifications faites par l’IA : choisissez un fichier, voyez chaque session et chaque prompt qui l’ont touché, et ouvrez le diff exact.

**🤖 Compatible avec les cinq assistants :**
- **Claude Code** — `~/.claude/projects/`
- **Codex** — `~/.codex/sessions/`
- **OpenCode** — `~/.local/share/opencode/`
- **Grok** — `~/.grok/`
- **GitHub Copilot** — sessions Copilot CLI et chat VS Code

Les sessions des cinq assistants apparaissent dans une seule liste, avec des badges et des logos pour les distinguer. Un **serveur MCP** intégré permet même aux assistants de partager leur contexte : reprenez votre dernière session Codex depuis Claude Code, ou demandez à Grok ce qu’une ancienne session Claude a modifié.

**🌐 Langues de l’interface :** English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Deutsch | Français | Español

## 🎬 Démonstrations

### 🔍 Recherche plein texte
Recherchez dans chaque prompt et chaque réponse, sur des milliers de sessions. Les résultats sont regroupés par session, avec le message correspondant, le projet et le coût. Le panneau avancé vous permet de choisir où chercher (partout, dans vos messages ou dans ceux de l’assistant), comment faire correspondre (n’importe quel mot, phrase exacte ou expression régulière) et s’il faut inclure les sorties d’outils et les transcriptions des sous-agents.

![Recherche plein texte](./assets/text-search.gif)

### ✅ Modifications de session et examen
Chaque tour affiche les fichiers modifiés avec le nombre de lignes +/-, le diff, l’annulation et la réapplication. Ouvrez **Examiner les modifications** pour voir au même endroit toutes les modifications de fichiers d’une conversation.

![Modifications de session et vue Examiner les modifications](./assets/session-changes.gif)

### ⏱️ Chronologie de fichier
**git blame, mais pour vos conversations IA.** Ouvrez n’importe quel fichier : la chronologie affiche toutes les sessions qui l’ont modifié. Dépliez une session pour voir le prompt exact et son diff, dans Claude Code, Codex, OpenCode, Grok et Copilot.

![Chronologie de fichier](./assets/timeline-demo.gif)

### 💬 Vue conversation
Transcription rendue avec une carte **Modifications du tour** pour chaque tour, un graphique de la fenêtre de contexte, le taux de succès du cache et le coût. Reprenez la session dans le terminal, l’application de bureau ou l’extension Codex pour VS Code, ou exportez-la en Markdown.

<img src="./assets/conversation-view.png" alt="Vue conversation avec les modifications de fichiers par tour et les cibles de reprise" width="420">

### 📊 Consommation du quota et changement de compte
Cartes de quota 5 heures et hebdomadaire en direct pour Claude, Codex, Fable et Grok, graphiques de consommation qui prévoient quand chaque fenêtre sera épuisée, carte thermique d’activité et tableau des coûts jour par jour. Gardez plusieurs comptes Claude et Codex et passez de l’un à l’autre depuis l’onglet Compte, l’onglet Utilisation du plan du tableau de bord ou la commande **Changer de compte Claude / Codex** ; l’utilisation du plan est suivie séparément pour chaque compte, si bien que l’historique du quota ne mélange jamais les comptes.

<img src="./assets/account-quota.png" alt="Onglet Compte avec les cartes de quota, le graphique de consommation et la carte thermique d’activité" width="420">

### 📅 Récap hebdomadaire
Un résumé glissant sur 7 jours de vos sessions, tokens, coûts, modifications et jours actifs, comparé à la semaine précédente, avec une répartition par outil et par projet.

<img src="./assets/weekly-digest.png" alt="Récap hebdomadaire avec les totaux, les tokens jour par jour et les principaux projets" width="420">

### 📚 Navigateur de sessions unifié
Les sessions Claude Code, Codex, Grok, OpenCode, Copilot et Cursor dans une seule liste, regroupées par projet, avec des filtres par modèle et le coût de chaque dossier.

<img src="./assets/chat-history.png" alt="Onglet Sessions regroupé par projet, avec le filtre par modèle ouvert" width="420">

### 🔌 Serveur MCP ccassist
Un serveur MCP local permet à Claude Code, Codex, Grok, OpenCode et Cursor de lire votre historique de sessions et de reprendre le travail des uns et des autres.

<img src="./assets/history-mcp.png" alt="Onglet MCP listant les outils ccassist disponibles pour les agents CLI" width="420">

### 📍 Le quota dans la barre d’état
Les pourcentages Claude, Fable, Codex et Grok sont toujours visibles ; survolez-les pour voir chaque fenêtre et son heure de réinitialisation.

<img src="./assets/usage-quota-statusbar.png" alt="Indicateur de quota dans la barre d’état avec son infobulle" width="555">


## 🌟 Fonctionnalités

### Sessions et historique
- **Historique unifié** pour Claude Code, Codex, OpenCode, Grok et GitHub Copilot, organisé par projet avec détection du projet en cours
- **Actions rapides et navigation au clavier** — épinglez, reprenez ou supprimez une session depuis sa ligne ; déplacez-vous avec les flèches, ouvrez avec Entrée, supprimez avec Suppr
- **Menu contextuel de projet** — clic droit sur l’en-tête d’un projet pour l’épingler, le masquer, l’afficher dans votre gestionnaire de fichiers ou l’ouvrir dans une nouvelle fenêtre
- **Masquage de sessions individuelles** — allégez la liste sans rien supprimer ; les sessions masquées sont regroupées par projet dans l’onglet Masquées, avec affichage en un clic ou masquage groupé via la multisélection
- **Rendu riche des transcriptions** — Markdown avec code en coloration syntaxique, diagrammes Mermaid avec zoom et export, et formules LaTeX composées hors ligne avec KaTeX (copier une formule rendue vous redonne sa source TeX)
- **Filtre de recherche en direct** pour affiner la liste au fil de la frappe
- **Filtres par modèle, projets épinglés, épinglage et renommage** pour garder un historique volumineux ordonné et facile à parcourir
- **Reprise** de n’importe quelle conversation dans le terminal, l’application de bureau ou VS Code — ou copie de la commande pour l’exécuter ailleurs
- **Fork** d’une conversation à partir de n’importe quel message, pour explorer une autre piste sans toucher à l’original `Pro`
- **Conversion de format** entre Claude et Codex, avec reprise directe dans l’assistant cible `Pro`
- **Actualisation automatique** des sessions récentes tant qu’elles évoluent encore
- **Liste d’historique épurée**, au style visuel plus minimal, pour parcourir plus facilement les longues listes de sessions

### Archivage et synchronisation Markdown
- **Archivage des sessions** — Claude et Codex finissent par supprimer les anciennes transcriptions ; l’archivage en conserve une copie intégrale dans un dossier dédié, consultable depuis un onglet **Archivées**. Consulter et restaurer les sessions archivées est toujours gratuit. `Pro` pour archiver
- **Export Markdown** des sessions complètes, avec métadonnées personnalisables `Pro`
- **Synchronisation Markdown** — les sessions exportées peuvent être committées dans git, transférées d’un appareil à l’autre, réimportées avec leurs modifications de fichiers intactes ou reprises comme une session native (même d’un système d’exploitation à l’autre)
- **Actions groupées** — sélectionnez plusieurs sessions pour les exporter ou les supprimer d’un coup `Pro`

### Modifications de fichiers et diffs
- **Diffs façon GitHub** avec coloration syntaxique et prise en charge de plusieurs fichiers
- **Vue Examiner les modifications** — toutes les modifications de fichiers d’une conversation au même endroit
- **Appliquer, annuler ou réappliquer** des modifications dans votre workspace en un clic
- **Chronologie de fichier** — git blame pour vos conversations IA : la chronologie suit automatiquement l’éditeur actif et liste toutes les sessions qui ont modifié le fichier ; ouvrez ensuite n’importe quelle session pour lire le prompt exact et afficher son diff (ou faites un clic droit sur un fichier pour ouvrir sa chronologie)

### Recherche
- **Recherche directe dans les fichiers** — chaque recherche parcourt directement vos fichiers de session ; rien n’est copié dans un index séparé, et les résultats indiquent combien de fichiers ont été analysés
- **Panneau avancé** — un clic à côté de la barre de recherche ouvre des options au choix : chercher partout, uniquement dans vos prompts ou uniquement dans les réponses de l’assistant ; faire correspondre n’importe quel mot, une phrase exacte ou une expression régulière
- **Recherche dans les sorties d’outils et les sous-agents** — incluez les entrées/résultats d’outils et les transcriptions des sous-agents pour trouver des détails absents des messages principaux
- **Résultats regroupés par session** avec coût, nombre de tokens et de messages, et correspondances surlignées

### Serveur MCP ccassist — partager le contexte entre assistants
- **Serveur MCP local** — l’extension peut héberger un serveur MCP local léger pour que Claude Code, Codex, Grok, OpenCode et Cursor puissent interroger votre historique de sessions depuis n’importe lequel d’entre eux (boucle locale uniquement, désactivé par défaut)
- **Continuez le travail d’un outil à l’autre** — dites *« reprends ma dernière session Codex »* dans Claude Code (ou l’inverse) et l’agent récupère un bloc de passation condensé : derniers tours, résumé de la session et modifications effectuées
- **Configuration en un clic** — lancez **Set up ccassist (MCP + Skill)** depuis la page MCP du panneau latéral ou la palette de commandes ; la commande enregistre le serveur auprès de chaque CLI et installe une compétence `ccassist` qui apprend aux agents quand et comment l’utiliser
- **Sept outils** — `search_sessions`, `list_recent_sessions`, `get_context` et `get_session` pour retrouver et charger d’anciens travaux, plus `grep_sessions` (recherche littérale dans les transcriptions, sorties d’outils comprises), `get_session_changes` (résumés par fichier ou diffs reconstruits) et `get_file_sessions` (quelles sessions ont touché un fichier) `Pro`
- **Confidentiel par conception** — tout reste sur votre machine ; le serveur n’écoute que sur localhost, et le paramètre `workspaceOnly` peut le limiter aux sessions du workspace actuel

### Analyses et suivi des coûts
- **Tableau de bord** avec statistiques d’utilisation, chronologies d’activité et tendances des coûts
- **Suivi du quota** — cartes de quota Claude/Codex en direct, graphique de consommation, historique des réinitialisations hebdomadaires et bilan hebdomadaire, avec détail par modèle, dont Sonnet, Opus et Fable lorsque disponible
- **Plusieurs comptes Claude et Codex** — enregistrez chaque compte une seule fois, changez de compte actif depuis le panneau latéral, le tableau de bord ou la palette de commandes, et consultez l’utilisation du plan de chaque compte
- **Graphiques d’utilisation par modèle** pour voir quels modèles portent votre activité et vos coûts dans le temps
- **Analyse détaillée des coûts** pour tous les modèles Claude, OpenAI, OpenCode, Grok et Copilot pris en charge, y compris l’analyse des tokens de cache
- **Analyses par session** — utilisation de la fenêtre de contexte dans le temps (son taux de remplissage, tour par tour), compactages signalés sur la chronologie, pic de contexte comparé à la limite du modèle, et tours sans succès de cache
- **Indicateur de quota dans la barre d’état**, avec accès rapide au tableau de bord

## 💎 Tarifs

Gratuit pour un usage quotidien. Quelques fonctionnalités avancées nécessitent Pro.

|   | Gratuit | Pro |
|---|---|---|
| Parcourir les sessions récentes | ✓ (7 derniers jours) | ✓ (illimité) |
| Recherche, diffs, tableau de bord | ✓ (récent) | ✓ (historique illimité) |
| Chronologie de fichier | ✓ (3 derniers jours) | ✓ (toutes les sessions) |
| Export Markdown et actions groupées | — | ✓ |
| Archivage des sessions | — | ✓ |
| Fork de sessions et conversion de format | — | ✓ |
| Serveur MCP ccassist | ✓ (7 derniers jours, outils de base) | ✓ (historique complet + outils grep/diff) |
| Appareils | 2 | 5 |

Consultez [ccassist.dev](https://ccassist.dev) pour les tarifs actuels et la politique de remboursement.

## 🔒 Confidentialité

Le contenu de vos chats reste sur votre machine : l’extension lit les dossiers d’historique locaux des assistants pris en charge et stocke tout dans une base SQLite locale. Vous pouvez le vérifier avec n’importe quel proxy réseau : aucun texte de chat, contenu de fichier ni diff n’est jamais envoyé.

Ce qui est envoyé par défaut : un identifiant d’appareil anonymisé, la version de l’OS et de l’extension, et des compteurs d’utilisation agrégés (par exemple « session ouverte », « recherche lancée »). Les rapports d’erreur contiennent les messages d’erreur et les traces d’appels, jamais le contenu des chats. Les deux peuvent être désactivés dans les paramètres de l’extension (`enableErrorReporting`, `enableUsageStatsSharing`).

## 🚀 Premiers pas

**Prérequis :** VS Code 1.80.0+ et un historique existant de Claude Code, Codex, OpenCode, Grok et/ou GitHub Copilot.

1. Installez l’extension depuis la marketplace des extensions VS Code
2. L’extension détecte automatiquement votre historique Claude, Codex, OpenCode, Grok et Copilot
3. Cliquez sur l’icône CCAssist dans la barre d’activité pour commencer

Cliquez sur une session pour voir la conversation et ses modifications de fichiers, utilisez **Modifications de fichiers** pour un résumé des diffs façon commit, et ouvrez l’onglet **Tableau de bord** pour l’analyse des coûts et du quota.

## ⌨️ Commandes et raccourcis

Ouvrez la palette de commandes (`Ctrl+Shift+P`) et cherchez **CCAssist** : actualiser les sessions, ouvrir le tableau de bord, actualiser le quota d’utilisation API, ouvrir le panneau latéral, changer de compte Claude / Codex, et plus encore.

| Raccourci | Action |
|----------|--------|
| `Ctrl+Alt+;` | Modifications récentes de fichiers (Quick Pick) |

D’autres actions (afficher le diff, appliquer les modifications, ouvrir le fichier, voir les modifications de fichiers, afficher dans la chronologie) sont disponibles via les menus contextuels (clic droit).

## ⚙️ Configuration

Accédez-y via **Paramètres → Extensions → Claude Code Assist**, ou cherchez « Claude History » dans les paramètres de VS Code. Parmi les options utiles :

- **`claude-history.claudeDirectory`** — chemin `.claude` personnalisé (détecté automatiquement si vide)
- **`claude-history.archiveDirectory`** / **`claude-history.export.directory`** — emplacement des sessions archivées et exportées
- **`claude-history.autoRefreshEnabled`** / **`autoRefreshInterval`** — actualisation automatique des sessions récentes
- **`claude-history.dateFormat`** — format ISO ou format régional de votre système
- **`claude-history.resume.defaultTargetClaude`** / **`defaultTargetCodex`** — où les sessions sont reprises par défaut
- **`claude-history.statusBar.showApiUsage`** — afficher l’indicateur de quota
- **`claude-history.mcp.enabled`** / **`mcp.port`** / **`mcp.providers`** / **`mcp.workspaceOnly`** — héberger le serveur MCP ccassist, choisir son port, sélectionner les historiques de CLI qu’il expose et, si besoin, le limiter au workspace actuel
- **`claude-history.enableErrorReporting`** / **`enableUsageStatsSharing`** — activer ou désactiver les rapports anonymes

## 🔧 Dépannage

**« Aucun répertoire Claude, Codex, OpenCode, Grok ou Copilot trouvé »** — vérifiez que l’assistant concerné a été utilisé au moins une fois et que son répertoire existe, ou définissez un chemin personnalisé dans les paramètres.

**Les sessions ne se chargent pas** — cliquez sur **Actualiser les sessions** et vérifiez les chemins de vos répertoires.

**Les diffs ne s’affichent pas correctement** — l’extension associe les fichiers par leur chemin relatif à la racine du projet ; vérifiez que le fichier existe dans votre workspace actuel.

**Performances avec un historique volumineux** — les sessions se chargent de manière incrémentale, avec mise en cache ; utilisez **Vider le cache du projet** ou reconstruisez l’index de recherche si tout ralentit.

L’extension utilise SQLite via WebAssembly : elle fonctionne donc de la même façon sous Windows, macOS (Intel et Apple Silicon) et Linux, avec un seul et même build.

## 📝 Historique des versions

Consultez [CHANGELOG.md](./CHANGELOG.md) pour les notes de version détaillées.

## 📄 Licence

Propriétaire — consultez [LICENSE](./LICENSE) pour les conditions. L’extension est gratuite, mais son code source n’est pas open source.

## Contact et support

Une question, une suggestion, ou simplement envie d’échanger ? N’hésitez pas à me contacter !

**📧 E-mail :** yash@ccassist.dev
**🐦 Twitter/X :** [@yashagl](https://x.com/yashagl)

## 🔗 Liens

- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [Dépôt GitHub](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) · [Codex](https://github.com/openai/codex) · [OpenCode CLI](https://opencode.ai/) · [Grok](https://grok.com/) · [GitHub Copilot](https://github.com/features/copilot)

---

**Boostez votre workflow avec un historique complet, le suivi des modifications de fichiers et la gestion des sessions dans Claude Code, Codex, OpenCode, Grok et GitHub Copilot.**
