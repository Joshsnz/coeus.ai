# Coeus AI — Project-Aware AI Desktop Workspace

**Coeus AI** is a native C++ desktop AI workspace that combines a custom Skia/SDL2 graphical interface, project-aware AI assistance, retrieval over local codebases, tool execution, structured telemetry, and a shared GUI/headless runtime design.

This public repository is intended as a **portfolio/demo release**. The full source code is private, but this repository provides a compiled demo build, usage notes, architecture documentation, and a technical case study.

---

## Overview

Coeus AI was built as a local-first AI development environment for working with software projects. It is designed to let a user load or work against a project, ask targeted questions about the codebase, inspect contextual evidence, and interact with an AI assistant through a desktop interface rather than a web chat.

The project demonstrates:

- Native C++ application development
- Custom GUI architecture with Skia and SDL2
- Project-aware AI assistant workflows
- Retrieval and context assembly over local files
- Tool execution and project operations
- Structured telemetry and debugging infrastructure
- Shared GUI/headless runtime design for testing and automation

---

## Demo Repository Contents

This repository is structured as a documentation and binary demo package.

```text
.
├── bin/
│   └── AgentGui_skia.exe
├── docs/
│   ├── ARCHITECTURE.md
│   ├── BUILD_WINDOWS.md
│   ├── DEMO_GUIDE.md
│   ├── PORTFOLIO_CASE_STUDY.md
│   ├── DEPENDENCIES.md
│   ├── TROUBLESHOOTING.md
│   ├── RELEASE_NOTES.md
│   ├── ROADMAP.md
│   ├── SECURITY_AND_PRIVACY.md
│   ├── FAQ.md
│   ├── KNOWN_LIMITATIONS.md
│   ├── SCREENSHOTS.md
│   ├── VIDEO_WALKTHROUGH_SCRIPT.md
│   └── PORTFOLIO_SUMMARY_SHORT.md
└── README.md
```

Depending on the release package, additional runtime DLLs or support files may also be present in `bin/`.

> Note: the current executable may still be named `AgentGui_skia.exe` because that was the internal/native build target name. The public-facing project name is **Coeus AI**.

---

## Key Features

### Project-Aware AI Assistance

- Ask questions about a loaded software project
- Inspect file-level and project-level context
- Support for targeted file understanding
- Support for broader architecture questions
- Support for recent-change and comparison-style questions
- Uses local project context rather than acting as a generic chatbot

### Native Desktop Interface

- Custom C++ desktop GUI
- Skia-based rendering pipeline
- SDL2/OpenGL windowing backend
- Conversation view
- Context/evidence panels
- Settings and tool panels
- Telemetry/debugging surfaces

### Retrieval and Context System

- Project file inventory
- Local file-context indexing
- Search and retrieval over code/project files
- Summary and gist support
- Memory/snapshot support for continuity

### Tool and Runtime Layer

- Built-in project tools
- File-context operations
- Search and retrieval tooling
- Planning/apply workflow support
- Shared runtime usable by GUI and headless modes

### Telemetry and Debugging

- Per-turn trace data
- Activity feed
- Run artifacts
- Debug markers
- Build and evaluation diagnostics

---

## Technology Stack

- **Language**: C++20
- **GUI**: Skia, SDL2, OpenGL
- **Build**: MSVC, CMake, Windows batch build scripts
- **Data/Storage**: SQLite, JSON/JSONL, filesystem artifacts
- **Retrieval/Search**: BM25-style retrieval, vector memory support, FAISS integration
- **Networking/LLM Integration**: libcurl, OpenSSL, provider/runnable abstraction
- **Parsing/Indexing**: tree-sitter integration
- **Telemetry**: structured traces, run logs, activity feed

---

## Running the Demo

1. Clone or download the repository.
2. Open the `bin/` folder.
3. Run:

```powershell
.\bin\AgentGui_skia.exe
```

If the application requires DLLs, keep the included DLL files in the same directory as the executable.

For a guided walkthrough, see:

```text
docs/DEMO_GUIDE.md
```

---

## Build Notes

The full source build is not included in this public demo repository. The original application is built privately using:

- Visual Studio 2022 Build Tools
- MSVC x64
- CMake
- Skia
- SDL2
- vcpkg-managed native dependencies

For a high-level overview of the build environment, see:

```text
docs/BUILD_WINDOWS.md
```

---

## Architecture

The application is built around a separation between:

- UI/rendering layer
- agent runtime
- project context system
- retrieval/search system
- tool execution layer
- telemetry/export layer
- optional headless runtime

For more detail, see:

```text
docs/ARCHITECTURE.md
```

---

## Portfolio Case Study

A narrative project writeup is available here:

```text
docs/PORTFOLIO_CASE_STUDY.md
```

This explains the project goals, features, technical highlights, and engineering outcomes without exposing private source code or proprietary implementation details.

---

## Current Status

- GUI build compiles successfully
- CMake build path established
- Native executable demo available
- Documentation package prepared
- Source code remains private

---

## Notes

This repository is provided for demonstration and portfolio purposes. Some internal implementation details, source code, prompts, and proprietary runtime architecture are intentionally excluded from the public release.
