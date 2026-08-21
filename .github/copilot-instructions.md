# GitHub Copilot Instructions for Playback

These instructions help guide GitHub Copilot in generating suggestions, commit messages, and pull request descriptions for the Playback repository.

## Coding Standards & Style
- **C++ Standard:** Follow modern C++ practices.
- **Formatting & Linting:** Strictly adhere to the project's `.clang-format` and `.clang-tidy` rules. Do not introduce code that violates these checks.
- **Architecture:** The project is based on the Flashback Java mod architecture. Ensure code logic is robust and stable. Rely on LeviLamina for modding, ImGui for the UI, and FFmpeg for media handling. Do not make assumptions about hardcoded file paths; use a stable, high-level approach.

## Commit Messages & PR Titles
- **Format:** Use Conventional Commits standard (e.g., `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`, `perf:`).
- **Commit Body:** When generating a commit message, provide a brief description of *why* the change was made, not just *what* changed.
- **PR Titles:** Should match the primary commit message format (e.g., `feat: add new cinematic camera interpolation`).
- **Branch Names:** When suggesting or evaluating branch names, ensure they follow the `type/description` pattern (e.g., `feat/add-ai-files`, `fix/crash-on-export`).

## Branching Strategy
- **`develop`**: The main upstream branch for active development. **All PRs and analysis must target `develop`.**
- **`main`**: The stable branch. Do not target PRs directly to `main`.
- **`feat/26.20`**: The stable release branch for Minecraft version v26.20.

## Security & Quality
- Never suggest hardcoded credentials, sensitive tokens, or insecure memory operations.
- Prefer safe C++ constructs (e.g., smart pointers over raw pointers) to prevent memory leaks in the recording/export pipeline.

## Build System
- The project uses Xmake. When asked to generate build scripts or commands, reference the `xmake.lua` file.
