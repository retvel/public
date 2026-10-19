# Source Snapshot: About repositories

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories
- **Upstream file:** [`github/docs` → `content/repositories/creating-and-managing-repositories/about-repositories.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/repositories/creating-and-managing-repositories/about-repositories.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/discussions/you-can-use-discussions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/discussions/you-can-use-discussions.md); [`data/reusables/gated-features/more-info.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/more-info.md); [`data/reusables/repositories/about-internal-repos.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/about-internal-repos.md); [`data/reusables/repositories/internal-repo-default.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/internal-repo-default.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About repositories
intro: A repository contains all of your code, your files, and each file's revision history. You can discuss and manage your work within the repository.
redirect_from:
  - /articles/about-repositories
  - /github/creating-cloning-and-archiving-repositories/about-repositories
  - /github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/about-repositories
  - /github/creating-cloning-and-archiving-repositories/about-repository-visibility
  - /github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/about-repository-visibility
  - /articles/what-are-the-limits-for-viewing-content-and-diffs-in-my-repository
  - /articles/limits-for-viewing-content-and-diffs-in-a-repository
  - /github/creating-cloning-and-archiving-repositories/limits-for-viewing-content-and-diffs-in-a-repository
  - /github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/limits-for-viewing-content-and-diffs-in-a-repository
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Create and set up a repository
---

## About repositories

A repository is the most basic element of {% data variables.product.prodname_dotcom %}. It's a place where you can store your code, your files, and each file's revision history. Repositories can have multiple collaborators and can be either public{% ifversion ghes or ghec %}, internal,{% endif %} or private.

To create a new repository, go to [https://github.com/new](https://github.com/new). For instructions, see [AUTOTITLE](/repositories/creating-and-managing-repositories/quickstart-for-repositories).

## Repository terminology

Before getting started with repositories, learn these important terms.

{% rowheaders %}

Term | Definition |
---- | ---------- |
Branch | A parallel version of your code that is contained within the repository, but does not affect the primary or main branch.
Clone | To download a full copy of a repository's data from {% data variables.location.product_location %}, including all versions of every file and folder.
Fork | A new repository that shares code and visibility settings with the original "upstream" repository.
Merge | To take the changes from one branch and apply them to another.
Pull request | A request to merge changes from one branch into another.
Remote | A repository stored on {% data variables.product.github %}, not on your computer.
Upstream | The branch on an original repository that has been forked or cloned. The corresponding branch on the cloned or forked repository is called the "downstream."

{% endrowheaders %}

## About repository ownership

You can own repositories individually, or you can share ownership of repositories with other people in an organization.

In either case, access to repositories is managed by permissions. For more information, see [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/repository-access-and-collaboration/permission-levels-for-a-personal-account-repository) and [AUTOTITLE](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization).

## About collaboration

You can use repositories to manage your work and collaborate with others.
* You can use issues to collect user feedback, report software bugs, and organize tasks you'd like to accomplish. For more information, see [AUTOTITLE](/issues/tracking-your-work-with-issues/learning-about-issues/about-issues).{% ifversion fpt or ghec %}
* {% data reusables.discussions.you-can-use-discussions %}{% endif %}
* You can use pull requests to propose changes to a repository. For more information, see [AUTOTITLE](/pull-requests/reference/pull-requests).
* You can use {% data variables.product.prodname_projects_v2 %} to organize and prioritize your issues and pull requests. For more information, see [AUTOTITLE](/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects).

{% ifversion fpt or ghec %}
With {% data variables.product.prodname_free_team %} for personal accounts and organizations, you can work with unlimited collaborators on unlimited public repositories with a full feature set, or unlimited private repositories with a limited feature set. To get advanced tooling for private repositories, you can upgrade to {% data variables.product.prodname_pro %}, {% data variables.product.prodname_team %}, or {% data variables.product.prodname_ghe_cloud %}. {% data reusables.gated-features.more-info %}
{% else %}
Each person and organization can own unlimited repositories and invite an unlimited number of collaborators to all repositories.
{% endif %}

## About repository visibility

You can restrict who has access to a repository by choosing a repository's visibility: {% ifversion ghes or ghec %}public, internal, or private{% else %}public or private{% endif %}.

When you create a repository, you can choose to make the repository public or private.{% ifversion ghec or ghes %} If you're creating the repository in an organization{% ifversion ghec %} that is owned by an enterprise account{% endif %}, you can also choose to make the repository internal.{% endif %}{% ifversion fpt %} Repositories in organizations that use {% data variables.product.prodname_ghe_cloud %} and are owned by an enterprise account can also be created with internal visibility. For more information, see [the {% data variables.product.prodname_ghe_cloud %} documentation](/enterprise-cloud@latest/repositories/creating-and-managing-repositories/about-repositories).{% endif %}

{%- ifversion fpt or ghec %}
* {% ifversion ghec %}If your account is not a {% data variables.enterprise.prodname_managed_user %}, you can create public repositories. {% endif %}Public repositories are accessible to everyone on the internet.
* Private repositories are only accessible to you, people you explicitly share access with, and, for organization repositories, certain organization members.
{%- elsif ghes %}
* If {% data variables.location.product_location %} is not in private mode or behind a firewall, public repositories are accessible to everyone on the internet. Otherwise, public repositories are available to everyone using {% data variables.location.product_location %}, including outside collaborators.
* Private repositories are only accessible to you, people you explicitly share access with, and, for organization repositories, certain organization members.
{%- endif %}
{%- ifversion ghec or ghes %}
* Internal repositories are accessible to all enterprise members. For more information, see [About internal repositories](#about-internal-repositories).
{%- endif %}

{% ifversion fpt or ghec %}

### Security considerations for repository visibility

Public repositories expose your codebase to everyone, increasing the risk that attackers might exploit vulnerabilities or access sensitive information. You can mitigate these risks by enabling {% data variables.product.github %} security features such as {% data variables.product.prodname_dependabot %}, {% data variables.product.prodname_secret_scanning %}, push protection, and {% data variables.product.prodname_code_scanning %} for the repository. Additionally, you should add a security policy (a `SECURITY.md` file) to your repository, that outlines how vulnerabilities should be reported, to ensure that potential threats are addressed efficiently.

Although private repositories restrict access to authorized users, it's still essential to implement strong access controls, multi-factor authentication, and regular audits to mitigate risks.

For more information, see [AUTOTITLE](/code-security/getting-started/quickstart-for-securing-your-repository).

{% endif %}

Organization owners always have access to every repository created in an organization. For more information, see [AUTOTITLE](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization).

People with admin permissions for a repository can change an existing repository's visibility. For more information, see [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility).

{% ifversion ghes or ghec %}

## About internal repositories

{% data reusables.repositories.about-internal-repos %} For more information on innersource, see [AUTOTITLE](/admin/concepts/enterprise-best-practices/use-innersource).

{% ifversion ghec %}

> [!NOTE]
> You can only create internal repositories if you use {% data variables.product.prodname_ghe_cloud %} with an enterprise account. An enterprise account is a separate type of account that allows a central point of management for multiple organizations. For more information, see [AUTOTITLE](/get-started/learning-about-github/types-of-github-accounts).

{% endif %}

Organization members have read permissions to all internal repositories in an enterprise, including those in organizations they are not a member of. Internal repositories are not visible to people {% ifversion fpt or ghec %}outside of the enterprise{% else %}who are not members of any organization{% endif %}, including outside collaborators on organization repositories. For more information, see [AUTOTITLE](/admin/managing-accounts-and-repositories/managing-roles-in-your-enterprise/abilities-of-roles) and [AUTOTITLE](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization).

{% data reusables.repositories.internal-repo-default %}

Repository, organization, and enterprise policies determine whether internal repositories can be forked and where forks can be created. For more information, see [AUTOTITLE](/organizations/managing-organization-settings/managing-the-forking-policy-for-your-organization) and [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-repository-management-policies-in-your-enterprise#enforcing-a-policy-for-forking-private-or-internal-repositories).

{% endif %}

## Next steps

Here are some helpful resources for taking your next steps with repositories.

* [AUTOTITLE](/repositories/creating-and-managing-repositories/best-practices-for-repositories): Learn how to use repositories most effectively.
* [AUTOTITLE](/repositories/creating-and-managing-repositories/creating-a-new-repository): Create a new repository.
* [AUTOTITLE](/pull-requests/how-tos/commit-changes/managing-branches-within-your-repository): Learn how to create and delete branches within your repository.
* [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/creating-a-pull-request): Create a pull request to propose and collaborate on changes to a repository.

---

## Included files

### `data/reusables/discussions/you-can-use-discussions.md`

````markdown
You can use {% data variables.product.prodname_discussions %} to ask and answer questions, share information, make announcements, and conduct or participate in conversations about a project. For more information, see [AUTOTITLE](/discussions/collaborating-with-your-community-using-discussions/about-discussions).
````

### `data/reusables/gated-features/more-info.md`

````markdown
See [AUTOTITLE](/get-started/learning-about-github/githubs-plans).
````

### `data/reusables/repositories/about-internal-repos.md`

````markdown
{% ifversion ghec %}If your organization is owned by an enterprise account, you{% else %}You{% endif %} can use internal repositories to practice "innersource" within your enterprise. Members of your enterprise can collaborate using open source methodologies without sharing proprietary information publicly{% ifversion ghes %}, even with private mode disabled{% endif %}.
````

### `data/reusables/repositories/internal-repo-default.md`

````markdown
{% ifversion fpt or ghec %}
Internal repositories are the default setting for all new repositories created in an organization owned by an enterprise account.
{% endif %}
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_projects_v2 %}` | Projects |
| `{% data variables.product.prodname_free_team %}` | GitHub Free |
| `{% data variables.product.prodname_pro %}` | GitHub Pro |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.enterprise.prodname_managed_user %}` | managed user account |
| `{% data variables.product.prodname_dependabot %}` | Dependabot |
| `{% data variables.product.prodname_secret_scanning %}` | secret scanning |
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_discussions %}` | GitHub Discussions |
