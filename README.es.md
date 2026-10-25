# Claude Code and Codex Assist — Historial, diffs y analítica de uso para VS Code, Cursor y más

[English](./README.md) | [简体中文](./README.zh-CN.md) | [繁體中文](./README.zh-TW.md) | [日本語](./README.ja.md) | [한국어](./README.ko.md) | [Deutsch](./README.de.md) | [Français](./README.fr.md) | **Español**

> **Nota**: Esta es una extensión no oficial; no está creada por Anthropic, OpenAI, SST/OpenCode, xAI/Grok ni GitHub, ni tiene relación con ellos.

![Claude Code and Codex Assist en 40 segundos: historial de sesiones, reanudación, seguimiento de cuota, diffs, búsqueda y contexto entre CLI](./assets/ccassist-promo.gif)

Explora tu historial de chat de **Claude Code**, **Codex**, **OpenCode**, **Grok** y **GitHub Copilot** directamente en VS Code: consulta los diffs de archivos, busca en todas las conversaciones, controla el uso de tokens y el coste, y reanuda sesiones anteriores sin salir del editor. También sirve para seguir tu uso: un único panel muestra el coste por modelo, el consumo de cuota y el historial de reinicios semanales de todos tus asistentes de IA, y si usas más de una cuenta de Claude o Codex, cambias entre ellas con un clic. ¿Alguna vez te has preguntado qué conversación con IA cambió un archivo? La línea de tiempo de archivos es un git blame para las ediciones de IA: elige un archivo, mira cada sesión y prompt que lo tocó y abre el diff exacto.

**🤖 Funciona con los cinco asistentes:**
- **Claude Code** — `~/.claude/projects/`
- **Codex** — `~/.codex/sessions/`
- **OpenCode** — `~/.local/share/opencode/`
- **Grok** — `~/.grok/`
- **GitHub Copilot** — Copilot CLI y sesiones de chat de VS Code

Las sesiones de los cinco aparecen en una única lista, con insignias y logotipos que las distinguen. Un **servidor MCP** integrado permite incluso que los asistentes compartan contexto entre sí: continúa tu última sesión de Codex desde Claude Code o pregúntale a Grok qué cambió una sesión anterior de Claude.

**🌐 Idiomas de la interfaz:** English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Deutsch | Français | Español

## 🎬 Demos de funciones

### 🔍 Búsqueda de texto completo
Busca en todos los prompts y respuestas de miles de sesiones. Los resultados se agrupan por sesión con el mensaje coincidente, el proyecto y el coste. El panel Avanzado te permite elegir en quién buscar (todos, tú o el asistente), cómo hacer coincidir (cualquier palabra, frase exacta o regex) y si incluir la salida de herramientas y las transcripciones de subagentes.

![Búsqueda de texto completo](./assets/text-search.gif)

### ✅ Cambios de la sesión y revisión
Cada turno muestra los archivos que tocó con su recuento de +/-, diff, deshacer y volver a aplicar. Abre **Revisar cambios** para ver en un solo lugar todos los cambios de archivos de una conversación.

![Cambios de la sesión y Revisar cambios](./assets/session-changes.gif)

### ⏱️ Línea de tiempo de archivos
**git blame, pero para conversaciones con IA.** Abre cualquier archivo y la línea de tiempo muestra todas las sesiones que lo editaron; despliega una sesión para ver el prompt exacto y su diff, en Claude Code, Codex, OpenCode, Grok y Copilot.

![Línea de tiempo de archivos](./assets/timeline-demo.gif)

### 💬 Vista de conversación
Transcripción renderizada con tarjetas de **cambios del turno**, un gráfico de la ventana de contexto, la tasa de aciertos de caché y el coste. Reanuda en la terminal, en la app de escritorio o en la extensión de Codex para VS Code, o exporta a Markdown.

<img src="./assets/conversation-view.png" alt="Vista de conversación con cambios de archivos por turno y destinos para reanudar" width="420">

### 📊 Consumo de cuota y cambio de cuenta
Tarjetas de cuota en vivo de 5 horas y semanales para Claude, Codex, Fable y Grok, gráficos de consumo que proyectan cuándo se agotará cada ventana, un mapa de calor de actividad y una tabla de costes día a día. Guarda varias cuentas de Claude y Codex y cambia entre ellas desde la pestaña Cuenta, la pestaña Plan del panel o el comando **Cambiar cuenta de Claude / Codex**; el uso del plan de cada cuenta se registra por separado, así que el historial de cuota nunca mezcla cuentas.

<img src="./assets/account-quota.png" alt="Pestaña Cuenta con tarjetas de cuota, gráfico de consumo y mapa de calor de actividad" width="420">

### 📅 Resumen semanal
Un resumen móvil de 7 días con sesiones, tokens, coste, ediciones y días activos frente a la semana anterior, desglosado por herramienta y por proyecto.

<img src="./assets/weekly-digest.png" alt="Resumen semanal con totales, tokens por día y proyectos principales" width="420">

### 📚 Explorador de sesiones unificado
Sesiones de Claude Code, Codex, Grok, OpenCode, Copilot y Cursor en una sola lista, agrupadas por proyecto, con filtros por modelo y el coste de cada carpeta.

<img src="./assets/chat-history.png" alt="Pestaña Sesiones agrupada por proyecto con el filtro de modelos abierto" width="420">

### 🔌 Servidor MCP de ccassist
Un servidor MCP local permite que Claude Code, Codex, Grok, OpenCode y Cursor lean tu historial de sesiones y continúen el trabajo de los demás.

<img src="./assets/history-mcp.png" alt="Pestaña MCP con las herramientas de ccassist disponibles para los agentes de CLI" width="420">

### 📍 Cuota en la barra de estado
Los porcentajes de Claude, Fable, Codex y Grok siempre a la vista; pasa el cursor por encima para ver cada ventana con su hora de reinicio.

<img src="./assets/usage-quota-statusbar.png" alt="Indicador de cuota en la barra de estado con ventana emergente" width="555">


## 🌟 Funciones

### Sesiones e historial
- **Historial unificado** de Claude Code, Codex, OpenCode, Grok y GitHub Copilot, organizado por proyecto y con detección del proyecto actual
- **Acciones rápidas y navegación con teclado**: fija, reanuda o elimina desde la fila de una sesión; muévete con las flechas, abre con Intro y elimina con Supr
- **Menú contextual del proyecto**: haz clic derecho en la cabecera de un proyecto para fijarlo, ocultarlo, mostrarlo en el gestor de archivos o abrirlo en una ventana nueva
- **Oculta sesiones concretas**: despeja la lista sin borrar nada; las sesiones ocultas se reúnen en la pestaña Ocultas, agrupadas por proyecto, y puedes volver a mostrarlas con un clic u ocultar varias a la vez con la selección múltiple
- **Renderizado completo de transcripciones**: Markdown con código resaltado, diagramas Mermaid con zoom y exportación, y fórmulas LaTeX compuestas sin conexión con KaTeX (al copiar una fórmula renderizada obtienes de nuevo el código TeX)
- **Filtro de búsqueda en vivo** para acotar la lista mientras escribes
- **Filtros por modelo, proyectos fijados, y fijar y renombrar** ayudan a mantener ordenados y fáciles de recorrer los historiales grandes
- **Reanuda** cualquier conversación en la terminal, la app de escritorio o VS Code, o copia el comando para ejecutarlo en otro sitio
- **Bifurca** una conversación desde cualquier mensaje para explorar una alternativa sin tocar la original `Pro`
- **Conversor de formato** entre Claude y Codex, que reanuda directamente en el asistente de destino `Pro`
- **Actualización automática** que mantiene al día las sesiones recientes mientras siguen cambiando
- **Lista de historial más limpia**, con un estilo visual más minimalista que facilita recorrer listas largas de sesiones

### Archivo y sincronización Markdown
- **Archivo de sesiones**: Claude y Codex acaban borrando las transcripciones antiguas; archivar guarda una copia completa a salvo en su propia carpeta, que puedes explorar desde una pestaña **Archivadas** dedicada. Ver y restaurar sesiones archivadas siempre es gratis. Archivar requiere `Pro`
- **Exportación a Markdown** de sesiones completas con metadatos personalizables `Pro`
- **Sincronización Markdown**: las sesiones exportadas se pueden subir a git, llevar a otros dispositivos, volver a importar con los cambios de archivos intactos o reanudar como sesión nativa (incluso entre sistemas operativos distintos)
- **Acciones en bloque**: selecciona varias sesiones para exportarlas o eliminarlas a la vez `Pro`

### Cambios de archivos y diffs
- **Diffs estilo GitHub** con resaltado de sintaxis y soporte para varios archivos
- **Vista Revisar cambios**: todos los cambios de archivos de una conversación en un solo lugar
- **Aplica, deshaz o vuelve a aplicar** cambios en tu espacio de trabajo con un clic
- **Línea de tiempo de archivos**: git blame para conversaciones con IA. La línea de tiempo sigue automáticamente el editor activo y lista todas las sesiones que editaron el archivo; entra en cualquiera para leer el prompt exacto y abrir su diff (o haz clic derecho en un archivo para abrir la línea de tiempo)

### Búsqueda
- **Búsqueda directa en archivos**: cada búsqueda analiza directamente tus archivos de sesión; no se copia nada a un índice aparte, y los resultados indican cuántos archivos se analizaron
- **Panel Avanzado**: un clic junto a la barra de búsqueda abre las opciones; busca en todos, solo en tus prompts o solo en las respuestas del asistente, y haz coincidir cualquier palabra, una frase exacta o una expresión regular
- **Búsqueda en salida de herramientas y subagentes**: incluye las entradas y resultados de herramientas y las transcripciones de subagentes para encontrar detalles que nunca aparecen en los mensajes principales del chat
- **Resultados agrupados por sesión** con coste, tokens y número de mensajes, y las coincidencias resaltadas

### Servidor MCP de ccassist: contexto compartido entre asistentes
- **Servidor MCP local**: la extensión puede alojar un servidor MCP local y ligero para que Claude Code, Codex, Grok, OpenCode y Cursor consulten tu historial de sesiones desde cualquiera de ellos (solo loopback, desactivado por defecto)
- **Continúa el trabajo entre herramientas**: di *«continúa mi última sesión de Codex»* en Claude Code (o al revés) y el agente obtiene un resumen de traspaso condensado: los últimos turnos, un resumen de la sesión y lo que cambió
- **Configuración en un clic**: ejecuta **Set up ccassist (MCP + Skill)** desde la página MCP del panel lateral o la paleta de comandos; registra el servidor en cada CLI e instala una skill `ccassist` que enseña a los agentes cuándo y cómo usarlo
- **Siete herramientas**: `search_sessions`, `list_recent_sessions`, `get_context` y `get_session` para encontrar y cargar trabajo anterior, además de `grep_sessions` (búsqueda literal en transcripciones, incluida la salida de herramientas), `get_session_changes` (resúmenes por archivo o diffs reconstruidos) y `get_file_sessions` (qué sesiones tocaron un archivo) `Pro`
- **Privado por diseño**: todo se queda en tu equipo; el servidor solo escucha en localhost, y el ajuste `workspaceOnly` puede limitarlo a las sesiones del espacio de trabajo actual

### Analítica y seguimiento de costes
- **Panel** con estadísticas de uso, líneas de tiempo de actividad y tendencias de coste
- **Seguimiento de cuota**: tarjetas de cuota de Claude/Codex en vivo, gráfico de consumo, historial de reinicios semanales y resumen semanal, con desglose por modelo, incluidos Sonnet, Opus y Fable cuando están disponibles
- **Varias cuentas de Claude y Codex**: guarda cada cuenta una vez, cambia la cuenta activa desde el panel lateral, el panel de analítica o la paleta de comandos, y consulta el uso del plan de cada cuenta
- **Gráficos de uso por modelo** que muestran qué modelos impulsan tu actividad y tu coste a lo largo del tiempo
- **Análisis de costes detallado** de todos los modelos compatibles de Claude, OpenAI, OpenCode, Grok y Copilot, con datos sobre los tokens de caché
- **Analítica por sesión**: uso de la ventana de contexto a lo largo del tiempo (cuánto se llenó, turno a turno), eventos de compactación marcados en la línea de tiempo, pico de contexto frente al límite del modelo y turnos sin acierto de caché
- **Indicador de cuota en la barra de estado** con acceso rápido al panel

## 💎 Precios

Gratis para el uso diario. Algunas funciones avanzadas requieren Pro.

|   | Gratis | Pro |
|---|---|---|
| Explorar sesiones recientes | ✓ (últimos 7 días) | ✓ (ilimitado) |
| Búsqueda, diffs, panel | ✓ (recientes) | ✓ (historial ilimitado) |
| Línea de tiempo de archivos | ✓ (últimos 3 días) | ✓ (todas las sesiones) |
| Exportación a Markdown y acciones en bloque | — | ✓ |
| Archivo de sesiones | — | ✓ |
| Bifurcación de sesiones y conversión de formato | — | ✓ |
| Servidor MCP de ccassist | ✓ (últimos 7 días, herramientas básicas) | ✓ (historial completo + herramientas grep/diff) |
| Dispositivos | 2 | 5 |

Consulta [ccassist.dev](https://ccassist.dev) para ver los precios actuales y la política de reembolso.

## 🔒 Privacidad

El contenido de tus chats no sale de tu equipo: la extensión lee las carpetas de historial locales de los asistentes compatibles y lo guarda todo en una base de datos SQLite local. Puedes comprobarlo con cualquier proxy de red: nunca se envía texto de chats, contenido de archivos ni diffs.

Lo que se envía por defecto: un ID de dispositivo anonimizado, la versión del sistema operativo y de la extensión, y contadores de uso agregados (p. ej., «sesión abierta», «búsqueda ejecutada»). Los informes de errores incluyen mensajes de error y trazas de pila, nunca contenido de chats. Ambos se pueden desactivar en los ajustes de la extensión (`enableErrorReporting`, `enableUsageStatsSharing`).

## 🚀 Primeros pasos

**Requisitos previos:** VS Code 1.80.0+ y un historial existente de Claude Code, Codex, OpenCode, Grok o GitHub Copilot.

1. Instala la extensión desde el marketplace de extensiones de VS Code
2. La extensión detecta automáticamente tu historial de Claude, Codex, OpenCode, Grok y Copilot
3. Haz clic en el icono de CCAssist en la barra de actividad para empezar a explorar

Haz clic en cualquier sesión para ver la conversación y sus cambios de archivos, usa **Cambios de archivos** para ver un resumen de diffs al estilo de un commit y abre la pestaña **Panel** para consultar la analítica de costes y cuota.

## ⌨️ Comandos y atajos

Abre la paleta de comandos (`Ctrl+Shift+P`) y busca **CCAssist**: actualizar sesiones, abrir el panel de analítica, actualizar la cuota de uso de API, abrir el panel lateral, cambiar de cuenta de Claude / Codex, y más.

| Atajo | Acción |
|----------|--------|
| `Ctrl+Alt+;` | Cambios recientes de archivos (Quick Pick) |

Las demás acciones (mostrar diff, aplicar cambios, abrir archivo, ver cambios de archivos, mostrar en la línea de tiempo) están disponibles en los menús contextuales del clic derecho.

## ⚙️ Configuración

Accede desde **Ajustes → Extensiones → Claude Code Assist** o busca «Claude History» en los ajustes de VS Code. Algunas opciones útiles:

- **`claude-history.claudeDirectory`**: ruta personalizada de `.claude` (se detecta automáticamente si se deja vacía)
- **`claude-history.archiveDirectory`** / **`claude-history.export.directory`**: dónde se guardan las sesiones archivadas y exportadas
- **`claude-history.autoRefreshEnabled`** / **`autoRefreshInterval`**: actualización automática de las sesiones recientes
- **`claude-history.dateFormat`**: formato ISO o el formato regional de tu sistema
- **`claude-history.resume.defaultTargetClaude`** / **`defaultTargetCodex`**: dónde se reanudan las sesiones por defecto
- **`claude-history.statusBar.showApiUsage`**: muestra el indicador de cuota
- **`claude-history.mcp.enabled`** / **`mcp.port`** / **`mcp.providers`** / **`mcp.workspaceOnly`**: aloja el servidor MCP de ccassist, elige su puerto, decide qué historiales de CLI expone y, si quieres, limítalo al espacio de trabajo actual
- **`claude-history.enableErrorReporting`** / **`enableUsageStatsSharing`**: activa o desactiva los informes anónimos

## 🔧 Solución de problemas

**«No Claude, Codex, OpenCode, Grok, or Copilot directory found»**: asegúrate de haber usado el asistente correspondiente al menos una vez y de que el directorio exista, o define una ruta personalizada en los ajustes.

**Las sesiones no cargan**: haz clic en **Actualizar sesiones** y comprueba las rutas de los directorios.

**Los diffs no se muestran bien**: la extensión localiza los archivos por su ruta relativa a la raíz del proyecto; asegúrate de que el archivo existe en tu espacio de trabajo actual.

**Rendimiento con historiales grandes**: las sesiones se cargan de forma incremental y con caché; si todo va lento, usa **Limpiar caché del proyecto** o reconstruye el índice de búsqueda.

La extensión usa SQLite mediante WebAssembly, así que funciona igual en Windows, macOS (Intel y Apple Silicon) y Linux con una única compilación.

## 📝 Historial de versiones

Consulta [CHANGELOG.md](./CHANGELOG.md) para ver las notas de versión detalladas.

## 📄 Licencia

Propietaria: consulta [LICENSE](./LICENSE) para ver las condiciones. La extensión es de uso gratuito, pero su código fuente no es de código abierto.

## Contacto y soporte

¿Preguntas, sugerencias o simplemente quieres saludar? ¡Escríbeme!

**📧 Correo:** yash@ccassist.dev
**🐦 Twitter/X:** [@yashagl](https://x.com/yashagl)

## 🔗 Enlaces

- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=agsoft.claude-history-viewer)
- [Repositorio de GitHub](https://github.com/yashagldit/Claude-Code-History-VSCode)
- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) · [Codex](https://github.com/openai/codex) · [OpenCode CLI](https://opencode.ai/) · [Grok](https://grok.com/) · [GitHub Copilot](https://github.com/features/copilot)

---

**Mejora tu flujo de trabajo con un historial completo, seguimiento de cambios en archivos y gestión de sesiones en Claude Code, Codex, OpenCode, Grok y GitHub Copilot.**
