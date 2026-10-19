# Source Snapshot: Git and GitHub learning resources

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/get-started/start-your-journey/git-and-github-learning-resources
- **Upstream file:** [`github/docs` → `content/get-started/start-your-journey/git-and-github-learning-resources.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/get-started/start-your-journey/git-and-github-learning-resources.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/support/ask-and-answer-forum.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/support/ask-and-answer-forum.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Git and GitHub learning resources
redirect_from:
  - /articles/good-resources-for-learning-git-and-github
  - /articles/what-are-other-good-resources-for-learning-git-and-github
  - /articles/git-and-github-learning-resources
  - /github/getting-started-with-github/git-and-github-learning-resources
  - /github/getting-started-with-github/quickstart/git-and-github-learning-resources
  - /get-started/quickstart/git-and-github-learning-resources
intro: 'Discover essential Git and {% data variables.product.github %} resources, including tutorials, online courses, and community support to enhance your skills.'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
authors:
  - GitHub
shortTitle: Learning resources
category:
  - Start your GitHub journey
contentType: get-started
---

## Using {% data variables.product.github %}

Become better acquainted with {% data variables.product.github %} through our [AUTOTITLE](/get-started/using-github) articles:
* To review the fundamentals of a {% data variables.product.github %} workflow, see [AUTOTITLE](/get-started/using-github/github-flow).
* To learn about the various tools for working with repositories hosted on {% data variables.product.github %}, and how to choose a tool that best suits your needs, see [AUTOTITLE](/get-started/using-github/connecting-to-github).
* To understand the different communication tools on {% data variables.product.github %}, such as {% data variables.product.prodname_github_issues %}{% ifversion fpt or ghec %}, {% data variables.product.prodname_discussions %},{% endif %} and pull requests, see [AUTOTITLE](/get-started/using-github/communicating-on-github).

You can also check out our [{% data variables.product.github %} for Beginners YouTube series](https://www.youtube.com/playlist?list=PL0lo9MOBetEFcp4SCWinBdpml9B2U25-f).

## Using Git

Familiarize yourself with Git through our series of articles:

* [AUTOTITLE](/get-started/git-basics)
* [AUTOTITLE](/get-started/using-git)

There are also other online reading resources to help you learn Git:

* [Official Git project site](https://git-scm.com)
* [ProGit book](https://git-scm.com/book)
* [Git command list](https://git-scm.com/docs)
* [Git Guides](https://github.com/git-guides)

## Online courses

* {% data variables.product.prodname_learning %} offers free interactive courses that are built into {% data variables.product.github %} with instant automated feedback and help. Learn to open your first pull request, make your first open source contribution, create a {% data variables.product.prodname_pages %} site, and more. For more information about course offerings, see [{% data variables.product.prodname_learning %}]({% data variables.product.prodname_learning_link %}).

* [GitHub Learn](https://learn.github.com/) is {% data variables.product.github %}'s unified learning hub for courses, {% data variables.product.prodname_learning %}, videos, and {% data variables.product.prodname_certifications %}.

* [Microsoft Learn training for {% data variables.product.github %}](https://learn.microsoft.com/en-us/training/github/) offers {% data variables.product.github %}-authored, free training paths.

* [Git branching](https://learngitbranching.js.org/) is a free interactive tool for learning and practising Git concepts.

## Training

{% data variables.product.github %} offers [{% data variables.product.prodname_expert_services %}](https://github.com/services), with hands-on, project-based training for teams and individuals.

## Community

{% data reusables.support.ask-and-answer-forum %}

---

## Included files

### `data/reusables/support/ask-and-answer-forum.md`

````markdown
You can connect with developers around the world to ask and answer questions, learn, and interact directly with {% data variables.product.company_short %} staff. To get the conversation started, see [{% data variables.product.prodname_gcf %}](https://github.com/orgs/community/discussions/).
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_github_issues %}` | GitHub Issues |
| `{% data variables.product.prodname_discussions %}` | GitHub Discussions |
| `{% data variables.product.prodname_learning %}` | GitHub Skills |
| `{% data variables.product.prodname_pages %}` | GitHub Pages |
| `{% data variables.product.prodname_learning_link %}` | https://skills.github.com/ |
| `{% data variables.product.prodname_certifications %}` | GitHub Certifications |
| `{% data variables.product.prodname_expert_services %}` | GitHub Expert Services |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.prodname_gcf %}` | GitHub Community Support |
