# Source Snapshot: About pull requests

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/pull-requests/get-started/about-pull-requests
- **Upstream file:** [`github/docs` → `content/pull-requests/get-started/about-pull-requests.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/pull-requests/get-started/about-pull-requests.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/pull_requests/pr-stack-invitation.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pull_requests/pr-stack-invitation.md); [`data/features/pr-stacks.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/pr-stacks.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About pull requests
shortTitle: About pull requests
intro: 'Use pull requests to propose, discuss, and merge changes on {% data variables.product.github %}.'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
contentType: get-started
category: 
  - Create pull requests
---

A pull request proposes merging code changes from one branch into another. As a collaborative feature, pull requests give you a place to discuss and review work before it becomes part of a project.

## Why use pull requests

Pull requests turn a set of code changes into a conversation. Instead of merging work directly, you propose it so that collaborators can weigh in. This helps you and your team maintain high quality and secure code, in a few ways: 

* Catch bugs and problems early, before they reach the main branch.
* Discuss and improve changes together, with feedback tied to specific lines.
* Keep a clear, reviewable history of what changed and why.

## What you can do with pull requests

Pull requests make your changes easy to review and validate. With a pull request, you can:

* Propose changes from a branch or a fork.
{% ifversion pr-stacks %}* {% data reusables.pull_requests.pr-stack-invitation %}{% endif %}
* Discuss and review the proposed changes, line by line.
* Run automated checks, such as tests, builds, and code scanning, against the changes.
* Respond to feedback and update the pull request as it evolves.
* Merge the changes once reviews and required checks are satisfied.

## Key parts of a pull request

A pull request gathers everything you and your reviewers need into one place:

* **Conversation** shows the description, comments, reviews, and a timeline of activity.
* **Commits** shows how the branch changed over time.
* **Checks** shows the results of automated tests, builds, and other validations.
* **Files changed** shows the diff that reviewers comment on.
* The **merge box** summarizes whether you can merge your changes or not. It shows what may still need to happen, such as required reviews or checks, before a pull request can be merged.

## How pull requests fit your workflow

Whether you're proposing changes or reviewing someone else's, a pull request follows a few stages:

* **Branch or fork** the repository to create an isolated place to work.
* **Commit** your changes as you go, building up a history of your work.
* **Open a pull request** to propose merging your changes into the base branch.
* **Review and discuss** the changes with collaborators, making updates as needed.
* **Merge** the pull request when it's ready.

## Next steps

* [AUTOTITLE](/pull-requests/get-started/pull-request-quickstart)
* [AUTOTITLE](/pull-requests/get-started/reviewing-pull-requests-quickstart)
* [AUTOTITLE](/pull-requests/concepts/writing-code-for-a-project)

---

## Included files

### `data/reusables/pull_requests/pr-stack-invitation.md`

````markdown
Use stacked pull requests to break large code changes into a chain of smaller, dependent pull requests that you can review and merge independently.
````

### `data/features/pr-stacks.yml`

````yaml
versions:
  fpt: '*'
  ghec: '*'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
