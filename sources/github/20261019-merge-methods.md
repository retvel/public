# Source Snapshot: About merge methods on GitHub

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/about-merge-methods-on-github
- **Upstream file:** [`github/docs` → `content/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/about-merge-methods-on-github.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/about-merge-methods-on-github.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/pull_requests/configure_pull_request_merges_intro.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/configure_pull_request_merges_intro.md); [`data/reusables/pull_requests/merge-queue-references.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/merge-queue-references.md); [`data/reusables/pull_requests/default_merge_option.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/default_merge_option.md); [`data/reusables/pull_requests/squash_and_merge_summary.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/squash_and_merge_summary.md); [`data/reusables/pull_requests/rebase_and_merge_summary.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/rebase_and_merge_summary.md); [`data/reusables/pull_requests/rebase_and_merge_verification.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/rebase_and_merge_verification.md); [`data/reusables/pull_requests/rebase_and_merge_verification_2.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/rebase_and_merge_verification_2.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About merge methods on GitHub
intro: 'You can allow contributors with push access to your repository to merge their pull requests with different merge options or enforce a specific merge method for all of your repository''s pull requests.'
redirect_from:
  - /articles/about-merge-methods-on-github
  - /github/administering-a-repository/about-merge-methods-on-github
  - /github/administering-a-repository/configuring-pull-request-merges/about-merge-methods-on-github
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: About merge methods
category:
  - Configure merges and pull requests
---
{% data reusables.pull_requests.configure_pull_request_merges_intro %} You can enforce one type of merge method, such as commit squashing or rebasing, by only enabling the desired method for your repository.

> [!NOTE]
> When using the merge queue, you no longer get to choose the merge method, as this is controlled by the queue. {% data reusables.pull_requests.merge-queue-references %}
>
> Merge methods set on the repository that conflict with the merge method rule will prevent merging. For example if you do not allow rebase merging for the repository, and the merge rule only allows rebase on a branch, that merge will not be possible. For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets#require-a-pull-request-before-merging).

{% data reusables.pull_requests.default_merge_option %}

The default merge method creates a merge commit. You can prevent anyone from pushing merge commits to a protected branch by enforcing a linear commit history. For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches#require-linear-history).

## Squashing your merge commits

{% data reusables.pull_requests.squash_and_merge_summary %}

Before enabling squashing commits, consider these disadvantages:
* You lose information about when specific changes were originally made and who authored the squashed commits.
* If you continue working on the head branch of a pull request after squashing and merging, and then create a new pull request between the same branches, commits that you previously squashed and merged will be listed in the new pull request. You may also have conflicts that you have to repeatedly resolve in each successive pull request. For more information, see [AUTOTITLE](/pull-requests/reference/pull-request-merges#squashing-and-merging-a-long-running-branch).
* Some Git commands that use the "SHA" or "hash" ID may be harder to use since the SHA ID for the original commits is lost. For example, using [`git rerere`](https://git-scm.com/docs/git-rerere) may not be as effective.

For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/configuring-commit-squashing-for-pull-requests).

## Rebasing and merging your commits

{% data reusables.pull_requests.rebase_and_merge_summary %}

Before enabling commit rebasing, consider these disadvantages:
* Repository contributors may have to rebase on the command line, resolve any conflicts, and force push their changes to the pull request's topic branch (or remote head branch) before they can use the **rebase and merge** option on {% data variables.product.prodname_dotcom %}. Force pushing must be done carefully so contributors don't overwrite work that others have based their work on. To learn more about when the **Rebase and merge** option is disabled on {% data variables.product.prodname_dotcom %} and the workflow to re-enable it, see [AUTOTITLE](/pull-requests/reference/pull-request-merges#rebase-and-merge-your-commits).
* {% indented_data_reference reusables.pull_requests.rebase_and_merge_verification spaces=2 %}

  {% indented_data_reference reusables.pull_requests.rebase_and_merge_verification_2 spaces=2 %}

For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/configuring-commit-rebasing-for-pull-requests).

---

## Included files

### `data/reusables/pull_requests/configure_pull_request_merges_intro.md`

````markdown
You can configure pull request merge options to meet your workflow needs and preferences for managing Git history. For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges).
````

### `data/reusables/pull_requests/merge-queue-references.md`

````markdown

For more information about merge queues, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue).
````

### `data/reusables/pull_requests/default_merge_option.md`

````markdown
When you click the default **Merge pull request** option on a pull request, all commits from the feature branch are added to the base branch in a merge commit. The pull request is merged using [the `--no-ff` option](https://git-scm.com/docs/git-merge#_fast_forward_merge).

To merge pull requests, you must have [write permissions](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization) in the repository.

![Diagram of a standard merge and commit flow, where commits from a feature branch and an additional merge commit are both added to `main`.](assets/standard-merge-commit-diagram.png)
````

### `data/reusables/pull_requests/squash_and_merge_summary.md`

````markdown
When you select the **Squash and merge** option on a pull request, the pull request's commits are squashed into a single commit. Instead of seeing all of a contributor's individual commits from a topic branch, the commits are combined into one commit and merged into the default branch. Pull requests with squashed commits are merged using the [fast-forward option](https://git-scm.com/docs/git-merge#_fast_forward_merge).

To squash and merge pull requests, you must have [write permissions](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization) in the repository, and the repository must [allow squash merging](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/configuring-commit-squashing-for-pull-requests).

![Diagram of commit squashing, where multiple commits from a feature branch are combined into only one commit that is added to `main`.](assets/commit-squashing-diagram.png)

You can use squash and merge to create a more streamlined Git history in your repository. Work-in-progress commits are helpful when working on a feature branch, but they aren’t necessarily important to retain in the Git history. If you squash these commits into one commit when merging to the default branch, the changes are consolidated, leading to a clear Git history.
````

### `data/reusables/pull_requests/rebase_and_merge_summary.md`

````markdown
When you select the **Rebase and merge** option on a pull request, all commits from the topic branch (or head branch) are added onto the base branch individually without a merge commit. In that way, the rebase and merge behavior resembles a [fast-forward merge](https://git-scm.com/docs/git-merge#_fast_forward_merge) by maintaining a linear project history. However, rebasing achieves this by re-writing the commit history on the base branch with new commits.

The rebase and merge behavior on {% data variables.product.github %} deviates slightly from `git rebase` outside of {% data variables.product.prodname_dotcom %}. Rebase and merge on {% data variables.product.prodname_dotcom %}:

* Always updates the committer information and creates new commit SHAs, whereas `git rebase` does not change the committer information when the rebase happens on top of an ancestor commit.
* Drops commits that were empty to begin with, such as those created with `git commit --allow-empty`, whereas `git rebase` keeps originally-empty commits by default.

For more information about `git rebase`, see [git-rebase](https://git-scm.com/docs/git-rebase) in the Git documentation.

To rebase and merge pull requests, you must have [write permissions](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization) in the repository, and the repository must [allow rebase merging](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/configuring-commit-rebasing-for-pull-requests).

For a visual representation of `git rebase`, see [The "Git Branching - Rebasing" chapter from the _Pro Git_ book](https://git-scm.com/book/en/v2/Git-Branching-Rebasing).
````

### `data/reusables/pull_requests/rebase_and_merge_verification.md`

````markdown
When using the **Rebase and Merge** option on a pull request, it's important to note that the commits in the head branch are added to the base branch without commit signature verification.
When you use this option, {% data variables.product.prodname_dotcom %} creates a modified commit, using the data and content of the original commit. This means that {% data variables.product.prodname_dotcom %} didn't truly create this commit, and can't therefore sign it as a generic system user.
{% data variables.product.prodname_dotcom %} doesn't have access to the committer's private signing keys, so it can't sign the commit on the user's behalf.
````

### `data/reusables/pull_requests/rebase_and_merge_verification_2.md`

````markdown
A workaround for this is to rebase and merge locally, and then push the changes to the pull request's base branch.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.github %}` | GitHub |
