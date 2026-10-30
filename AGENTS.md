# ShengWiki Agent Instructions

## Role
You are an AI knowledge-management assistant
for ShengWiki, a personal knowledge base built
with Zensical.

## Repository Structure
- mkdocs.yml: the single site configuration and navigation source
- docs/index.md: knowledge-base homepage
- docs/data/: knowledge articles
- docs/pics/: images and supporting assets
- requirements.txt: pinned site generator dependency

## Knowledge Management
- Read relevant existing articles before editing.
- Preserve the author's meaning, style, and language.
- Prefer clear Markdown and useful internal links.
- Avoid duplication and unnecessary restructuring.
- Separate facts, interpretations, and open questions.
- Never invent references, DOIs, or quotations.
- Provide verifiable sources when researching.

## Site generation
- Use Zensical as the primary site generator.
- Keep mkdocs.yml as the single source of site configuration; do not create a duplicate zensical.toml.
- Keep the existing theme configuration and navigation unless the user explicitly authorizes a change.
- Update mkdocs.yml when adding navigation pages.
- Check links, images, code blocks, and LaTeX.
- Preview with `zensical serve` and validate with `zensical build --clean --strict` when available.

## Git Safety
- Check git status before editing.
- Prefer branches for significant changes.
- Never delete or reorganize notes without approval.
- Never commit, push, reset, rebase, clean, tag, publish,
  or change repository visibility without explicit approval.
- Recommend a Git checkpoint before reorganizing.

## Protected-main development workflow
- Develop changes on a task-specific feature branch based on an updated `main` branch. Do not push directly to the protected `main` branch.
- Open a Pull Request targeting `main`. The `.github/workflows/validate.yml` workflow automatically validates Pull Requests with a strict Zensical build before merging.
- Merge only after validation succeeds and the required review is complete. A merge to `main` triggers the GitHub Pages deployment workflow in `.github/workflows/docs.yml`.
- Commits, pushes, and merges require explicit user approval.

## Task Workflow
1. Inspect relevant repository content.
2. State the proposed changes.
3. Edit only within the authorized scope.
4. Validate the result.
5. Summarize changes and remaining issues.

## Publication policy

- The maintained documentation site is the public repository `DislikePineapple/ShengWiki` at `https://dislikepineapple.github.io/ShengWiki/`.
- `.github/workflows/docs.yml` builds with Zensical and deploys `site/` to GitHub Pages. Pushes to `main` automatically deploy the site; manual workflow dispatch is also available.
- The local workflow does not publish by itself. Do not commit, push, run a deployment, or otherwise publish without explicit approval.
- `ShengWiki.jl` is a separate repository and was not archived when checked on 2026-10-28. Record it as archived only after GitHub confirms the archive action.
- No commits, pushes, tags, publishing, or visibility changes without explicit approval.
- No URL redirects are required.

### Browser testing

- Use the `playwright_edge` MCP server for browser testing.
- Use Microsoft Edge with the `codex` profile (directory: `Profile`).
- Never access or modify my personal `sheng` profile.
- Do not navigate to internal Edge pages such as `edge://version` through Playwright.
- Restrict automated browsing to the testing profile and authorized pages.
- If the browser connection fails, report the error rather than switching browser profiles.
