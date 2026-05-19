# Coeus AI Architecture

## Overview

Coeus AI is structured as a native desktop AI workspace with a modular runtime core. The application is organized around a separation between the UI, project context systems, retrieval, tool execution, model/provider integration, and telemetry.

The public demo repository does not include private source code. This document explains the architecture at a professional overview level.

> **Important:** the public release contains the GUI desktop build only. A separate headless build exists in the private development environment for testing and automation, but it is not included in this package.

---

## High-Level Architecture

```text
Coeus AI
├── Native GUI Layer
│   ├── Skia rendering
│   ├── SDL2/OpenGL backend
│   ├── Panels, conversation UI, settings, evidence display
│   └── User input and interaction surfaces
│
├── Agent Runtime Layer
│   ├── Turn processing
│   ├── Runtime orchestration
│   ├── Request construction
│   ├── Output handling
│   └── GUI bridge
│
├── Project Context Layer
│   ├── Project inventory
│   ├── File context management
│   ├── Searchable code/file records
│   ├── Summaries and gists
│   └── Memory/snapshot support
│
├── Retrieval Layer
│   ├── Keyword-style search
│   ├── Vector memory support
│   ├── Ranked candidate selection
│   └── Context assembly
│
├── Tool Layer
│   ├── Built-in project tools
│   ├── File-context tools
│   ├── Search/retrieval tools
│   ├── Planning/apply workflows
│   └── Tool observation records
│
├── LLM / Provider Layer
│   ├── Provider management
│   ├── HTTP JSON runner
│   ├── Local process runner
│   └── Request/response abstraction
│
└── Telemetry Layer
    ├── Run traces
    ├── Activity feed
    ├── Structured markers
    ├── Artifact export
    └── Debugging surfaces
```

---

## Native GUI Layer

The GUI is a custom native desktop interface built in C++.

Primary responsibilities:

- Render the application shell
- Display conversation history
- Display project/context/evidence panels
- Present settings and tool panels
- Handle user input
- Bridge user actions into the runtime layer

Technology used:

- Skia
- SDL2
- OpenGL
- Custom C++ UI components

---

## Agent Runtime Layer

The runtime layer coordinates each assistant interaction.

At a high level, it handles:

- Receiving user input
- Building a structured request
- Consulting project state and retrieval systems
- Calling model/provider layers
- Processing model output
- Updating state and telemetry
- Returning output to the GUI

The private development architecture also supports a separate non-GUI/headless build for automated testing and evaluation. That build is not part of the public release.

---

## Project Context Layer

The project context layer is responsible for making a local project understandable to the assistant.

It manages:

- Project metadata
- File inventory
- File context records
- Summaries
- Gists
- Memory snapshots
- Context available for retrieval and prompt construction

This allows Coeus AI to answer questions based on project files rather than generic model knowledge alone.

---

## Retrieval Layer

The retrieval layer helps locate relevant project information before an assistant response is generated.

It includes support for:

- Search over local project files
- Ranked retrieval
- Vector memory integration
- Candidate selection
- Context assembly for answering

The user-facing goal is simple: when the assistant answers a project question, it should have access to relevant supporting material.

---

## Tool Layer

Coeus AI includes a tool system for project operations and internal workflows.

Example tool categories:

- Project inventory tools
- Search tools
- Retrieval tools
- File-context tools
- Planning/apply workflow tools
- Artifact and telemetry tools

Tool output can be surfaced to the user and recorded for debugging.

---

## LLM / Provider Layer

The provider layer abstracts model access. It supports remote and local-style execution paths through a provider management system.

Responsibilities include:

- Managing provider configuration
- Preparing requests
- Handling HTTP-based model calls
- Supporting local process runners
- Returning structured responses to the runtime

---

## Telemetry Layer

Telemetry is a central part of the architecture.

It supports:

- Activity feed
- Run trace records
- Structured markers
- Exported artifacts
- Debugging and evaluation diagnostics

This makes the system inspectable and helps explain why a given answer or action occurred.

---

## GUI Build vs Private Headless Build

The public release includes:

```powershell
.\bin\CoeusAI.exe
```

That is the GUI desktop build.

The private development environment also has a separate headless build path used for:

- Automated evaluation
- Regression testing
- Runtime debugging
- Non-GUI workflow checks

This distinction matters because public users should not expect a headless executable or CLI workflow in this portfolio package.

---

## Source Availability

The public repository is a portfolio/demo release. It intentionally excludes:

- Full source code
- Private prompts
- Proprietary runtime internals
- API keys
- Private evaluation datasets
- Internal development scripts
- Private headless executable
