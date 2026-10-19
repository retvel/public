# Source Snapshot: About GitHub CLI

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/github-cli/github-cli/about-github-cli
- **Upstream file:** [`github/docs` → `content/github-cli/github-cli/about-github-cli.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/github-cli/github-cli/about-github-cli.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/cli/cli-intro.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/cli-intro.md); [`data/reusables/cli/about-cli.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/about-cli.md); [`data/reusables/cli/cli-features.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/cli-features.md); [`data/reusables/cli/cli-installation.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/cli-installation.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About GitHub CLI
intro: '{% data reusables.cli.cli-intro %}'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
redirect_from:
  - /github/getting-started-with-github/github-cli
  - /github/getting-started-with-github/using-github/github-cli
  - /actions/guides/managing-github-actions-with-github-cli
  - /get-started/using-github/github-cli
contentType: concepts
category:
  - Learn the basics
---
## About {% data variables.product.prodname_cli %}

{% data reusables.cli.about-cli %}

{% data reusables.cli.cli-features %}

For more information about what you can do with {% data variables.product.prodname_cli %}, see the [{% data variables.product.prodname_cli %} manual](https://cli.github.com/manual).

### What's the difference between {% data variables.product.prodname_cli %} and Git on the command line?

The Git command line interface (`git`) allows you to work with a local or remote Git repository. The remote repository may be hosted on {% data variables.product.prodname_dotcom %} or it may be hosted by another service.

{% data variables.product.prodname_cli %} (`gh`) is specifically for working with {% data variables.product.prodname_dotcom %}. It allows you to use the command line to interact with {% data variables.product.prodname_dotcom %} in all sorts of ways, as illustrated by the previous list. If you tend to work on the command line, you may prefer using {% data variables.product.prodname_cli %} instead of using {% data variables.product.prodname_dotcom %} in a browser. {% data variables.product.prodname_cli %} also makes it easier for you to create scripts to automate {% data variables.product.prodname_dotcom %} operations.

## Installing {% data variables.product.prodname_cli %}

{% data reusables.cli.cli-installation %}

## Sharing feedback

If you have feedback or feature requests, you can open an issue in the [`cli/cli` repository](https://github.com/cli/cli).

---

## Included files

### `data/reusables/cli/cli-intro.md`

````markdown
{% data variables.product.prodname_cli %} is a command-line tool that brings pull requests, issues, {% data variables.product.prodname_actions %}, and other {% data variables.product.github %} features to your terminal, so you can do all your work in one place.
````

### `data/reusables/cli/about-cli.md`

````markdown
{% data variables.product.prodname_cli %} is an open source tool for using {% data variables.product.prodname_dotcom %} from your computer's command line. When you're working from the command line, you can use the {% data variables.product.prodname_cli %} to save time and avoid switching context.
````

### `data/reusables/cli/cli-features.md`

````markdown
{% data variables.product.prodname_cli %} includes {% data variables.product.prodname_dotcom %} features such as:

* View, create, clone, and fork repositories
* Create, close, edit, and view issues and pull requests
* Review, diff, and merge pull requests
* Run, view, and list workflows
* Create, list, view, and delete releases
* Create, edit, list, view, and delete gists{% ifversion fpt %}
* List, create, delete, and connect to a codespace{% endif %}
* Retrieve information from the {% data variables.product.prodname_dotcom %} API
````

### `data/reusables/cli/cli-installation.md`

````markdown
For installation instructions for {% data variables.product.prodname_cli %}, see the [{% data variables.product.prodname_cli %} repository](https://github.com/cli/cli#installation).
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_cli %}` | GitHub CLI |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.github %}` | GitHub |
