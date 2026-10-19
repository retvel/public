# Source Snapshot: Setting repository visibility

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility
- **Upstream file:** [`github/docs` → `content/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/advanced-security/more-info-ghas.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/advanced-security/more-info-ghas.md); [`data/reusables/repositories/navigate-to-repo.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/navigate-to-repo.md); [`data/reusables/repositories/sidebar-settings.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/sidebar-settings.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Setting repository visibility
intro: You can choose who can view your repository.
redirect_from:
  - /articles/making-a-private-repository-public
  - /articles/making-a-public-repository-private
  - /articles/converting-a-public-repo-to-a-private-repo
  - /articles/setting-repository-visibility
  - /github/administering-a-repository/setting-repository-visibility
  - /github/administering-a-repository/managing-repository-settings/setting-repository-visibility
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Repository visibility
category:
  - Manage access and repository policies
---

## About repository visibility changes

> [!NOTE]
> If you can't change a repository's visibility, the organization owner may have restricted the ability to change repository visibility to organization owners only. For more information, see [AUTOTITLE](/organizations/managing-organization-settings/restricting-repository-visibility-changes-in-your-organization).

{% ifversion ghec %}

Members of an {% data variables.enterprise.prodname_emu_enterprise %} can only set the visibility of repositories owned by their personal account to private, and repositories in their enterprise's organizations can only be private or internal. For more information, see [AUTOTITLE](/admin/concepts/identity-and-access-management/enterprise-managed-users).

{% endif %}

We recommend reviewing the following caveats before you change the visibility of a repository.

{% ifversion ghes %}

> [!WARNING]
> Changes to the visibility of a large repository or repository network may affect data integrity. Visibility changes can also have unintended effects on forks. {% data variables.product.company_short %} recommends the following before changing the visibility of a repository network.
>
> * Wait for a period of reduced activity on {% data variables.location.product_location %}.
> * Contact your site administrator before proceeding. Your site administrator can contact us for further assistance by visiting {% data variables.contact.contact_ent_support %}.

{% endif %}

### Making a repository private

* {% data variables.product.github %} will detach public forks of the public repository and put them into a new network. Public forks are not made private.
{%- ifversion ghes or ghec %}
* If you change a repository's visibility from internal to private, {% data variables.product.github %} will remove forks that belong to any user without access to the newly private repository. The visibility of any forks will also change to private. For more information, see [AUTOTITLE](/pull-requests/reference/forks#what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility)
{%- endif %}
{%- ifversion fpt %}
* If you're using {% data variables.product.prodname_free_user %} for personal accounts or organizations, some features won't be available in the repository after you change the visibility to private. Any published {% data variables.product.prodname_pages %} site will be automatically unpublished. If you added a custom domain to the {% data variables.product.prodname_pages %} site, you should remove or update your DNS records before making the repository private, to avoid the risk of a domain takeover. For more information, see [AUTOTITLE](/get-started/learning-about-github/githubs-plans) and [AUTOTITLE](/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
{%- endif %}
{%- ifversion fpt or ghec %}
* {% data variables.product.prodname_dotcom %} will no longer include the repository in the {% data variables.product.prodname_archive %}. For more information, see [AUTOTITLE](/repositories/archiving-a-github-repository/about-archiving-content-and-data-on-github#about-the-github-archive-program).
* {% data variables.product.prodname_GHAS %} features, such as {% data variables.product.prodname_code_scanning %}, will stop working unless the repository is owned by an organization that has access to the feature in private repositories with a {% data variables.product.prodname_GHAS %}, {% data variables.product.prodname_GH_code_security %}, or {% data variables.product.prodname_GH_secret_protection %} license and sufficient spare seats. {% data reusables.advanced-security.more-info-ghas %}
{%- endif %}
{%- ifversion ghes %}
* Anonymous Git read access is no longer available. For more information, see [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/enabling-anonymous-git-read-access-for-a-repository).
{%- endif %}

{% ifversion ghes or ghec %}

### Making a repository internal

* Any forks of the repository will remain in the repository network, and {% data variables.product.github %} maintains the relationship between the root repository and the fork. For more information, see [AUTOTITLE](/pull-requests/reference/forks#what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility)

{% endif %}

### Making a repository public

* {% data variables.product.github %} will detach private forks and turn them into a standalone private repository. For more information, see [AUTOTITLE](/pull-requests/reference/forks#what-happens-to-forks-when-a-repository-is-deleted-or-changes-visibility){% ifversion fpt or ghec %}
* If you're converting your private repository to a public repository as part of a move toward creating an open source project, see the [Open Source Guides](http://opensource.guide) for helpful tips and guidelines. You can also take a free course on managing an open source project with [{% data variables.product.prodname_learning %}]({% data variables.product.prodname_learning_link %}). Once your repository is public, you can also view your repository's community profile to see whether your project meets best practices for supporting contributors. For more information, see [AUTOTITLE](/communities/setting-up-your-project-for-healthy-contributions/about-community-profiles-for-public-repositories).
* The repository will automatically gain access to {% data variables.product.prodname_GHAS %} features.
* Actions history and logs will be visible to everyone. If your repository had reusable or required workflows that were shared from a different repository in your organization, the workflow file path including the repository name will be visible in the logs. For more information on how to remove workflow runs and artifacts see [AUTOTITLE](/actions/how-tos/manage-workflow-runs) and [AUTOTITLE](/rest/actions/workflow-runs).

For information about improving repository security, see [AUTOTITLE](/code-security/getting-started/quickstart-for-securing-your-repository).{% endif %}

## Consequences of changing a repository's visibility

>[!CAUTION]Before you change your repository's visibility, understand the consequences of this change.

### Changing from public to private

* Stars and watchers for this repository will be erased, which will affect repository rankings.
* Custom {% data variables.product.prodname_dependabot %} alert rules will be disabled unless {% data variables.product.prodname_GH_code_security %} is enabled for this repository. Dependency graph and {% data variables.product.prodname_dependabot_alerts %} will remain enabled with permission to perform read-only analysis on this repository.
> * {% data variables.product.prodname_code_scanning_caps %} will become unavailable unless {% data variables.product.prodname_code_security %} is enabled for this repository.
* Current forks will remain public and will be detached from this repository.

### Changing from private to public

* The code will be visible to everyone who can visit {% data variables.location.product_location %}.
* Anyone can fork your repository.
* All push rulesets will be disabled.
* Your changes will be published as activity.
* Actions history and logs will be visible to everyone.
* Stars and watchers for this repository will be erased.

### Changing from private to internal

* All members of the enterprise will be given read access.
* Outside collaborators can no longer be added to forks unless they're added to the root.
* Stars and watchers for this repository will be erased.

### Changing from internal to private

* Stars and watchers for this repository will be erased, which will affect repository rankings.
* Custom {% data variables.product.prodname_dependabot %} alert rules will be disabled unless {% data variables.product.prodname_GH_code_security %} is enabled for this repository. Dependency graph and {% data variables.product.prodname_dependabot_alerts %} will remain enabled with permission to perform read-only analysis on this repository.
> * {% data variables.product.prodname_code_scanning_caps %} will become unavailable unless {% data variables.product.prodname_code_security %} is enabled for this repository.
* Current forks will remain public and will be detached from this repository.

### Changing from internal to public

* The code will be visible to everyone who can visit {% data variables.location.product_location %}.
* Anyone can fork your repository.
* All push rulesets will be disabled.
* Your changes will be published as activity.
* Actions history and logs will be visible to everyone.
* Stars and watchers for this repository will be erased.

### Changing from public to internal

* All members of the enterprise will be given read access.
* Outside collaborators can no longer be added to forks unless they're added to the root.
* Stars and watchers for this repository will be erased.

## Changing a repository's visibility

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
1. In the "Danger Zone" section, to the right of to "Change repository visibility", click **Change visibility**.
1. Select a visibility.
1. Click to confirm that you are changing the visibility of the correct repository.
1. Click **I have read and understand these effects**.
1. Click **Make this repository public** or **Make this repository private**.

## Further reading

* [AUTOTITLE](/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility)

---

## Included files

### `data/reusables/advanced-security/more-info-ghas.md`

````markdown
For more information, see [AUTOTITLE](/get-started/learning-about-github/about-github-advanced-security).
````

### `data/reusables/repositories/navigate-to-repo.md`

````markdown
1. On {% data variables.product.prodname_dotcom %}, navigate to the main page of the repository.
````

### `data/reusables/repositories/sidebar-settings.md`

````markdown
1. Under your repository name, click **{% octicon "gear" aria-hidden="true" aria-label="gear" %} Settings**. If you cannot see the "Settings" tab, select the **{% octicon "kebab-horizontal" aria-label="More" %}** dropdown menu, then click **Settings**.

   ![Screenshot of a repository header showing the tabs. The "Settings" tab is highlighted by a dark orange outline.](assets/repo-actions-settings.png)
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.enterprise.prodname_emu_enterprise %}` | enterprise with managed users |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.contact.contact_ent_support %}` | [GitHub Enterprise Support](https://support.github.com) |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_free_user %}` | GitHub Free |
| `{% data variables.product.prodname_pages %}` | GitHub Pages |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_archive %}` | GitHub Archive Program |
| `{% data variables.product.prodname_GHAS %}` | GitHub Advanced Security |
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_GH_code_security %}` | GitHub Code Security |
| `{% data variables.product.prodname_GH_secret_protection %}` | GitHub Secret Protection |
| `{% data variables.product.prodname_learning %}` | GitHub Skills |
| `{% data variables.product.prodname_learning_link %}` | https://skills.github.com/ |
| `{% data variables.product.prodname_dependabot %}` | Dependabot |
| `{% data variables.product.prodname_dependabot_alerts %}` | Dependabot alerts |
| `{% data variables.product.prodname_code_scanning_caps %}` | Code scanning |
| `{% data variables.product.prodname_code_security %}` | Code Security |
