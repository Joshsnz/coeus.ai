# Coeus AI — Project-Aware AI Desktop Workspace

**Coeus AI** is a native C++ desktop AI workspace for working with software projects. It combines a custom Skia/SDL2 graphical interface, project-aware AI assistance, retrieval over local codebases, tool execution, workflow orchestration, structured telemetry, and a private headless evaluation harness used to test repository-grounded behavior.

This public repository is a **portfolio/demo release**. The full source code remains private, but this package provides a compiled Windows GUI demo build, usage documentation, architecture notes, technical case-study material, screenshots/video placeholders, and benchmark reports generated from a private headless test harness.

---

## Contents

- [What This Is](#what-this-is)
- [Why It Matters](#why-it-matters)
- [Quick Review Path](#quick-review-path)
- [Repository Contents](#repository-contents)
- [Running the Demo](#running-the-demo)
- [Demo Walkthrough](#demo-walkthrough)
- [Key Features](#key-features)
- [RepoGrounding Evaluation Reports](#repogrounding-evaluation-reports)
- [Architecture Overview](#architecture-overview)
- [Technical Highlights](#technical-highlights)
- [Task and Workflow Orchestration](#task-and-workflow-orchestration)
- [Retrieval and Context System](#retrieval-and-context-system)
- [Telemetry and Evaluation](#telemetry-and-evaluation)
- [Technology Stack](#technology-stack)
- [Documentation Map](#documentation-map)
- [Current Status](#current-status)
- [Public Release Scope](#public-release-scope)
- [Known Limitations](#known-limitations)
- [Portfolio Summary](#portfolio-summary)

---

## What This Is

Coeus AI is a local-first AI development workspace built around the idea that an assistant should understand the **currently loaded project**, not just answer as a generic chatbot.

The application is designed to let a user:

- open or work against a local software project,
- ask questions about source files,
- inspect project context,
- request architecture and runtime-flow explanations,
- compare source files semantically,
- ask whether features are actually implemented,
- maintain project context across follow-up turns,
- and interact through a native desktop interface rather than a browser chat window.

The public package demonstrates the product direction and engineering work without exposing the private source code.

---

## Why It Matters

A common failure mode in AI coding assistants is that they sound confident while losing repository context, hallucinating unsupported features, or routing normal codebase questions into the wrong workflow.

Coeus AI explores a more structured approach:

- separate local project inventory from source evidence,
- assemble context from project files,
- route different user intents differently,
- distinguish semantic repository QA from patch/diff requests,
- retain repository context across follow-up turns,
- suppress internal trace/vector/project-storage details from user-facing answers,
- and validate these behaviors through automated headless benchmark scenarios.

The included **RepoGrounding** benchmark reports show this behavior being tested on repository-context tasks such as startup tracing, source-order tracing, semantic comparison, negative grounding, multi-turn continuity, and artifact suppression.

---

## Quick Review Path

For reviewers, the fastest path through the project is:

1. Read this README for the overall summary.
2. Open the portfolio case study:
   - [`docs/PORTFOLIO_CASE_STUDY.md`](docs/PORTFOLIO_CASE_STUDY.md)
3. Review the architecture overview:
   - [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md)
4. Run or inspect the GUI demo:
   - [`bin/CoeusAI.exe`](bin/CoeusAI.exe)
   - [`docs/DEMO_GUIDE.md`](docs/DEMO_GUIDE.md)
5. Review the evaluation evidence:
   - [`docs/evals/README.md`](docs/evals/README.md)
   - [`docs/evals/repo_grounding_core/index.html`](docs/evals/repo_grounding_core/index.html)
   - [`docs/evals/repo_grounding_plus/index.html`](docs/evals/repo_grounding_plus/index.html)
6. Review the planned video walkthrough:
   - [`docs/VIDEO_WALKTHROUGH_SCRIPT.md`](docs/VIDEO_WALKTHROUGH_SCRIPT.md)
7. Check limitations and release scope:
   - [`docs/KNOWN_LIMITATIONS.md`](docs/KNOWN_LIMITATIONS.md)
   - [`docs/SECURITY_AND_PRIVACY.md`](docs/SECURITY_AND_PRIVACY.md)
   - [`docs/PROJECT_STATUS.md`](docs/PROJECT_STATUS.md)

---

## Repository Contents

This repository is structured as a documentation and binary demo package.

```text
.
├── bin/
│   └── CoeusAI.exe
├── docs/
│   ├── evals/
│   │   ├── README.md
│   │   ├── repo_grounding_core/
│   │   │   ├── README.md
│   │   │   ├── index.html
│   │   │   └── scorecard.svg
│   │   └── repo_grounding_plus/
│   │       ├── README.md
│   │       ├── index.html
│   │       └── scorecard.svg
│   ├── ARCHITECTURE.md
│   ├── BUILD_WINDOWS.md
│   ├── DEMO_GUIDE.md
│   ├── DEPENDENCIES.md
│   ├── FAQ.md
│   ├── KNOWN_LIMITATIONS.md
│   ├── PORTFOLIO_CASE_STUDY.md
│   ├── PORTFOLIO_SUMMARY_SHORT.md
│   ├── PROJECT_STATUS.md
│   ├── RELEASE_NOTES.md
│   ├── SCREENSHOTS.md
│   ├── SECURITY_AND_PRIVACY.md
│   ├── TROUBLESHOOTING.md
│   └── VIDEO_WALKTHROUGH_SCRIPT.md
└── README.md
