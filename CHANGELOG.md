# Changelog

All notable changes to the Claude Code Assist extension will be documented in this file.

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