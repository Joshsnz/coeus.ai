# Coeus AI Demo Guide

## Running the Demo

From the repository root:

```powershell
.\bin\CoeusAI.exe
```

Keep any included DLL files in the same directory as `CoeusAI.exe`.

---

## Public Demo Scope

This release includes the GUI desktop build only.

It does **not** include:

- A headless executable
- A command-line evaluation runner
- Private test harnesses
- Private source code
- API keys or provider credentials

---

## What to Demonstrate

The demo is intended to show the application as a native project-aware AI workspace.

Recommended walkthrough:

1. Launch `CoeusAI.exe`.
2. Open or select a local project if the demo package supports it.
3. Show the main conversation interface.
4. Ask a project-aware question.
5. Show how context/evidence panels relate to the answer.
6. Open settings or tool panels.
7. Show telemetry/debugging surfaces if available.
8. Explain that the private development architecture also supports headless testing, but the public package is GUI-only.

---

## Suggested Demo Questions

Use questions that demonstrate project awareness without exposing private implementation details:

```text
What does this project do?
```

```text
Explain the main architecture of this project.
```

```text
Where is the main runtime flow handled?
```

```text
Compare these two files at a high level.
```

```text
What changed recently in this project?
```

Actual behavior depends on the included demo data, runtime configuration, and available model/provider setup.

---

## What Reviewers Should Notice

- This is a native C++ application, not a web wrapper.
- The UI has custom rendering and panels.
- The assistant is designed around project context.
- The system has retrieval, tooling, telemetry, and runtime separation.
- The public build is a GUI demo package; source code and private test builds are not included.

---

## Troubleshooting

If the executable does not start:

1. Confirm you are running Windows x64.
2. Keep all bundled DLLs beside `CoeusAI.exe`.
3. Run from PowerShell so startup errors remain visible:

```powershell
cd .\bin
.\CoeusAI.exe
```

4. Check `docs/TROUBLESHOOTING.md`.
