# Developing ShengWiki

ShengWiki is a personal knowledge base for notes on programming, mathematics, and scientific computing. This article describes the repository's current structure, planned content areas, and development workflow.

## Current structure

- `mkdocs.yml` is the single configuration and navigation source used by Zensical.
- `docs/index.md` contains the homepage introduction and Toolkit links.

## Planned content organization

The existing `Toolkits` collection is current. The subject collections below are future areas to develop, not published sections yet:

```text
docs/
├── index.md
├── data/
│   ├── Article/
│   ├── Fluid/
│   ├── Math/
│   ├── Programming/
│   └── Toolkits/
├── javascripts/
├── pics/
└── stylesheets/
```

Planned topics include:

- **Programming:** Fortran, Julia, and Python.
- **Mathematics:** linear algebra and numerical methods.
- **Fluid mechanics:** boundary layers, LST, PSE, and DNS.

Create a category and add it to navigation when it has publishable material. Until then, these remain roadmap items rather than empty site sections.

## Review and publication

Start development from an updated `main` on a task-specific branch, then open a pull request targeting `main`. The `zensical-build` check in `.github/workflows/validate.yml` runs automatically for pull requests targeting `main`. It uses read-only `contents: read` permission, runs `zensical build --clean --strict`, and does not deploy the site. This is a required status check and must pass before merge.

After review and explicit approval, merge the pull request. A merge to `main` triggers `.github/workflows/docs.yml` to build and deploy `site/` to [ShengWiki on GitHub Pages](https://dislikepineapple.github.io/ShengWiki/). The deployment workflow also supports manual dispatch from `main`. Feature-branch pushes do not publish the site. Commits, pushes, and merges require explicit user approval; do not manually run a deployment without approval or commit generated output.

The homepage is available from the [repository index](../../index.md).
