# Coeus AI — Portfolio Case Study

## Summary

Coeus AI is a native C++ desktop workspace for project-aware AI assistance. It was built to explore what sits around an LLM in a serious software tool: local project awareness, source retrieval, context assembly, tool execution, workflow routing, validation, telemetry, and repeatable evaluation.

The public package is a portfolio/demo release. The full source remains private, but the public repository includes the demo release, documentation, screenshots/video planning notes, and RepoGrounding evaluation reports.

## Problem

Generic chat assistants often fail in software-project contexts because they:

- lose repository state,
- answer from general knowledge instead of current source files,
- hallucinate unsupported features,
- misroute semantic source questions into patch/diff workflows,
- rely on summaries as if they were proof,
- and expose internal trace or storage artifacts in user-facing answers.

Coeus AI was built to investigate a more structured approach.

## Goal

The goal was to build a native desktop app that behaves like a project-aware workspace rather than a browser chatbot.

The system should:

- load or work against a local project,
- understand the project file surface,
- retrieve relevant source context,
- answer grounded engineering questions,
- preserve follow-up context,
- distinguish semantic questions from patch requests,
- expose useful diagnostics,
- and support private automated evaluation.

## Solution

Coeus combines several layers:

- **Native C++ GUI** using Skia/SDL2/OpenGL.
- **Application/project state** for active project and conversation context.
- **Compiled-turn policy pipeline** to normalize user turns into canonical state.
- **Retrieval and context assembly** over local source/project files.
- **Tool and command layer** for deterministic workflows.
- **Validation and post-processing** to reduce unsupported claims and artifact leakage.
- **Telemetry and headless runtime** for debugging and automated evaluation.

## What makes it more than a chatbot wrapper

The private source review confirms that Coeus has dedicated subsystems for:

- GUI rendering and interaction,
- agent policy and runtime orchestration,
- prompt construction and policy projection,
- file context and inventory,
- retrieval and context lattice assembly,
- memory and summaries,
- command/tool execution,
- telemetry and export,
- provider/model transport,
- and private headless evaluation.

A clean local scan of the private native C++ source tree, excluding generated parser code, static assets, build output, vendor folders, and environment files, reports:

| Metric | Value |
|---|---:|
| Files analyzed | 364 |
| Total lines | 181,781 |
| Code lines | 144,110 |
| Reported complexity | 36,717 |

These figures are used as codebase-scale evidence, not as a quality score.

## Evaluation

The public repository includes RepoGrounding reports generated from the private headless evaluation harness.

These reports test:

- repository bootstrap,
- source-grounded repository QA,
- runtime/source-flow tracing,
- semantic comparison,
- negative grounding,
- multi-turn continuity,
- patch/diff routing discipline,
- and internal artifact suppression.

They do not claim SWE-bench performance or full autonomous software repair.

## Public/private split

Public:

- demo release,
- rendered documentation,
- evaluation scorecards,
- architecture summary,
- case study,
- limitations,
- security/privacy notes.

Private on request:

- codebase metrics,
- source tree and file manifest,
- source-level architecture notes,
- selected implementation evidence,
- private source access depending on review context,
- private telemetry/eval notes.

Excluded:

- secrets,
- provider keys,
- environment files,
- private traces,
- generated caches,
- build outputs,
- private project data.

## Skills demonstrated

- Native C++ desktop application architecture.
- AI application/product engineering.
- Retrieval-backed codebase context.
- Workflow/tool execution.
- State and policy management.
- Evaluation harness design.
- Telemetry-driven debugging.
- Public/private release packaging.
