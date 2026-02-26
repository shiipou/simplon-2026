# Copilot coding agent instructions (simplon-2026)

## Repository purpose
- This repository is a shared knowledge base / course notes for the Simplon 2026 cohort.
- Content is primarily **Markdown** documents organized by topic (HTML, CSS, Linux, Git, JavaScript, Java, etc.).
- The repo also contains an **Obsidian vault** configuration under `.obsidian/` (editor settings + plugins). Treat it as tooling/config, not authored learning content.

## High-level repo characteristics
- Project type: documentation repository (no compiled app).
- Main “source of truth”: Markdown files and the root `README.md` table of contents.
- Primary languages/formats:
  - Markdown (`*.md`) for documentation.
  - JSON/JS under `.obsidian/` for Obsidian configuration/plugins (often vendored/generated).
- There is currently **no `.github/workflows/` CI**, and no build/test/lint scripts detected.

## Contribution conventions (from `CONTRIBUTING.md`)
- Documentation files must be written **in French**.
- Pull request titles/descriptions should be **in English**.
- **Do not push directly to `main`**: always create a feature branch and open a PR.
- Naming conventions:
  - Folders: `NN. <Topic name>` (2-digit number + dot + space + name), e.g. `02. Langage HTML`.
  - Files: `NN. <Title>.md` (2-digit number + dot + space + title).
- Whenever you add/rename/move documentation, you must **update the root `README.md`** so the table of contents stays accurate.

## Project layout (where to make changes)
- Root `README.md`: primary navigation/table of contents. Keep links valid (URL-encoded spaces and special characters).
- Topic folders at repo root:
  - `01. Méthodes de recherche sur l'internet/`
  - `02. Langage HTML/`
  - `03. Langage CSS/`
  - `04. Obsidian/`
  - `05. Linux/`
  - `06. GIT/`
  - `07. Espace de travail/`
  - `08. Markdown/`
  - `09. VS Code/`
  - `10. Javascript (js)/`
  - `11. Veille techno/`
  - `12. Java/`
- Obsidian vault config:
  - `.obsidian/` (may contain plugin JS bundles with `TODO` comments; generally do not edit unless the change is specifically about Obsidian configuration).

## “Build / test / run” for this repo
There is no application to compile. Validation is documentation-focused:
1. **Link validation (manual)**
   - After changing paths/titles, verify links from `README.md` open correctly on GitHub.
   - Prefer relative links; remember that GitHub URLs require encoding spaces as `%20`.
2. **Markdown quality checks (manual)**
   - Ensure headings are consistent and the document is readable in GitHub’s renderer.
   - Keep code blocks properly fenced and specify a language when helpful.
3. **Obsidian compatibility (optional/manual)**
   - If you touched `.obsidian/` or internal links, open the vault in Obsidian and confirm notes render and links resolve.

## Search guidance for agents
- Trust this file first; only search the repo when the instructions are incomplete.
- For content changes, start from `README.md` and navigate to the target topic folder.
- Avoid editing `.obsidian/plugins/**` unless explicitly required: these files can be generated or third-party.