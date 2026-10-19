# Source Snapshot: GITHUB_TOKEN

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/actions/concepts/security/github_token
- **Upstream file:** [`github/docs` → `content/actions/concepts/security/github_token.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/actions/concepts/security/github_token.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/actions/actions-do-not-trigger-workflows.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/actions-do-not-trigger-workflows.md); [`data/reusables/actions/actions-do-not-trigger-pages-rebuilds.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/actions-do-not-trigger-pages-rebuilds.md); [`data/features/actions-github-token-pull-request-approval.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-github-token-pull-request-approval.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: GITHUB_TOKEN
intro: Learn what `GITHUB_TOKEN` is, how it works, and why it matters for secure automation in {% data variables.product.prodname_actions %} workflows.
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Secure your workflows
contentType: concepts
---

## About the `GITHUB_TOKEN`

At the start of each workflow job, {% data variables.product.prodname_dotcom %} automatically creates a unique `GITHUB_TOKEN` secret to use in your workflow. You can use the `GITHUB_TOKEN` to authenticate in the workflow job.

When you enable {% data variables.product.prodname_actions %}, {% data variables.product.prodname_dotcom %} installs a {% data variables.product.prodname_github_app %} on your repository. The `GITHUB_TOKEN` secret is a {% data variables.product.prodname_github_app %} installation access token. You can use the installation access token to authenticate on behalf of the {% data variables.product.prodname_github_app %} installed on your repository. The token's permissions are limited to the repository that contains your workflow. For more information, see [AUTOTITLE](/actions/reference/workflows-and-actions/workflow-syntax#permissions).

Before each job begins, {% data variables.product.github %} fetches an installation access token for the job. The `GITHUB_TOKEN` expires when the job finishes or after its effective maximum lifetime.

The effective maximum lifetime of the token depends on the type of runner:

* **{% data variables.product.github %}-hosted runners** The maximum job execution time is 6 hours, so the `GITHUB_TOKEN` can live for a maximum of 6 hours.
* **Self-hosted runners** The maximum job execution time is 5 days. However, because the `GITHUB_TOKEN` is an installation access token, it can only be refreshed for up to 24 hours. If your job runs longer than 24 hours, use a {% data variables.product.pat_generic %} or other authentication method instead.

The token is also available in the `github.token` context. For more information, see [AUTOTITLE](/actions/reference/workflows-and-actions/contexts#github-context).

## When `GITHUB_TOKEN` triggers workflow runs

{% data reusables.actions.actions-do-not-trigger-workflows %}

{% ifversion actions-github-token-pull-request-approval %}
> [!NOTE]
> If you need workflow runs from workflow-created pull requests to execute without requiring approval, use a {% data variables.product.prodname_github_app %} installation access token or a {% data variables.product.pat_generic %} instead of `GITHUB_TOKEN` when creating or updating the pull request.
{% endif %}

{% data reusables.actions.actions-do-not-trigger-pages-rebuilds %}

## Next steps

* [AUTOTITLE](/actions/tutorials/authenticate-with-github_token)
* [AUTOTITLE](/actions/reference/workflows-and-actions/workflow-syntax#permissions)

---

## Included files

### `data/reusables/actions/actions-do-not-trigger-workflows.md`

````markdown
When you use the repository's `GITHUB_TOKEN` to perform tasks, events triggered by the `GITHUB_TOKEN` will not create a new workflow run, with the following exceptions:

* `workflow_dispatch` and `repository_dispatch` events always create workflow runs.{% ifversion actions-github-token-pull-request-approval %}
* `pull_request` events with the `opened`, `synchronize`, or `reopened` activity types: when a workflow using `GITHUB_TOKEN` creates or updates a pull request, the resulting `pull_request` event creates workflow runs in an **approval-required** state. The pull request displays a banner in the merge box, and a user with write access to the repository can start the runs by selecting **Approve workflows to run**. Other `pull_request` activity types (such as `labeled`, `edited`, or `closed`) do not create workflow runs. This prevents recursive workflow runs while still allowing CI workflows to run on pull requests created by automation. For more information about approving workflow runs, see [AUTOTITLE](/actions/how-tos/manage-workflow-runs/approve-runs-from-forks).{% endif %}

For all other events, this behavior prevents you from accidentally creating recursive workflow runs. For example, if a workflow run pushes code using the repository's `GITHUB_TOKEN`, a new workflow will not run even when the repository contains a workflow configured to run when `push` events occur.
````

### `data/reusables/actions/actions-do-not-trigger-pages-rebuilds.md`

````markdown
Commits pushed by a {% data variables.product.prodname_actions %} workflow that uses the `GITHUB_TOKEN` do not trigger a {% data variables.product.prodname_pages %} build.
````

### `data/features/actions-github-token-pull-request-approval.yml`

````yaml
# Approval-required workflow runs for pull requests created or updated by
# workflows using GITHUB_TOKEN. Implementation feature flag:
# `actions_requires_approval_for_actions_bot_prs`.
versions:
  fpt: '*'
  ghec: '*'
  # ghes: '>=3.XX' # Uncomment when this ships to GHES (currently rolling out on dotcom)
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_github_app %}` | GitHub App |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.pat_generic %}` | personal access token |
| `{% data variables.product.prodname_pages %}` | GitHub Pages |
