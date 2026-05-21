# Security and Privacy

## Public release boundary

The public Coeus repository is a portfolio/demo package. It includes documentation, generated evaluation reports, release material, and public-facing project notes.

It does not include:

- full private source code,
- private prompts,
- provider credentials,
- private traces,
- private project data,
- local caches,
- generated artifacts,
- environment files,
- or the private headless runner.

## Local project caution

Coeus is designed around local project context. Users should avoid loading projects containing secrets unless they understand their model/provider configuration and data-flow risks.

## Provider configuration

No API keys are bundled in the public repository. Provider configuration and secrets are intentionally excluded.

## Telemetry and traces

Telemetry exists to support debugging and private evaluation. Public reports are sanitized/generated artifacts. Raw private traces are not included in the public package.

## Private review package

A private codebase review package may be shared on request. That package excludes secrets, environment files, provider keys, local traces, generated caches, build output, and private project data.
