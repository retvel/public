# Source Snapshot: Forks

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/pull-requests/reference/forks
- **Upstream file:** [`github/docs` → `content/pull-requests/reference/forks.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/pull-requests/reference/forks.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/repositories/you-can-fork.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/you-can-fork.md); [`data/reusables/enterprise-accounts/emu-forks.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/enterprise-accounts/emu-forks.md); [`data/reusables/repositories/deleted_forks_from_private_repositories_warning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/deleted_forks_from_private_repositories_warning.md); [`data/reusables/repositories/private_forks_inherit_permissions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/private_forks_inherit_permissions.md); [`data/reusables/repositories/org-base-permissions-private-forks.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/org-base-permissions-private-forks.md); [`data/reusables/repositories/rulesets-push-rulesets-fork-network-information.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/rulesets-push-rulesets-fork-network-information.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Forks
intro: Understand how forks enable independent collaboration by creating separate repositories connected to the original, with distinct settings and permissions.
redirect_from:
  - /pull-requests/concepts/about-forks
  - /github/collaborating-with-issues-and-pull-requests/working-with-forks/about-forks
  - /articles/about-forks
  - /github/collaborating-with-issues-and-pull-requests/about-forks
  - /github/collaborating-with-pull-requests/working-with-forks/about-forks
  - /github/collaborating-with-issues-and-pull-requests/working-with-forks/what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility
  - /articles/changing-the-visibility-of-a-network
  - /articles/what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility
  - /github/collaborating-with-issues-and-pull-requests/what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility
  - /github/collaborating-with-pull-requests/working-with-forks/what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility
  - /pull-requests/collaborating-with-pull-requests/working-with-forks/what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility
  - /pull-requests/collaborating-with-pull-requests/working-with-forks/about-permissions-and-visibility-of-forks
  - /pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Work with forks
contentType: reference
---

Forks are repositories that start as copies of another repository, called the upstream repository. A fork has its own settings and permissions but stays connected to the upstream repository.

When you view a forked repository on {% data variables.product.github %}, the upstream repository is indicated below the name of the fork.

## What makes forks distinct from branches

A branch is part of one repository. A fork is a separate repository with its own settings and collaboration space.

Each fork can have its own:

* Branches
* Members and discussions
* Issues and pull requests
* Actions and projects
* Tags, labels, and wikis

## Which repositories can be forked?

{% data reusables.repositories.you-can-fork %}

Repository, organization, and enterprise policies can limit whether repositories can be forked and where forks can be created. For private{% ifversion ghec or ghes %} and internal{% endif %} repositories, access to forks also depends on repository visibility, organization membership, and administrator settings.

{% ifversion fpt or ghec %}

If you're a member of an {% data variables.enterprise.prodname_emu_enterprise %}, additional restrictions apply to the repositories you can fork. {% ifversion ghec %}{% data reusables.enterprise-accounts.emu-forks %}{% endif %} See [AUTOTITLE](/enterprise-cloud@latest/admin/concepts/identity-and-access-management/enterprise-managed-users){% ifversion fpt %} in the {% data variables.product.prodname_ghe_cloud %} documentation.{% else %}.{% endif %}

{% endif %}

See [AUTOTITLE](/organizations/managing-organization-settings/managing-the-forking-policy-for-your-organization){% ifversion fpt %}.{% else %} and [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-repository-management-policies-in-your-enterprise#enforcing-a-policy-for-forking-private-or-internal-repositories).{% endif %}

## Visibility of forks

A fork's visibility depends on the upstream repository. Public repository forks are public, and private repository forks are private.{% ifversion ghec or ghes %} For internal repositories, the visibility of a fork depends on its owner: a fork owned by an organization is internal, while a fork owned by a personal account is private.{% endif %} You cannot change the visibility of a fork by itself.

A repository network includes the upstream repository, its forks, and forks of those forks. Repositories in the network share Git data and remain connected to the upstream repository. See [AUTOTITLE](/repositories/viewing-activity-and-data-for-your-repository/understanding-connections-between-repositories).

Deleting a repository or changing its visibility can affect the network. If you delete a fork, code contributions from that fork can remain accessible to the repository network.

## What happens to forks when a repository is deleted or changes visibility

{% data reusables.repositories.deleted_forks_from_private_repositories_warning %}

Visibility changes can separate forks into new repository networks so that existing fork owners can keep working without unexpected loss of access.

| Action | Effect on forks |
| --- | --- |
| A private repository is deleted | Its private forks are also deleted. |
| A public repository is deleted | An active public fork becomes the new upstream repository for the network. |
| A public repository is made private | Its public forks stay public in a separate network. |
| A private repository is made public | Private forks stay private but disconnect into separate private networks. |

Changing a public repository to private can also affect stars, watchers, dependency graph, {% data variables.product.prodname_dependabot_alerts %}, and {% data variables.product.prodname_code_scanning %} availability. Review repository visibility settings carefully before changing them.

{% ifversion ghes %}
If a public repository has anonymous Git read access enabled and the repository is made private, all of the repository's forks lose anonymous Git read access and return to the default disabled setting. If a forked repository is made public, repository administrators can re-enable anonymous Git read access. See [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/enabling-anonymous-git-read-access-for-a-repository).
{% endif %}

## Permissions of forks

{% data reusables.repositories.private_forks_inherit_permissions %}

Public forks do not inherit the permissions structure of the upstream repository. Fork owners control access to their forks, but repository networks still share Git data. Commits pushed to any repository in a network can be accessible from other repositories in that network, including the upstream repository.

When you fork a public repository to your personal account, you can allow maintainers of the upstream repository to push to your pull request branch. This can help maintainers update your branch, run tests, or resolve small issues before merging. You cannot give push permissions to a fork owned by an organization. See [AUTOTITLE](/pull-requests/how-tos/work-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork).

### Push rulesets for forked repositories

{% data reusables.repositories.rulesets-push-rulesets-fork-network-information %}

See [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets#push-rulesets).

### Important security considerations

Forks are powerful collaboration tools, but they can expose code and history in ways that are easy to overlook.

* Forks have their own permissions separate from the upstream repository.
* Owners of an upstream repository can read all forks in the repository network.
* Organization owners may have administrative access to forks created in personal namespaces.
* Organization owners of a repository that has been forked have read permission to forks created in organizations, but do not have the ability to delete the fork or its branches.
* Forks created in another organization will not be deleted when individual access is removed from the upstream repository.
* Git data from any repository in a network may be accessed from any repository in the same network, including the upstream repository, even after a fork is deleted.

Before allowing forks for sensitive work, review the permissions and visibility model for your repository or organization.

### Forks within an organization

Forks within the same organization copy collaborator and team settings from the upstream repository. The organization controls permissions for these forks, and existing visible teams may keep access.

### Forks within an enterprise

Internal repositories support a single level of forking. You cannot fork a private fork of an internal repository. This keeps access and management simpler for repositories that are visible across an enterprise.

---

## Included files

### `data/reusables/repositories/you-can-fork.md`

````markdown
{% ifversion ghec %}
Generally, you can fork any public repository to your personal account or to an organization where you have permission to create repositories, unless you're a member of an {% data variables.enterprise.prodname_emu_enterprise %}.

Forking of private and internal repositories is governed by repository, organization, and enterprise policies. With the most permissive policies:

* You can fork a private repository to your personal account or to an organization where you have permission to create repositories, including an organization in another enterprise.
* You can fork an internal repository to your personal account or to an organization in the same enterprise as the upstream repository. You can never fork an internal repository to an organization in another enterprise.

{% elsif ghes %}
You can fork a private or internal repository to your personal account or to an organization on {% data variables.product.prodname_dotcom %} where you have permission to create repositories, provided that the settings for the repository and your enterprise policies allow forking.

Generally, you can fork any public repository to your personal account or to an organization where you have permission to create repositories.

{% elsif fpt %}
You can fork any public repository:

* To your personal account
* To an organization where you have permission to create repositories

If you have access to a private repository and the owner permits forking, you can fork the repository:

* To your personal account
* To an organization on {% data variables.product.prodname_team %} where you have permission to create repositories

You cannot fork a private repository to an organization using {% data variables.product.prodname_free_team %}. For more information about {% data variables.product.prodname_team %} and {% data variables.product.prodname_free_team %}, see [AUTOTITLE](/get-started/learning-about-github/githubs-plans).
{% endif %}
````

### `data/reusables/enterprise-accounts/emu-forks.md`

````markdown
{% data variables.enterprise.prodname_managed_users_caps %} cannot fork repositories from outside of the enterprise. They can fork private or internal repositories owned by organizations in the enterprise into their user account namespace or other organizations owned by the enterprise, as specified by enterprise policy.
````

### `data/reusables/repositories/deleted_forks_from_private_repositories_warning.md`

````markdown
> [!WARNING]
> * If you remove a person’s access to a private repository, any of their forks of that private repository are deleted. Local clones of the private repository are retained. If a team's access to a private repository is revoked or a team with access to a private repository is deleted, and team members do not have access to the repository through another team, private forks of the repository will be deleted.{% ifversion ghes %}
> * When [LDAP Sync is enabled](/admin/managing-iam/using-ldap-for-enterprise-iam/using-ldap#enabling-ldap-sync), if you remove a person from a repository, they will lose access but their forks will not be deleted. If the person is added to a team with access to the original organization repository within three months, their access to the forks will be automatically restored on the next sync.{% endif %}
> * You are responsible for ensuring that people who have lost access to a repository delete any confidential information or intellectual property.
> * People with admin permissions to a private{% ifversion ghes or ghec %} or internal{% endif %} repository can disallow forking of that repository, and organization owners can disallow forking of any private{% ifversion ghes or ghec %} or internal{% endif %} repository in an organization. For more information, see [AUTOTITLE](/organizations/managing-organization-settings/managing-the-forking-policy-for-your-organization) and [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-the-forking-policy-for-your-repository).
````

### `data/reusables/repositories/private_forks_inherit_permissions.md`

````markdown
Private forks inherit the permissions structure of the upstream repository. This helps owners of private repositories maintain control over their code. For example, if the upstream repository is private and gives read/write access to a team, then the same team will have read/write access to any forks of the private upstream repository. Only team permissions (not individual permissions) are inherited by private forks.

> [!NOTE]
> {% data reusables.repositories.org-base-permissions-private-forks %} For more information, see [AUTOTITLE](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/setting-base-permissions-for-an-organization#about-base-permissions-for-an-organization).
````

### `data/reusables/repositories/org-base-permissions-private-forks.md`

````markdown
When you change base permissions for an organization, permissions for private forks are not automatically updated.
````

### `data/reusables/repositories/rulesets-push-rulesets-fork-network-information.md`

````markdown
Push rules apply to the entire fork network for a repository, ensuring every entry point to the repository is protected. For example, if you fork a repository that has push rulesets enabled, the same push rulesets will also apply to your forked repository.

For a forked repository, the only people who have bypass permissions for a push rule are the people who have bypass permissions in the root repository.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.enterprise.prodname_emu_enterprise %}` | enterprise with managed users |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_dependabot_alerts %}` | Dependabot alerts |
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_free_team %}` | GitHub Free |
| `{% data variables.enterprise.prodname_managed_users_caps %}` | Managed user accounts |
