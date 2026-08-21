# AI Agents Guide for Playback

This file provides long-term, stable guidance for AI coding assistants (e.g., GitHub Copilot, Cursor, etc.) and other automated tools interacting with the Playback repository.

## Branching Strategy & Workflow
- **`develop`**: This is the primary upstream branch for all active development. **All Pull Requests, code analysis, and feature work must target the `develop` branch.** Do not target `main` directly.
- **`main`**: The stable branch. Do not open PRs against `main` unless explicitly instructed for a hotfix.
- **`feat/26.20`**: The stable release branch for Minecraft version v26.20.
- **Branch Naming:** When creating new branches for work, always use Conventional Commits prefixes followed by a descriptive name. Examples:
  - `feat/add-new-ui-panel`
  - `chore/update-dependencies`
  - `fix/resolve-crash-on-export`
  - `docs/update-readme`
  - `ci/fix-github-actions`

## Project Architecture (High-Level)
Playback is an open-source Minecraft Bedrock replay mod. Its core architecture is based on the concepts from the **Flashback** Java mod.
- **Modding Framework:** LeviLamina
- **User Interface:** ImGui
- **Video Export:** FFmpeg
Do not rely on hardcoded file paths when generating code or suggesting changes, as internal structures may evolve. Rely on this stable, high-level understanding of the technology stack.

## Standard Files & Rules
Do not duplicate instructions that exist in other files. Instead, refer to the source of truth:
- **Code Formatting & Linting:** Obey `.clang-format` and `.clang-tidy`.
- **Build System:** Refer to `xmake.lua` for dependencies and build configuration.
- **Human Documentation:** `README.md` and `CONTRIBUTING.md` are intended for human developers. **Do not update them** unless explicitly requested by the user.
- **Changelog:** Update `CHANGELOG.md` only when completing a feature, fix, or significant change, and ensure the format matches existing entries.

## Core Capabilities & Skills
- **Skills Directory:** Check `./.skills/` for specific execution engine instructions.
- For all C++ compilation, package management, and build system tasks, invoke the `xmake-build-engine` skill located in `.skills/xmake/SKILL.md`.

## Commit Standard
When generating commit messages or PR titles, always use **Conventional Commits** (e.g., `feat:`, `fix:`, `chore:`). Ensure the commit body explains the *why* behind the change.
