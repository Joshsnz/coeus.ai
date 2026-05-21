# Coeus AI Architecture

## Overview

Coeus AI is a native C++ project-aware AI desktop workspace. It is structured around a separation between the desktop UI, application state, agent runtime, project context, retrieval, tool execution, model/provider integration, validation, telemetry, and a private headless evaluation runtime.

The public release does not include the private source code. This document explains the architecture at a professional overview level.

## High-level architecture

```text
Coeus AI
├── Native GUI Layer
│   ├── Skia rendering
│   ├── SDL2/OpenGL backend
│   ├── Conversation and context panels
│   ├── Evidence / telemetry / settings surfaces
│   └── User input and interaction surfaces
│
├── Application State Layer
│   ├── Active project state
│   ├── Conversation state
│   ├── Selected context
│   ├── Task/tool state
│   └── Runtime configuration
│
├── Agent Runtime Layer
│   ├── Turn processing
│   ├── Request construction
│   ├── Runtime orchestration
│   ├── Output handling
│   └── GUI bridge
│
├── Turn Policy / Compiled Turn Layer
│   ├── User-turn normalization
│   ├── Intent and request tagging
│   ├── Target selection
│   ├── Canonical answer contract
│   └── Resolved turn state
│
├── Project Context Layer
│   ├── Project inventory
│   ├── File context management
│   ├── Searchable source records
│   ├── Summaries / gists
│   └── Memory / snapshot support
│
├── Retrieval and Context Assembly
│   ├── File and chunk retrieval
│   ├── Source evidence selection
│   ├── Hybrid retrieval support
│   ├── Context lattice / packed context
│   └── Prompt-ready evidence assembly
│
├── Tool and Workflow Layer
│   ├── Command handling
│   ├── Built-in tools
│   ├── Planning/apply-style flows
│   ├── Tool observations
│   └── Connector boundary
│
├── Model / Provider Layer
│   ├── Provider configuration
│   ├── Remote HTTP model runner
│   ├── Local process runner
│   └── Model transport abstraction
│
├── Validation and Post-processing
│   ├── Output validation
│   ├── Answer-contract checks
│   ├── Internal artifact suppression
│   └── Presentation cleanup
│
└── Telemetry and Headless Evaluation
    ├── Run traces
    ├── Exported bundles
    ├── Tool traces
    ├── Marker truth
    └── Private headless test harness
```

## Compiled-turn concept

Internally, Coeus uses a policy-first compiled-turn model. A user message is not treated as a raw prompt that every downstream layer reinterprets. Instead, the turn is normalized into canonical turn state before retrieval, prompt assembly, validation, telemetry export, and final response handling.

The goal is to reduce drift between:

- what the user asked,
- what the app decided the turn means,
- what context was retrieved,
- what context was actually packed,
- and what the assistant is allowed to claim.

## Key truth boundaries

Coeus is designed around separating several forms of truth/state:

| Boundary | Meaning |
|---|---|
| Policy truth | What the turn means and what workflows are allowed. |
| Retrieval truth | What source/project material is actually indexed or retrieved. |
| Packed truth | What evidence/context was actually included in the prompt. |
| Continuity truth | Conversation/history state that may help route the turn but is not proof by itself. |
| Claim truth | What the assistant may safely assert to the user. |

This separation matters because source-grounded applications fail when summaries, memory, internal traces, or stale state silently become proof.

## GUI and headless dual surface

Coeus has two important runtime surfaces:

1. **Native GUI desktop app** — the public product surface.
2. **Private headless runtime** — a non-GUI automation and evaluation surface used by the private test harness.

This distinction lets the project support manual product demos and repeatable automated evaluations.

## Retrieval and context assembly

The retrieval layer supports repository-aware answers by selecting relevant project files or chunks from the loaded project. The context assembly layer then packages selected evidence into the model request.

The architecture is designed so the assistant can answer questions such as:

- how a feature is wired,
- what file owns a responsibility,
- how runtime flow moves across files,
- whether a feature is absent,
- and how two source files differ semantically.

## Telemetry and evaluation

Structured telemetry supports debugging and private evaluation. The public RepoGrounding reports are generated from this private headless evaluation harness.

The reports test codebase-context behaviour such as repository bootstrap, source-grounded answers, negative grounding, multi-turn continuity, semantic comparison, routing discipline, and artifact suppression.

## Public/private boundary

The public repository includes documentation, generated evaluation reports, release material, and a demo build. It does not include the full private source code, private prompts, private traces, provider configuration, local caches, private project data, or the private headless runner.
