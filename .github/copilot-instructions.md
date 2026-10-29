# Copilot Instructions
# ====================
# These rules are applied to every AI interaction in this workspace.
# Shared via Git — the whole team gets the same AI behavior.
# Edit to match your team's conventions.

## General Rules

- Follow existing code style and conventions in the codebase.
- Prefer editing existing files over creating new ones.
- Do not add features, refactor code, or make "improvements" beyond what was asked.
- Keep answers concise and actionable.

## Workspace Navigation

- Start by reading the root `AGENTS.md` to understand workspace structure, including **Persistent memory** and **OpenSpec**.
- Use progressive disclosure: read TL;DR lines first, descend only into relevant directories.
- At session start, read `Knowledge/David-Brain/daily-log/status.md` and today's diary under `Knowledge/David-Brain/daily-log/`.
- Check `Knowledge/` for domain context before asking the user for information.
- Check `Repos/AGENTS.md` for clone paths before working in `Repos/`.
- Check `Skills/` for reusable procedures before inventing a new approach.

## Persistent memory

- Append meaningful steps to today's diary; update `status.md` before finishing.
- Put durable facts in `Knowledge/` topic notes, not only in chat.

## OpenSpec

- Code changes in `Repos/Laboratorio_Paradigmas/despues/` follow OpenSpec under `despues/openspec/` (`/opsx-propose`, `/opsx-apply`).

## Conventions

<!-- Add your team-specific conventions below. Examples: -->
<!-- - Use kebab-case for file names, PascalCase for classes. -->
