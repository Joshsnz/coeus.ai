# Coeus AI — Portfolio Case Study

## Project Summary

**Coeus AI** is a native C++ desktop workspace for project-aware AI assistance. It combines a custom Skia/SDL2 interface, local project indexing, retrieval over codebases, tool execution, and structured telemetry.

The goal was to build a serious desktop AI environment that goes beyond a generic chatbot. Coeus AI is designed to understand the user’s active project context, retrieve relevant files, surface supporting evidence, and provide AI assistance in a way that is inspectable and useful for software development workflows.

**Public Release Type:** GUI binary/demo portfolio package  
**Executable:** `CoeusAI.exe`  
**Source Code:** Private  
**Public Headless Mode:** Not included

---

## Problem

Most AI coding interfaces are either web-chat style tools or editor-bound assistants. They often hide context assembly, lack clear evidence surfaces, and can be difficult to evaluate outside the UI.

Coeus AI was built to explore a more robust pattern:

- A local-first native desktop application
- Project-aware retrieval over a real file inventory
- Evidence-aware answer generation
- Tool execution for project operations
- Structured telemetry to make AI behavior inspectable
- A core runtime architecture that can be exercised by private/internal non-GUI builds for testing

---

## What the Public Demo Does

The public demo package provides the GUI desktop executable:

```text
CoeusAI.exe
```

The demo is intended to show the application as a native project-aware AI workspace.

Core user-facing capabilities include:

- Working with a local software project
- Building project inventory and context
- Asking file-specific questions
- Asking architecture-level project questions
- Comparing files or components
- Inspecting evidence and context used by the assistant
- Executing built-in project tools
- Viewing structured telemetry and debugging surfaces

---

## Private/Internal Headless Build

The private development version includes a separate headless build path used for testing, automation, and evaluation.

That headless build is useful for:

- Regression testing
- Automated runtime checks
- Evaluating project-aware behavior without the GUI
- Debugging turn-level behavior in a deterministic environment

The public portfolio package does **not** include the headless executable. It is referenced only as part of the private engineering architecture and testing strategy.

---

## Key Features

### Native Desktop Application

Coeus AI uses a native C++ GUI stack rather than a web frontend.

Key elements include:

- Skia rendering
- SDL2/OpenGL windowing
- Custom UI framework
- Conversation view
- Sidebar and panel system
- Context/evidence display
- Settings and tool panels
- Telemetry/debugging UI

### Project-Aware AI Workflow

The assistant is designed to operate against a project rather than only the current chat message.

It can use:

- File inventory
- Search results
- Retrieved source excerpts
- Summaries and gists
- Recent interaction state
- Tool outputs
- Structured runtime metadata

### Retrieval and Context Assembly

The system includes a retrieval layer that can search and rank project information before the assistant answers.

The user-facing goal is simple: when the assistant answers a project question, it should have access to relevant supporting material.

### Tool Execution

Coeus AI includes built-in tools for project and file-context operations, such as:

- Project inventory operations
- Search and retrieval tools
- File-context tooling
- Planning/apply workflow support
- Artifact and telemetry tooling

### Structured Telemetry

Coeus AI includes detailed runtime telemetry, such as:

- Turn traces
- Activity feed
- Run artifacts
- Debug markers
- Build and evaluation diagnostics

This makes the application easier to inspect and debug than a conventional opaque AI chat interface.

---

## Technical Highlights

- Large native C++20 application architecture
- Custom UI stack using Skia and SDL2
- Project-aware retrieval pipeline
- Runtime separation that supports GUI operation and private/internal headless testing
- Structured telemetry and trace export
- Tool execution architecture
- Native dependency management with CMake, MSVC, Skia, SDL2, FAISS, SQLite, OpenSSL, libcurl, and tree-sitter
- Practical Windows build hardening for large C++ projects

---

## Engineering Challenges

The project required solving several difficult engineering problems:

- Keeping UI logic separate from runtime logic
- Making project context retrievable and usable by an AI assistant
- Supporting large native dependency builds on Windows
- Handling compiler instability and translation-unit level build issues
- Maintaining structured telemetry without overwhelming the user
- Designing the application so it can be demonstrated without exposing private source code

---

## Outcome

The current demo release shows a working native C++ AI workspace with:

- Compiled Windows GUI executable
- Custom desktop interface
- Project-aware assistant workflow
- Retrieval/context system
- Tool and telemetry surfaces
- Professional documentation package

The private source version continues to evolve, but this public package is suitable as a portfolio demonstration of native C++ application design, AI tooling architecture, and complex system integration.
