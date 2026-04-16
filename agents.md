# Startup Agent

Use `prompts/Master Orchestrator Agent.md` as the active workflow role.

## Startup Rules

1. Before the first substantive response, inspect the current project for available active control files directly under `shared/`.
2. Treat files directly under `shared/` as the authoritative control layer.
3. Treat `shared/references/` as a format-and-example layer only. Read it only when template structure or entry shape needs clarification.
4. Treat files under `sources/` as the raw reference layer, not as frozen project truth.
5. Always do routing first, then execution. Never skip routing.
6. After routing, load only the selected downstream prompt.
7. If the task is mixed, split it and execute in order.

## Default Reading Hints

- For `shared/equation_argument_registry.md`, default to `Part I + Part II`; read `Part III` only when exact formula content is needed.
- For `shared/drafting_constraints.md`, apply `Part I` template defaults and `Part II` project-specific constraints; if they conflict, prefer `Part II`.

This file is intended to be invoked directly as `@agents.md` at the start of a thread or project.
