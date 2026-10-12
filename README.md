# Nox-Code

Nox Code is an open-source, local-first AI coding agent built for intelligent code generation, project-wide understanding, automated testing, debugging, and continuous performance optimization. Its VS Code extension foundation prioritizes local model compatibility, workspace-aware context retrieval, secure patch handling, and bounded repair loops.

## Features

- OpenAI-compatible provider support for local endpoints such as Ollama, LM Studio, llama.cpp, and OmniRoute.
- Workspace scanner with default exclusions for dependencies, build outputs, and binaries.
- Security helpers for secret redaction, workspace path validation, and dangerous command detection.
- Patch parsing and validation to reduce unsafe file modifications.
- Bounded repair loops to keep automated retries observable and finite.

## Setup

1. Install Node.js 20 or newer.
2. Install dependencies:
   `npm install`
3. Build the extension:
   `npm run build`
4. Run the tests:
   `npm test`

## Local model usage

Configure the provider with a base URL and model name. For example:

- Ollama: `http://localhost:11434`
- LM Studio: `http://localhost:1234/v1`
- llama.cpp server: `http://localhost:8080/v1`
- OmniRoute: `http://localhost:20128/v1`

Store secrets in VS Code SecretStorage when available; never log tokens or API keys.

## Security

The project treats workspace files and model responses as untrusted. It rejects path traversal, redacts likely secrets, and blocks risky shell commands by default.

## Limitations

This is a foundational implementation. A full production-grade code assistant requires richer workspace indexing, model orchestration, and approval flows beyond the included scaffold.
