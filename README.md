# Coeus AI — Project-Aware AI Desktop Workspace

**Coeus AI** is a native C++ desktop AI workspace for working with software projects. It combines a custom Skia/SDL2 graphical interface, project-aware AI assistance, retrieval over local codebases, tool execution, structured telemetry, and a private headless evaluation path used to test repository-grounded behavior.

This public repository is a **portfolio/demo release**. The full source code remains private, but this package provides a compiled Windows GUI demo build, architecture documentation, usage notes, evaluation reports, and a technical case study.

---

## Overview

Coeus AI was built as a local-first AI development environment for working with software projects.

Instead of treating the assistant as a generic chatbot, the application is designed around **project context**:

- load or work against a local project,
- inspect file-level and project-level context,
- ask targeted questions about the codebase,
- compare source files semantically,
- reason about absent or unsupported features,
- maintain continuity across follow-up questions,
- and avoid exposing internal trace or retrieval machinery in user-facing answers.

The project demonstrates both application engineering and evaluation engineering. In addition to the native GUI, the private development environment includes a headless runtime used to automate repository-grounding tests. Public benchmark reports from that private evaluation path are included in this portfolio package.

> **Public demo note:** this release includes the **GUI desktop build only**. The private source code and private headless test executable are not included. Evaluation reports generated from the private headless harness are included as portfolio evidence.

---

## Why This Project Matters

Many AI coding tools can produce plausible answers, but they often lose repository context, hallucinate unsupported features, or route ordinary codebase questions into the wrong mode.

Coeus AI was built to explore a more structured approach:

- separate project inventory from source evidence,
- retrieve relevant project context,
- maintain turn state across follow-ups,
- route semantic questions differently from patch/diff requests,
- use telemetry to debug model/runtime behavior,
- and test those behaviors with repeatable benchmark scenarios.

The included RepoGrounding evaluation reports show this system being tested on repository-context tasks such as startup-flow tracing, movement/data-flow tracing, semantic comparison, negative grounding, multi-turn continuity, and internal artifact suppression.

---

## Demo Repository Contents

This repository is structured as a documentation and binary demo package.

```text
.
├── bin/
│   └── CoeusAI.exe
├── docs/
│   ├── evals/
│   │   ├── repo_grounding_core/
│   │   │   ├── index.html
│   │   │   └── scorecard.svg
│   │   ├── repo_grounding_plus/
│   │   │   ├── index.html
│   │   │   └── scorecard.svg
│   │   └── README.md
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
