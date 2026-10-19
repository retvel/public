# Source Snapshot: Pull request merges

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/pull-requests/reference/pull-request-merges
- **Upstream file:** [`github/docs` → `content/pull-requests/reference/pull-request-merges.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/pull-requests/reference/pull-request-merges.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/pull_requests/default_merge_option.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/default_merge_option.md); [`data/reusables/pull_requests/squash_and_merge_summary.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/squash_and_merge_summary.md); [`data/reusables/pull_requests/rebase_and_merge_summary.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/rebase_and_merge_summary.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Pull request merges
intro: Learn strategies for merging pull requests, including merge commits, squash merges, and rebases, to manage repository history effectively.
redirect_from:
  - /pull-requests/concepts/about-pull-request-merges
  - /github/collaborating-with-issues-and-pull-requests/incorporating-changes-from-a-pull-request/about-pull-request-merges
  - /articles/about-pull-request-merge-squashing
  - /articles/about-pull-request-merges
  - /github/collaborating-with-issues-and-pull-requests/about-pull-request-merges
  - /github/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/about-pull-request-merges
  - /pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/about-pull-request-merges
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Merge and close pull requests
contentType: reference
---

Pull requests can be merged in different ways. The best strategy depends on how your team wants the repository history to look and how much detail you want to preserve from the pull request branch.

| Strategy | Result | Choose when |
| --- | --- | --- |
| Merge commit | Preserves every commit from the pull request branch and adds an explicit merge point. | Your team values complete history, or the individual commits are meaningful on their own. |
| Squash and merge | Combines all commits in the pull request into a single commit on the base branch. | A pull request represents one logical change, especially with many small fixup commits. |
| Rebase and merge | Adds each commit onto the base branch without a merge commit, for a linear history. | Your team wants a linear history and the commits are already organized clearly. |

## Merge your commits

{% data reusables.pull_requests.default_merge_option %}

A merge commit preserves the full commit history from the pull request branch. This makes it easier to see every commit that led to the final change, including review fixes and intermediate work. It also creates an explicit merge point in the base branch history.

Choose this strategy when your team values complete history or when the individual commits in a pull request are meaningful on their own.

## Squash and merge your commits

{% data reusables.pull_requests.squash_and_merge_summary %}

Squashing turns all commits in the pull request into one commit on the base branch. This keeps the default branch history concise and can make it easier to scan later. The tradeoff is that intermediate commits from the pull request are not preserved as separate commits on the base branch.

Choose this strategy when a pull request represents one logical change, especially if the branch includes many small fixup commits.

### Merge message for a squash merge

When you squash and merge, {% data variables.product.prodname_dotcom %} generates a default commit message that you can edit. The default message can include the pull request title, pull request description, or commit information, depending on repository settings and the number of commits in the pull request.

Maintainers and administrators can configure the default message for squashed commits. See [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/configuring-commit-squashing-for-pull-requests).

### Squashing and merging a long-running branch

Squash merging works best for short-lived branches. If you keep working on the same head branch after a squash merge, later pull requests can include commits that were already squashed into the base branch. This can make merge conflicts more likely and can force you to resolve the same conflicts more than once.

For long-running branches, consider using a merge commit or rebasing the branch before opening the next pull request.

## Rebase and merge your commits

{% data reusables.pull_requests.rebase_and_merge_summary %}

Rebasing adds each commit from the pull request branch onto the base branch without creating a merge commit. This produces a linear history while preserving the individual commits from the pull request.

Choose this strategy when your team wants a linear history and the pull request commits are already organized clearly. If {% data variables.product.github %} cannot safely rebase the pull request automatically, you can rebase locally, resolve conflicts, and push the updated branch. See [AUTOTITLE](/pull-requests/how-tos/merge-and-close-pull-requests/resolving-a-merge-conflict-using-the-command-line) and [AUTOTITLE](/pull-requests/how-tos/merge-and-close-pull-requests/merging-a-pull-request).

## Indirect merges

A pull request can be marked as merged if its head branch commits become reachable from the base branch outside that pull request. This can happen when the same commits are merged through another pull request or pushed directly to the default branch.

Indirect merges are uncommon, but they can affect automation and branch protection expectations. Pull requests merged indirectly are marked as `merged` even if branch protection rules on that pull request were not satisfied.

## Further reading

* [AUTOTITLE](/pull-requests/reference/pull-requests)
* [AUTOTITLE](/pull-requests/how-tos/merge-and-close-pull-requests)

---

## Included files

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

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.github %}` | GitHub |
