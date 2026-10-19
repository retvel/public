# Source Snapshot: Creating a pull request

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request
- **Upstream file:** [`github/docs` → `content/pull-requests/how-tos/create-pull-requests/creating-a-pull-request.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/pull-requests/how-tos/create-pull-requests/creating-a-pull-request.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/enterprise-accounts/emu-permission-propose.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/enterprise-accounts/emu-permission-propose.md); [`data/reusables/pull_requests/perms-to-open-pull-request.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/perms-to-open-pull-request.md); [`data/reusables/pull_requests/close-issues-using-keywords.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/close-issues-using-keywords.md); [`data/reusables/repositories/navigate-to-repo.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/navigate-to-repo.md); [`data/reusables/repositories/new-pull-request.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/new-pull-request.md); [`data/reusables/repositories/pr-title-description.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/pr-title-description.md); [`data/reusables/repositories/create-pull-request.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/create-pull-request.md); [`data/reusables/repositories/asking-for-review.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/asking-for-review.md); [`data/reusables/cli/cli-learn-more.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/cli-learn-more.md); [`data/reusables/repositories/changed-files.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/changed-files.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Creating a pull request
intro: Create a pull request to propose changes to the code in a repository.
permissions: 'Anyone with read access to a repository can create a pull request.<br>{% data reusables.enterprise-accounts.emu-permission-propose %}'
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request
  - /articles/creating-a-pull-request
  - /github/collaborating-with-issues-and-pull-requests/creating-a-pull-request
  - /pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Create a pull request
category:
  - Create pull requests
contentType: how-tos
---

If you want to create a new branch for your pull request but don't have write permissions to the repository, you can fork the repository first. See [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork) and [AUTOTITLE](/pull-requests/reference/forks).

When you create your pull request, you can specify which branch you want to merge your changes into. Pull requests can only be opened between two different branches.

{% data reusables.pull_requests.perms-to-open-pull-request %}

{% data reusables.pull_requests.close-issues-using-keywords %}

## Creating the pull request

{% webui %}

{% data reusables.repositories.navigate-to-repo %}
1. In the "Branch" menu, choose the branch that contains your commits.

   ![Screenshot of the branch dropdown menu on the main page of a repository.](assets/branch-dropdown.png)

{% data reusables.repositories.new-pull-request %}
1. Use the _base_ branch dropdown menu to select the branch where you want to merge your changes. Then, use the _compare_ branch dropdown menu to choose the topic branch where you made your changes.
{% data reusables.repositories.pr-title-description %}
{% data reusables.repositories.create-pull-request %}

{% data reusables.repositories.asking-for-review %}

After your pull request has been reviewed, it can be merged into the repository. See [AUTOTITLE](/pull-requests/how-tos/merge-and-close-pull-requests/merging-a-pull-request).

{% endwebui %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

To create a pull request, use the `gh pr create` subcommand.

```shell
gh pr create
```

To assign a pull request to an individual, use the `--assignee` or `-a` flags. You can use `@me` to self-assign the pull request.

```shell
gh pr create --assignee "@octocat"
```

To specify the branch into which you want the pull request merged, use the `--base` or `-B` flags. To specify the branch that contains commits for your pull request, use the `--head` or `-H` flags.

```shell
gh pr create --base my-base-branch --head my-changed-branch
```

To include a title and body for the new pull request, use the `--title` and `--body` flags.

```shell
gh pr create --title "The bug is fixed" --body "Everything works again"
```

To mark a pull request as a draft, use the `--draft` flag.

```shell
gh pr create --draft
```

To add labels or milestones to the new pull request, use the `--label` and `--milestone` flags.

```shell
gh pr create --label "bug,help wanted" --milestone octocat-milestone
```

To add the new pull request to a specific project, use the `--project` flag.

```shell
gh pr create --project octocat-project
```

To assign an individual or team as reviewers, use the `--reviewer` flag.

```shell
gh pr create --reviewer monalisa,hubot --reviewer myorg/team-name
```

To create the pull request in your default web browser, use the `--web` flag.

```shell
gh pr create --web
```

{% endcli %}

{% desktop %}

1. Click **Preview Pull Request**. {% data variables.product.prodname_desktop %} opens a preview dialog that shows the diff of the changes between your current branch and the base branch.

   Alternatively, to go straight to {% data variables.product.prodname_dotcom %} to create your pull request, select the dropdown icon and click **Create Pull Request**.

1. Confirm that the branch in the **base:** dropdown menu is the branch where you want to merge your changes.

   ![Screenshot of the "Open a Pull Request" dialog window. A button with a dropdown icon, labeled "base: development", is outlined in orange.](assets/base-branch-selection.png)

   {% data variables.product.prodname_desktop %} tells you whether the current branch can be automatically merged into the base branch.

   ![Screenshot of the "Open a Pull Request" dialog window. A status label stating "Can't automatically merge" is highlighted with an orange outline.](assets/preview-dialog-merge-status.png)

1. Click **Create Pull Request**. {% data variables.product.prodname_desktop %} opens your default browser and takes you to {% data variables.product.prodname_dotcom %}.
{% data reusables.repositories.pr-title-description %}
{% data reusables.repositories.create-pull-request %}

{% enddesktop %}

{% ifversion fpt or ghec %}

{% codespaces %}

1. After you commit changes to your local copy of the repository, click the **Create Pull Request** icon.
![Screenshot of the top of the "Source Control" side bar. The pull request icon is highlighted with a dark orange outline.](assets/codespaces-commit-pr-button.png)
1. Check that the local branch and repository you're merging from, and the remote branch and repository you're merging into, are correct. Then, give the pull request a title and a description.
![Screenshot of the "{% data variables.product.prodname_dotcom %} Pull Request" side bar with a form for creating a pull request, including "Title" and "Description" fields.](assets/codespaces-commit-pr.png)
1. Click **Create**.

For more information on creating pull requests in {% data variables.product.prodname_github_codespaces %}, see [AUTOTITLE](/codespaces/developing-in-a-codespace/using-github-codespaces-for-pull-requests).

{% endcodespaces %}

{% endif %}

## Making changes to files in your pull request

After you open your pull request, you can continue changing files by adding new commits to your head branch.

{% webui %}

You can also make changes to files on the {% data variables.product.github %} website.

1. On {% data variables.product.github %}, navigate to a pull request in a repository.
{% data reusables.repositories.changed-files %}
1. Scroll down to the file you want to make changes to.
   * If the pull request has a lot of files, you can use the filter to locate the file.
1. Above the file you want to change, click {% octicon "kebab-horizontal" aria-label="Show options" %}.
   ![Screenshot of the options above a file on the "File changed" tab. The "Show options" button is highlighted with an orange rectangle.](assets/menu-on-pull-request-file.png)
1. In the menu, click **Edit file**.
1. Make your changes in the editor. When you commit your change, choose to commit directly back to your head branch.

{% endwebui %}

## Further reading

* [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork)
* [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/keeping-your-pull-request-in-sync-with-the-base-branch)
* [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/changing-the-base-branch-of-a-pull-request)
* [AUTOTITLE](/issues/tracking-your-work-with-issues/using-issues/creating-an-issue)
* [AUTOTITLE](/issues/tracking-your-work-with-issues/using-issues/assigning-issues-and-pull-requests-to-other-github-users)
* [AUTOTITLE](/get-started/writing-on-github)

---

## Included files

### `data/reusables/enterprise-accounts/emu-permission-propose.md`

````markdown
{% ifversion ghec %} Members of an {% data variables.enterprise.prodname_emu_enterprise %} can only propose changes in repositories that are part of their enterprise. {% endif %}
````

### `data/reusables/pull_requests/perms-to-open-pull-request.md`

````markdown
{% ifversion fpt or ghec %}

> [!NOTE]
> To open a pull request in a public repository, you must have write access to the head or the source branch or, for organization-owned repositories, you must be a member of the organization that owns the repository to open a pull request.

{% endif %}
````

### `data/reusables/pull_requests/close-issues-using-keywords.md`

````markdown
You can link a pull request to an issue to show that a fix is in progress and automatically close the issue when the pull request is merged. For more information, see [AUTOTITLE](/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue).
````

### `data/reusables/repositories/navigate-to-repo.md`

````markdown
1. On {% data variables.product.prodname_dotcom %}, navigate to the main page of the repository.
````

### `data/reusables/repositories/new-pull-request.md`

````markdown
1. Above the list of files, in the yellow banner, click **Compare & pull request** to create a pull request for the associated branch.

   ![Screenshot of the banner above the list of files.](assets/pull-request-compare-pull-request.png)
````

### `data/reusables/repositories/pr-title-description.md`

````markdown
1. Type a title and description for your pull request.
````

### `data/reusables/repositories/create-pull-request.md`

````markdown
1. To create a pull request that is ready for review, click **Create Pull Request**.
To create a draft pull request, use the drop-down and select **Create Draft Pull Request**, then click **Draft Pull Request**. If you are the member of an organization, you may need to request access to draft pull requests from an organization owner. See [AUTOTITLE](/pull-requests/reference/pull-requests#draft-pull-requests).
````

### `data/reusables/repositories/asking-for-review.md`

````markdown
> [!TIP]
> After you create a pull request, you can ask a specific person to review your proposed changes. See [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/requesting-a-pull-request-review).
````

### `data/reusables/cli/cli-learn-more.md`

````markdown
> [!NOTE]
> To learn more about {% data variables.product.prodname_cli %}, see [AUTOTITLE](/github-cli/github-cli/about-github-cli).
````

### `data/reusables/repositories/changed-files.md`

````markdown
1. On the pull request, click **{% octicon "file-diff" aria-hidden="true" aria-label="file-diff" %} Files changed**.

   ![Screenshot of the tabs for a pull request. The "Files changed" tab is outlined in dark orange.](assets/pull-request-tabs-changed-files.png)
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_desktop %}` | GitHub Desktop |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_github_codespaces %}` | GitHub Codespaces |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.enterprise.prodname_emu_enterprise %}` | enterprise with managed users |
| `{% data variables.product.prodname_cli %}` | GitHub CLI |
