# Source Snapshot: Pull requests

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/pull-requests/reference/pull-requests
- **Upstream file:** [`github/docs` → `content/pull-requests/reference/pull-requests.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/pull-requests/reference/pull-requests.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/pull_requests/mark-ready-review.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/mark-ready-review.md); [`data/reusables/open-source/open-source-guide-general.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/open-source/open-source-guide-general.md); [`data/reusables/open-source/open-source-learning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/open-source/open-source-learning.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Pull requests
shortTitle: Pull requests
intro: Propose, review, and merge code changes using pull requests to collaborate effectively and maintain code quality.
redirect_from:
  - /pull-requests/concepts/about-pull-requests
  - /github/collaborating-with-issues-and-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests
  - /articles/using-pull-requests
  - /articles/about-pull-requests
  - /github/collaborating-with-issues-and-pull-requests/about-pull-requests
  - /github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests
  - /github/collaborating-with-issues-and-pull-requests/getting-started/about-collaborative-development-models
  - /articles/types-of-collaborative-development-models
  - /articles/about-collaborative-development-models
  - /github/collaborating-with-issues-and-pull-requests/about-collaborative-development-models
  - /github/collaborating-with-pull-requests/getting-started/about-collaborative-development-models
  - /pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models
  - /pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Create pull requests
contentType: reference
---

Pull requests are proposals to merge code changes into a project. A pull request is {% data variables.product.github %}'s key **collaboration feature**, letting you discuss and review changes before merging them. This helps teams work together, catch issues early, and maintain code quality.

<a href="https://github.com/pulls?ref_product=github&ref_type=engagement&ref_style=button" target="_blank" class="btn btn-primary mt-3 mr-3 no-underline"><span>View your pull requests</span> {% octicon "link-external" height:16 aria-label="link-external" %}</a>

## Working with pull requests

A pull request brings together the context reviewers need to understand a change. This context is organized into tabs:

* The **Conversation** tab shows the description, timeline, comments, and reviews.
* The **Commits** tab shows how the pull request branch changed over time.
* The **Checks** tab shows automated tests, builds, and other validations.
* The **Files changed** tab shows the diff that reviewers use to understand the proposed changes.
* The **Findings** tab shows automated code review results, such as code scanning alerts, for the proposed changes.

Separately from the tabs, the **merge status** highlights blockers, missing approvals, and other requirements before merging. It appears in the pull request header and in the merge box.

Together, these views help authors and reviewers discuss the change, track feedback, and decide when the pull request is ready to merge.

## Draft pull requests

When you create a pull request, you can choose to make it a draft pull request. Draft pull requests cannot be merged, and code owners are not automatically requested to review them. Drafts are useful when you want to share work-in-progress without formally requesting reviews.

{% data reusables.pull_requests.mark-ready-review %} You can convert a pull request to a draft at any time. See [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/changing-the-stage-of-a-pull-request).

## Pull request refs and merge branches

When you open a pull request, {% data variables.product.github %} creates temporary Git references that point to the pull request's head branch and, when possible, to a simulated merge result. These refs help {% data variables.product.github %} and integrations evaluate the pull request without changing the base branch.

For most contributors, these refs stay in the background. They are most relevant when you are building automation, debugging CI behavior, or fetching pull request state locally. For information about how {% data variables.product.prodname_actions %} uses the merge branch, see [AUTOTITLE](/actions/reference/workflows-and-actions/events-that-trigger-workflows#how-the-merge-branch-affects-your-workflow).

## Differences between commits on compare and pull request pages

Compare pages and pull request pages can calculate changed files from different merge bases. As a result, the same branches can sometimes show different diffs in each place.

This usually matters when the base branch has changed since the pull request was created. Pull request pages focus on what the pull request introduced, while compare pages reflect the current comparison between two refs.

## Collaborative development models

The way you use pull requests depends on the type of development model you use in your project. You can use the fork and pull model or the shared repository model.

### Fork and pull model

In the fork and pull model, anyone can fork an existing ("upstream") repository if they have read access and the owner of the upstream repository allows it. Be aware that a fork and its upstream share the same Git data. This means that all content uploaded to a fork is accessible from the upstream and all other forks of that upstream.

You do not need permission from the upstream repository to push to a fork you created. You can optionally allow anyone with push access to the upstream repository to make changes to your pull request branch. This model is popular with open-source projects because it reduces friction for new contributors and lets people work independently without upfront coordination.

> [!TIP]
> {% data reusables.open-source.open-source-guide-general %} {% data reusables.open-source.open-source-learning %}

### Shared repository model

In the shared repository model, collaborators have push access to a single shared repository and create topic branches when they need to make changes. Pull requests are useful in this model because they start code review and general discussion about a set of changes before the changes are merged into the main development branch. This model is more common with small teams and organizations collaborating on private projects.

## Further reading

* [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/creating-a-pull-request)
* [AUTOTITLE](/pull-requests/reference/branches)
* [AUTOTITLE](/pull-requests/how-tos/review-pull-requests/commenting-on-a-pull-request)
* [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/creating-a-pull-request-from-a-fork)
* [AUTOTITLE](/pull-requests/how-tos/work-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork)

---

## Included files

### `data/reusables/pull_requests/mark-ready-review.md`

````markdown
When you're ready to get feedback on your pull request, you can mark your draft pull request as ready for review. Marking a pull request as ready for review will request reviews from any code owners.
````

### `data/reusables/open-source/open-source-guide-general.md`

````markdown
For more information on open source, specifically how to create and grow an open source project, we've created [Open Source Guides](https://opensource.guide/) that will help you foster a healthy open source community.
````

### `data/reusables/open-source/open-source-learning.md`

````markdown
You can also take a free [{% data variables.product.prodname_learning %}]({% data variables.product.prodname_learning_link %}) course on maintaining open source communities.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_learning %}` | GitHub Skills |
| `{% data variables.product.prodname_learning_link %}` | https://skills.github.com/ |
