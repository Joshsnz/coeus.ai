# Coeus AI — Project-Aware AI Desktop Workspace

**Coeus AI** is a native C++ desktop AI workspace for working with software projects. It combines a custom Skia/SDL2 graphical interface, local project awareness, retrieval over codebases, tool/workflow execution, structured telemetry, and a private headless evaluation harness used to test repository-grounded behaviour.

This public repository is a **portfolio/demo release**. The full source code remains private, but this package provides documentation, architecture notes, demo guidance, public evaluation reports, release material, and links to the compiled Windows GUI demo.

## What this is

Coeus AI was built around the idea that an assistant should understand the **currently loaded project**, not just answer as a generic chatbot.

The application is designed to:

- work against a local software project,
- inspect project context,
- retrieve relevant source files,
- answer repository-aware engineering questions,
- compare source files semantically,
- identify absent features without hallucinating implementation,
- preserve context across follow-up turns,
- and present all of this through a native desktop interface.

## Why it matters

A common failure mode in AI coding tools is that they sound confident while losing repository context, hallucinating unsupported features, or routing normal source questions into the wrong workflow.

Coeus AI explores a more structured approach:

- separate local project inventory from source evidence,
- assemble answer context from actual project files,
- route different user intents through different workflows,
- distinguish semantic repository questions from patch/diff requests,
- retain repository context across follow-up turns,
- suppress internal trace/vector/project-storage artifacts from user-facing answers,
- and validate repository-grounding behaviour through automated headless benchmark scenarios.

## Architecture summary

Coeus AI uses a policy-first, compiled-turn architecture. User input is normalized into canonical turn state before retrieval, prompt assembly, validation, telemetry export, and final response handling. This reduces drift between what the user asked, what context was packed, and what the assistant is allowed to claim.

At a high level, the system separates:

- native GUI surfaces,
- project state and file inventory,
- turn policy and routing,
- retrieval/source evidence,
- context assembly,
- model/provider transport,
- command/tool execution,
- output validation and post-processing,
- structured telemetry,
- and private headless evaluation.

## Public demo

The compiled Windows GUI demo is distributed through **GitHub Releases**, not committed directly into the repository.

Download the latest release from:

```text
https://github.com/Joshsnz/coeus.ai/releases/latest
```

## RepoGrounding evaluation reports

The included RepoGrounding reports are generated from a private headless evaluation harness. They are **codebase-context benchmarks**, not SWE-bench-style autonomous repair tests.

They test behaviours such as:

- repository bootstrap,
- source-grounded codebase QA,
- runtime/source-flow tracing,
- semantic file comparison,
- negative grounding,
- multi-turn continuity,
- patch/diff routing discipline,
- and internal artifact suppression.

## Private codebase review package

A separate private review package is available on request. A clean local source scan of the private native C++ source tree, excluding generated parser code, static assets, build output, vendor folders, and environment files, reports:

| Metric | Value |
|---|---:|
| Files analyzed | 364 |
| Total lines | 181,781 |
| Code lines | 144,110 |
| Reported complexity | 36,717 |

The private package can include:

- clean `scc` codebase metrics,
- source-tree/file-manifest evidence,
- source-level architecture notes,
- selected implementation evidence,
- public evidence links,
- selected screenshots,
- RepoGrounding evaluation context,
- and optional selected source or broader source access depending on review context.

It excludes secrets, provider configuration, local traces, environment files, generated caches, build outputs, private project data, and unnecessary binaries.

## Documentation map

- `docs/ARCHITECTURE.md` — public architecture overview
- `docs/PORTFOLIO_CASE_STUDY.md` — project story and technical case study
- `docs/DEMO_GUIDE.md` — how to present the demo
- `docs/evals/` — public RepoGrounding reports
- `docs/SECURITY_AND_PRIVACY.md` — public/private boundary and data safety notes
- `docs/KNOWN_LIMITATIONS.md` — honest scope boundaries
- `docs/PROJECT_STATUS.md` — current status
- `docs/FAQ.md` — common questions

## Current status

Coeus AI is currently presented as a portfolio/demo release. The GUI demo and public reports are available, while the full source, private headless harness, private traces, provider configuration, and implementation internals remain private.

## Portfolio summary

Coeus AI demonstrates native C++ application engineering, AI product architecture, project-aware retrieval, workflow/tool execution, source-grounding design, telemetry-driven debugging, and evaluation discipline.
