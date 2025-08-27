# Changelog

All notable changes to the Claude Code Assist extension will be documented in this file.

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