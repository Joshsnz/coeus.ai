# Troubleshooting

## CoeusAI.exe does not start

Try launching from PowerShell:

```powershell
cd .\bin
.\CoeusAI.exe
```

This keeps any console messages visible.

---

## Missing DLL error

Keep all included DLL files in the same directory as:

```text
CoeusAI.exe
```

If the release was downloaded as a zip, extract the full zip before running the executable.

---

## Windows security warning

Windows may warn when running a downloaded executable. This is common for unsigned portfolio/demo binaries.

Use the release only if you downloaded it from the official repository/release page.

---

## No model response

The demo may require provider configuration or API credentials that are not included in the public release.

The public package is primarily intended to demonstrate the compiled GUI application, documentation, and architecture.

---

## Looking for headless mode?

The public package does not include headless mode. Headless execution exists only in the private development/testing environment.

---

## UI opens but project features are limited

Some functionality may depend on local project data, private configuration, or model-provider setup.

See:

```text
docs/KNOWN_LIMITATIONS.md
```
