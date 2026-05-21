# Private Codebase Review Package

The public Coeus repository is intentionally a demo/documentation package. A separate private review package is available on request for code-level evaluation.

## What the private package can include

- Clean local `scc` codebase metrics.
- Source tree / file manifest evidence.
- Source-level architecture notes.
- Selected implementation evidence.
- Public evidence links.
- RepoGrounding evaluation context.
- Selected screenshots of GUI, telemetry, and evaluation surfaces.
- Optional selected source or broader source access depending on review context.

## Clean source scan

A clean local scan of the private native C++ source tree excludes:

- generated Tree-sitter parser code,
- static assets and fonts,
- build outputs,
- cache directories,
- vendor/external directories,
- environment/secrets files.

Clean scan summary:

| Metric | Value |
|---|---:|
| Files analyzed | 364 |
| Total lines | 181,781 |
| Code lines | 144,110 |
| Reported complexity | 36,717 |
| C++ files | 177 |
| Header files | 187 |

These figures are codebase-scale evidence. They are not presented as a quality score.

## What is excluded

The private review package excludes:

- `.env` files,
- provider keys,
- secret configuration,
- private local traces,
- generated caches,
- build artifacts,
- unnecessary binaries,
- private project data,
- and generated parser/static-asset noise.

## Why this split exists

The public package is for professional presentation. The private package is for reviewers who need code-level proof without exposing secrets, traces, local data, or implementation material to the public internet.
