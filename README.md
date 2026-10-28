# ShengWiki

ShengWiki is a personal knowledge base built with Zensical.

## Repository and publication policy

The primary repository is `DislikePineapple/ShengWiki`. The planned public test URL is <https://dislikepineapple.github.io/ShengWiki/>. The intended policy is to keep the repository private during development; GitHub reported it as public during the 2026-10-28 preparation audit, so review that visibility mismatch and the publication audit before deployment. Do not change visibility without explicit approval.

The prepared `.github/workflows/docs.yml` workflow uses Zensical to build `site/` and deploy it through GitHub Pages. After publication is explicitly approved, GitHub Pages is configured to use GitHub Actions, and the workflow is on `main`, pushes to `main` automatically build and deploy the site. Manual workflow dispatch is also available. This local workflow does not publish on its own. Preserve `ShengWiki.jl` and its Documenter deployment until the new public site is verified. Commits, pushes, tags, publishing, and repository visibility changes require explicit approval.
