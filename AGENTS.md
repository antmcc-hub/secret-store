# Secret Store Agent Instructions

Secret Store is a CLI toolkit for managing secrets through AWS Secrets Manager while keeping credentials out of AI chat and repo files.

## Map

- `secret-store`, `secret-get`, and `secret-env` are shell entrypoints.
- `secrets-lib.sh` contains shared shell helpers.
- `secrets_loader.py` is a Python helper that loads Secrets Manager values into environment variables as a dotenv replacement.
- `install.sh` installs the CLI helpers.
- `AI-HARNESS-PROTOCOL.md` documents safe AI-assistant usage patterns.
- `README.md` is the main user documentation.

## Build, Test, Ship

- There is no build step.
- Verify shell syntax with `bash -n <script>` before committing script changes.
- Verify Python syntax with `python3 -m py_compile secrets_loader.py` before committing Python changes.
- Shipping path is GitHub-only. Do not publish/install changes outside GitHub unless Ant explicitly asks.

## Guardrails

- Never print secret values in chat, logs, tests, examples, or docs.
- Prefer commands that tell the user how to enter secrets in their own terminal instead of accepting values in the AI session.
- Keep examples using fake placeholder secret names/values.
- Treat this repo as security-sensitive even though it is small.

## Docs Drift To Watch

README and AI harness protocol should stay aligned whenever command behavior changes.
