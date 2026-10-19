# Source Snapshot: Managing GitHub Actions settings for a repository

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository
- **Upstream file:** [`github/docs` → `content/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/actions/enterprise-github-hosted-runners.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/enterprise-github-hosted-runners.md); [`data/reusables/actions/disabling-github-actions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/disabling-github-actions.md); [`data/reusables/actions/enabled-actions-description.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/enabled-actions-description.md); [`data/reusables/actions/disabled-actions-description.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/disabled-actions-description.md); [`data/reusables/repositories/settings-permissions-org-policy-note.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/settings-permissions-org-policy-note.md); [`data/reusables/repositories/navigate-to-repo.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/navigate-to-repo.md); [`data/reusables/repositories/sidebar-settings.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/sidebar-settings.md); [`data/reusables/repositories/settings-sidebar-actions-general.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/settings-sidebar-actions-general.md); [`data/reusables/actions/settings-ui/settings-actions-general.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/settings-ui/settings-actions-general.md); [`data/reusables/actions/actions-use-policy-settings.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/actions-use-policy-settings.md); [`data/reusables/actions/policy-label-for-select-actions-workflows.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/policy-label-for-select-actions-workflows.md); [`data/reusables/actions/allow-specific-actions-intro.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/allow-specific-actions-intro.md); [`data/reusables/actions/lockfile-allowed-actions-sha.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/lockfile-allowed-actions-sha.md); [`data/reusables/actions/action-checkout.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/action-checkout.md); [`data/reusables/actions/workflow-run-approve-public-fork.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflow-run-approve-public-fork.md); [`data/reusables/actions/workflows-from-public-fork-setting.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflows-from-public-fork-setting.md); [`data/reusables/actions/workflow-run-approve-link.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflow-run-approve-link.md); [`data/reusables/actions/private-repository-forks-overview.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/private-repository-forks-overview.md); [`data/reusables/actions/private-repository-forks-options.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/private-repository-forks-options.md); [`data/reusables/actions/private-repository-forks-configure.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/private-repository-forks-configure.md); [`data/reusables/actions/workflow-permissions-intro.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflow-permissions-intro.md); [`data/reusables/actions/workflow-permissions-modifying.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflow-permissions-modifying.md); [`data/reusables/actions/workflows/github-token-access.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflows/github-token-access.md); [`data/reusables/actions/workflow-pr-approval-permissions-intro.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/workflow-pr-approval-permissions-intro.md); [`data/reusables/actions/about-artifact-log-retention.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/about-artifact-log-retention.md); [`data/reusables/actions/checks-and-statuses-retention-scope.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/checks-and-statuses-retention-scope.md); [`data/reusables/actions/change-retention-period-for-artifacts-logs.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/change-retention-period-for-artifacts-logs.md); [`data/reusables/actions/cache-default-size.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/cache-default-size.md); [`data/reusables/actions/cache-eviction-process.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/cache-eviction-process.md); [`data/reusables/actions/change-cache-size-limit.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/change-cache-size-limit.md); [`data/features/actions-workflow-policy.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-workflow-policy.yml); [`data/features/internal-actions.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/internal-actions.yml); [`data/features/actions-blocklist-sha-pinning.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-blocklist-sha-pinning.yml); [`data/features/actions-workflow-lockfiles.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-workflow-lockfiles.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Managing GitHub Actions settings for a repository
intro: You can disable or configure {% data variables.product.prodname_actions %} for a specific repository.
redirect_from:
  - /github/administering-a-repository/configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-repository
  - /github/administering-a-repository/managing-repository-settings/configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-repository
  - /github/administering-a-repository/disabling-or-limiting-github-actions-for-a-repository
  - /github/administering-a-repository/managing-repository-settings/disabling-or-limiting-github-actions-for-a-repository
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Manage GitHub Actions settings
contentType: how-tos
category:
  - Manage access and repository policies
---

{% data reusables.actions.enterprise-github-hosted-runners %}

## About {% data variables.product.prodname_actions %} permissions for your repository

{% data reusables.actions.disabling-github-actions %} For more information about {% data variables.product.prodname_actions %}, see [AUTOTITLE](/actions/how-tos/write-workflows).

You can enable {% data variables.product.prodname_actions %} for your repository. {% data reusables.actions.enabled-actions-description %} You can disable {% data variables.product.prodname_actions %} for your repository altogether. {% data reusables.actions.disabled-actions-description %}

Alternatively, you can enable {% data variables.product.prodname_actions %} in your repository but limit the actions {% ifversion actions-workflow-policy %}and reusable workflows{% endif %} a workflow can run.

## Managing {% data variables.product.prodname_actions %} permissions for your repository

You can disable {% data variables.product.prodname_actions %} for a repository, or set a policy that configures which actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} can be used in the repository.

{% data reusables.repositories.settings-permissions-org-policy-note %}

{% ifversion fpt or ghec %}

> [!NOTE]
> If you see **{% data variables.product.prodname_actions %} is currently disabled for this repository** or **{% data variables.product.prodname_actions %} is currently disabled for your account**, the repository or account may be in a separate {% data variables.product.github %}-controlled disabled state, and changing these settings won't restore access.
> Contact {% data variables.contact.github_support %} for review.

{% endif %}

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under "Actions permissions", select an option.

   {% data reusables.actions.actions-use-policy-settings %}
1. Click **Save**.

{% data reusables.actions.allow-specific-actions-intro %}

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under "Actions permissions", select {% data reusables.actions.policy-label-for-select-actions-workflows %} and add your required actions to the list.
1. Click **Save**.

{% ifversion fpt or ghec %}

## Controlling changes from forks to workflows in public repositories

{% data reusables.actions.workflow-run-approve-public-fork %}

You can configure this behavior for a repository using the procedure below. Modifying this setting overrides the configuration set at the organization or enterprise level.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
{% data reusables.actions.workflows-from-public-fork-setting %}

{% data reusables.actions.workflow-run-approve-link %}
{% endif %}

## Enabling workflows for forks of private repositories

{% data reusables.actions.private-repository-forks-overview %}

If a policy is disabled for an {% ifversion ghec or ghes %}enterprise or{% endif %} organization, it cannot be enabled for a repository.

{% data reusables.actions.private-repository-forks-options %}

### Configuring the fork policy for a private repository

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
{% data reusables.actions.private-repository-forks-configure %}

## Setting the permissions of the `GITHUB_TOKEN` for your repository

{% data reusables.actions.workflow-permissions-intro %}

The default permissions can also be configured in the organization settings. If your repository belongs to an organization and a more restrictive default has been selected in the organization settings, the same option is selected in your repository settings and the permissive option is disabled.

{% data reusables.actions.workflow-permissions-modifying %}

### Configuring the default `GITHUB_TOKEN` permissions

By default, when you create a new repository in your personal account, `GITHUB_TOKEN` only has read access for the `contents` and `packages` scopes. If you create a new repository in an organization, the setting is inherited from what is configured in the organization settings.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
{% data reusables.actions.workflows.github-token-access %}
1. Click **Save** to apply the settings.

### Preventing {% data variables.product.prodname_actions %} from creating or approving pull requests

{% data reusables.actions.workflow-pr-approval-permissions-intro %}

By default, when you create a new repository in your personal account, workflows are not allowed to create or approve pull requests. If you create a new repository in an organization, the setting is inherited from what is configured in the organization settings.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under "Workflow permissions", use the **Allow GitHub Actions to create and approve pull requests** setting to configure whether `GITHUB_TOKEN` can create and approve pull requests.
1. Click **Save** to apply the settings.

{% ifversion ghes or ghec %}

## Allowing access to components in an internal repository

{% ifversion internal-actions %}Actions and reusable workflows in your internal repositories can be shared with internal and private repositories in the same organization or enterprise.{% else %}Members of your enterprise can use internal repositories to work on projects without sharing information publicly.{% endif %} For information about internal repositories, see [AUTOTITLE](/repositories/creating-and-managing-repositories/about-repositories#about-internal-repositories).

You can use the steps below to configure whether {% ifversion internal-actions %}actions and {% endif %}reusable workflows in an internal repository can be accessed from outside the repository.{% ifversion internal-actions %} For more information, see [AUTOTITLE](/actions/how-tos/reuse-automations/share-with-your-enterprise). Alternatively, you can use the REST API to set, or get details of the level of access. For more information, see [AUTOTITLE](/rest/actions/permissions#get-the-level-of-access-for-workflows-outside-of-the-repository) and [AUTOTITLE](/rest/actions/permissions#set-the-level-of-access-for-workflows-outside-of-the-repository).{% endif %}

1. On {% data variables.product.prodname_dotcom %}, navigate to the main page of the internal repository.
1. Under your repository name, click **{% octicon "gear" aria-hidden="true" aria-label="gear" %} Settings**.
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under **Access**, choose one of the access settings:

   * **Not accessible** - Workflows in other repositories cannot access this repository.
   * **Accessible from repositories in the 'ORGANIZATION NAME' organization** - Workflows in other repositories that are part of the 'ORGANIZATION NAME' organization can access the actions and reusable workflows in this repository. Access is allowed only from private or internal repositories.
   * **Accessible from repositories in the 'ENTERPRISE NAME' enterprise** - Workflows in other repositories that are part of the 'ENTERPRISE NAME' enterprise can access the actions and reusable workflows in this repository. Access is allowed only from private or internal repositories.
1. Click **Save** to apply the settings.
{% endif %}

## Allowing access to components in a private repository

Actions and reusable workflows in your private repositories can be shared with other private repositories {% ifversion fpt %}owned by the same user or organization{% else %}in the same organization or enterprise{% endif %}. For information about private repositories, see [AUTOTITLE](/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility).

You can use the steps below to configure whether actions and reusable workflows in a private repository can be accessed from outside the repository. For more information, see {% ifversion fpt %}[AUTOTITLE](/actions/how-tos/reuse-automations/share-across-private-repositories) and [AUTOTITLE](/actions/how-tos/reuse-automations/share-with-your-organization).{% else %}[AUTOTITLE](/actions/how-tos/reuse-automations/share-with-your-enterprise).{% endif %} Alternatively, you can use the REST API to set, or get details of the level of access. For more information, see [AUTOTITLE](/rest/actions/permissions#get-the-level-of-access-for-workflows-outside-of-the-repository) and [AUTOTITLE](/rest/actions/permissions#set-the-level-of-access-for-workflows-outside-of-the-repository).

{% ifversion fpt %}

### Managing access for a private repository

1. On {% data variables.product.prodname_dotcom %}, navigate to the main page of the private repository.
1. Under your repository name, click **{% octicon "gear" aria-hidden="true" aria-label="gear" %} Settings**.
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under **Access**, choose one of the access settings:

   * **Not accessible** - Workflows in other repositories cannot access this repository.
   * **Accessible from repositories owned by 'USER NAME' user** - Workflows in other repositories that are owned by the same user can access the actions and reusable workflows in this repository. Access is allowed only from private repositories.
1. Click **Save** to apply the settings.

{% endif %}

{% ifversion fpt %}

### Managing access for a private repository in an organization

1. On {% data variables.product.prodname_dotcom %}, navigate to the main page of the private repository.
1. Under your repository name, click **{% octicon "gear" aria-hidden="true" aria-label="gear" %} Settings**.
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under **Access**, choose one of the access settings:

   * **Not accessible** - Workflows in other repositories cannot access this repository.
   * **Accessible from repositories in the 'ORGANIZATION NAME' organization** - Workflows in other repositories that are part of the 'ORGANIZATION NAME' organization can access the actions and reusable workflows in this repository. Access is allowed only from private repositories.
1. Click **Save** to apply the settings.

{% endif %}

{% ifversion fpt %}{% else %}

1. On {% data variables.product.prodname_dotcom %}, navigate to the main page of the private repository.
1. Under your repository name, click **{% octicon "gear" aria-hidden="true" aria-label="gear" %} Settings**.
{% data reusables.repositories.settings-sidebar-actions-general %}
1. Under **Access**, choose one of the access settings:
   * **Not accessible** - Workflows in other repositories cannot access this repository.
   * **Accessible from repositories in the 'ORGANIZATION NAME' organization** - Workflows in other repositories that are part of the 'ORGANIZATION NAME' organization can access the actions and reusable workflows in this repository. Access is allowed only from private repositories.
   * **Accessible from repositories in the 'ENTERPRISE NAME' enterprise** - Workflows in other repositories that are part of the 'ENTERPRISE NAME' enterprise can access the actions and reusable workflows in this repository. Access is allowed only from private repositories.
1. Click **Save** to apply the settings.
{% endif %}

{% ifversion fpt or ghec %}

## Configuring cache settings for your repository

You can configure cache retention and size settings for your repository. This feature is opt-in and available to users with a payment method on file, {% data variables.product.prodname_pro %}, {% data variables.product.prodname_team %}, or {% data variables.product.prodname_ghe_cloud %} plans.

If your repository is owned by an organization that has configured cache settings, you can configure limits up to the maximum set by the organization. If your repository is user-owned, you can configure up to the global maximums.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}

1. In the "Cache settings" section, configure the following settings:
   * **Cache retention**: The number of days to retain caches before automatic deletion. The default is 7 days. You can configure up to 90 days for public repositories or 365 days for private and internal repositories (or up to the limit set by your organization).
   * **Cache size eviction limit**: The maximum total size of all caches in your repository. The default is 10 GB. You can configure up to 10,000 GB per repository (or up to the limit set by your organization). When this limit is exceeded, older caches will be evicted to make room for new caches.
1. Click **Save** to apply the settings.

For more information about cache eviction, see [AUTOTITLE](/actions/reference/workflows-and-actions/dependency-caching#usage-limits-and-eviction-policy).

{% endif %}

<!-- Anchor to maintain the existing "#configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-repository" link from other articles. -->
<a name="configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-repository"></a>
## Configuring the retention period for checks, workflow runs, commit statuses, artifacts, and logs in your repository

You can configure the retention period for checks, workflow runs, commit statuses, artifacts, and logs in your repository.

{% data reusables.actions.about-artifact-log-retention %}

You can also define a custom retention period for a specific artifact created by a workflow. For more information, see [AUTOTITLE](/actions/how-tos/manage-workflow-runs/remove-workflow-artifacts#setting-the-retention-period-for-an-artifact).

## Setting the check, workflow run, status, artifact and log retention period for a repository

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
{% data reusables.actions.change-retention-period-for-artifacts-logs %}

{% ifversion ghes %}

## Configuring cache storage for a repository

{% data reusables.actions.cache-default-size %} However, these default sizes might be different if an enterprise owner has changed them. {% data reusables.actions.cache-eviction-process %}

You can set a total cache storage size for your repository up to the maximum size allowed by the organization or enterprise policy settings.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.repositories.settings-sidebar-actions-general %}
{% data reusables.actions.change-cache-size-limit %}

{% endif %}

---

## Included files

### `data/reusables/actions/enterprise-github-hosted-runners.md`

````markdown
{% ifversion ghes %}

> [!NOTE]
> {% data variables.product.prodname_ghe_server %} users should use self-hosted runners. {% data variables.product.prodname_dotcom %}-hosted runners are **not** supported.

{% endif %}
````

### `data/reusables/actions/disabling-github-actions.md`

````markdown
By default, {% ifversion ghes %}after {% data variables.product.prodname_actions %} is enabled on {% data variables.product.prodname_ghe_server %}, it{% elsif fpt or ghec %}{% data variables.product.prodname_actions %}{% endif %} is enabled on all repositories and organizations. You can choose to disable {% data variables.product.prodname_actions %} or limit it to actions {% ifversion actions-workflow-policy %}and reusable workflows{% endif %} in your {% ifversion ghec or ghes %}enterprise{% else %}organization{% endif %}.
````

### `data/reusables/actions/enabled-actions-description.md`

````markdown
When you enable {% data variables.product.prodname_actions %}, workflows are able to run actions {% ifversion actions-workflow-policy %}and reusable workflows{% endif %} located within your repository and any other{% ifversion fpt %} public{% elsif ghec or ghes %} public or internal{% endif %} repository.
````

### `data/reusables/actions/disabled-actions-description.md`

````markdown
When you disable {% data variables.product.prodname_actions %}, no workflows run in your repository.
````

### `data/reusables/repositories/settings-permissions-org-policy-note.md`

````markdown
> [!NOTE]
> You might not be able to manage these settings if your organization has an overriding policy or is managed by an enterprise that has overriding policy. For more information, see [AUTOTITLE](/organizations/managing-organization-settings/disabling-or-limiting-github-actions-for-your-organization) or [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-github-actions-in-your-enterprise).
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

### `data/reusables/repositories/settings-sidebar-actions-general.md`

````markdown
{% data reusables.actions.settings-ui.settings-actions-general %}
````

### `data/reusables/actions/settings-ui/settings-actions-general.md`

````markdown
{% comment %}This reusable is only to be used in other repo/org/enterprise setting reusables.{%- endcomment -%}
1. In the left sidebar, click **{% octicon "play" aria-hidden="true" aria-label="play" %} Actions**, then click **General**.
````

### `data/reusables/actions/actions-use-policy-settings.md`

````markdown
If you choose {% data reusables.actions.policy-label-for-select-actions-workflows %}, actions {% ifversion actions-workflow-policy %}and reusable workflows{% endif %} within your {% ifversion ghec or ghes %}enterprise{% else %}organization{% endif %} are allowed, and there are additional options for allowing other specific actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %}. For more information, see [Allowing select actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} to run](#allowing-select-actions{% ifversion actions-workflow-policy %}-and-reusable-workflows{% endif %}-to-run).

{% ifversion ghec or fpt %}When you allow actions{% ifversion actions-workflow-policy %} and reusable workflows from only in{% else %} local to{% endif %} your {% ifversion ghec or ghes %}enterprise{% else %}organization{% endif %}, the policy blocks all access to actions authored by {% data variables.product.prodname_dotcom %}. For example, the [`actions/checkout`](https://github.com/actions/checkout) action would not be accessible.{% endif %}

{% ifversion actions-blocklist-sha-pinning %}
When you enable **Require actions to be pinned to a full-length commit SHA**, all actions must be pinned to a full-length commit SHA to be used. This includes actions from your {% ifversion ghec or ghes %}enterprise{% else %}organization{% endif %} and actions authored by {% data variables.product.github %}. {% ifversion actions-workflow-policy %}Reusable workflows can still be referenced by tag.{% endif %} For more information, see [AUTOTITLE](/actions/reference/security/secure-use#using-third-party-actions).
{% endif %}
````

### `data/reusables/actions/policy-label-for-select-actions-workflows.md`

````markdown
{% ifversion actions-workflow-policy %}{% ifversion ghec or ghes %}**Allow enterprise, and select non-enterprise, actions and reusable workflows**{% else %}**Allow _OWNER_, and select non-_OWNER_, actions and reusable workflows**{% endif %}{% else %}**Allow select actions**{% endif %}
````

### `data/reusables/actions/allow-specific-actions-intro.md`

````markdown
<span name="allowing-select-actions-to-run"></span>
<span name="allowing-specific-actions-to-run"></span>

### Allowing select actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} to run

When you choose {% data reusables.actions.policy-label-for-select-actions-workflows %}, local actions (`./` and `$/`){% ifversion actions-workflow-policy %} and reusable workflows{% endif %} are allowed, and there are additional options for allowing other specific actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %}:

{% data reusables.repositories.settings-permissions-org-policy-note %}

* **Allow actions created by {% data variables.product.prodname_dotcom %}:** You can allow all actions created by {% data variables.product.prodname_dotcom %} to be used by workflows. Actions created by {% data variables.product.prodname_dotcom %} are located in the `actions` and `github` organizations. For more information, see the [`actions`](https://github.com/actions) and [`github`](https://github.com/github) organizations.
* **Allow Marketplace actions by verified creators:** {% ifversion ghes %}This option is available if you have {% data variables.product.prodname_github_connect %} enabled and configured with {% data variables.product.prodname_actions %}. For more information, see [AUTOTITLE](/admin/managing-github-actions-for-your-enterprise/managing-access-to-actions-from-githubcom/enabling-automatic-access-to-githubcom-actions-using-github-connect).{% endif %} You can allow all {% data variables.product.prodname_marketplace %} actions created by verified creators to be used by workflows. When GitHub has verified the creator of the action as a partner organization, the {% octicon "verified" aria-label="The verified badge" %} badge is displayed next to the action in {% data variables.product.prodname_marketplace %}.
* **Allow{% ifversion actions-blocklist-sha-pinning %} or block{% endif %} specified actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %}:** You can restrict workflows to use actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} in specific organizations and repositories. Specified actions cannot be set to more than 1000.

  To restrict access to specific tags or commit SHAs of an action{% ifversion actions-workflow-policy %} or reusable workflow{% endif %}, use the same syntax used in the workflow to select the action{% ifversion actions-workflow-policy %} or reusable workflow{% endif %}.

  * For an action, the syntax is `OWNER/REPOSITORY@TAG-OR-SHA`. For example, use `actions/javascript-action@v1.0.1` to select a tag or `actions/javascript-action@a824008085750b8e136effc585c3cd6082bd575f` to select a SHA. For more information, see [AUTOTITLE](/actions/how-tos/write-workflows/choose-what-workflows-do/find-and-customize-actions#using-release-management-for-your-custom-actions).
  {%- ifversion actions-workflow-policy %}
  * For a reusable workflow, the syntax is `OWNER/REPOSITORY/PATH/FILENAME@TAG-OR-SHA`. For example, `octo-org/another-repo/.github/workflows/workflow.yml@v1`. For more information, see [AUTOTITLE](/actions/how-tos/reuse-automations/reuse-workflows#calling-a-reusable-workflow).
  {%- endif %}

  You can use the `*` wildcard character to match patterns. For example, to allow all actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} in organizations that start with `space-org`, you can specify `space-org*/*`. To allow all actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} in repositories that start with octocat, you can use `*/octocat**@*`. For more information about using the `*` wildcard, see [AUTOTITLE](/actions/reference/workflows-and-actions/workflow-syntax#filter-pattern-cheat-sheet).

  Use `,` to separate patterns. For example, to allow all actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} from the `octocat` and `octokit` organizations, you can specify `octocat/*, octokit/*`.

  {% ifversion actions-blocklist-sha-pinning %}
  Use the `!` prefix to block patterns. For example, to allow all actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} from the `space-org` organization, but block a specific action like `space-org/action`, you can specify `space-org/*, !space-org/action@*`. By default, only actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} specified in the list will be allowed. To allow all actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} while also blocking specific actions, you can specify `*, !space-org/action@*`.
  {% endif %}

{% data reusables.actions.lockfile-allowed-actions-sha %}

This procedure demonstrates how to add specific actions{% ifversion actions-workflow-policy %} and reusable workflows{% endif %} to the list.
````

### `data/reusables/actions/lockfile-allowed-actions-sha.md`

````markdown
{% ifversion actions-workflow-lockfiles %}

> [!NOTE]
> For workflows covered by a dependency lockfile, this policy checks each locked dependency by its commit SHA instead of the tag or branch in the workflow file. Tags and branches are mutable, so they can't identify the code that runs. The locked SHA can. This has two effects:
>
> * Allowlist entries pinned to a tag or branch, such as `{% data reusables.actions.action-checkout %}`, don't match, even when the workflow uses `{% data reusables.actions.action-checkout %}`. A locked SHA can't be reliably matched back to a tag, because the tag may have moved since you locked it, and a tag's history includes every earlier release. To allow a locked dependency, use a wildcard such as `actions/checkout@*` or `actions/*`, or the full commit SHA.
> * Locked dependencies satisfy **Require actions to be pinned to a full-length commit SHA** without changes to the workflow file. Dependencies that aren't in the lockfile still need a full-length SHA.
>
> For more information, see [AUTOTITLE](/actions/concepts/security/workflow-dependency-lockfiles).

{% endif %}
````

### `data/reusables/actions/action-checkout.md`

````markdown
actions/checkout@v6
````

### `data/reusables/actions/workflow-run-approve-public-fork.md`

````markdown
Anyone can fork a public repository, and then submit a pull request that proposes changes to the repository's {% data variables.product.prodname_actions %} workflows. Although workflows from forks do not have access to sensitive data such as secrets, they can be an annoyance for maintainers if they are modified for abusive purposes.

To help prevent this, workflows on pull requests to public repositories from some outside contributors will not run automatically, and might need to be approved first. Depending on the "Approval for running fork pull request workflows from contributors" setting, workflows on pull requests to public repositories will not run automatically and may need approval if:

* The pull request is **created by** a user that requires approvals based on the selected policy.
* The pull request event is **triggered by** a user that requires approvals based on the selected policy.

By default, all first-time contributors require approval to run workflows.

Workflows triggered by `pull_request_target` events are run in the context of the base branch. Since the base branch is considered trusted, workflows triggered by these events will always run, regardless of approval settings. For more information about the `pull_request_target` event, see [AUTOTITLE](/actions/reference/workflows-and-actions/events-that-trigger-workflows#pull_request_target).

> [!WARNING] These workflow approval policies are intended to restrict the set of users that can execute workflows in {% data variables.product.prodname_actions %} runners that could lead to unexpected resource and compute consumption when using {% data variables.product.prodname_dotcom %}-hosted runners. If you are using self-hosted runners, potentially malicious user-controlled workflow code will execute automatically if the user is allowed to bypass approval in the set approval policy or if the pull request is approved. You must consider the risk of executing this code in your infrastructure and should review and follow the self-hosted runner security recommendations regardless of the approval settings utilized. See [AUTOTITLE](/actions/reference/security/secure-use#hardening-for-self-hosted-runners).
````

### `data/reusables/actions/workflows-from-public-fork-setting.md`

````markdown
1. Under **Approval for running fork pull request workflows from contributors**, choose which subset of users will require approval before running workflows on their pull requests. Both the pull request author and the actor of the pull request event triggering the workflow will be checked to determine if approval is required. If approval is required, a user with write access to the repository must approve the pull request workflow to be run. See [AUTOTITLE](/actions/how-tos/manage-workflow-runs/approve-runs-from-forks).

   >[!WARNING] When requiring approvals only for first-time contributors (the first two settings), a user that has had any commit or pull request merged into the repository will not require approval. A malicious user could meet this requirement by getting a simple typo or other innocuous change accepted by a maintainer, either as part of a pull request they have authored or as part of another user's pull request.

   * **Require approval for first-time contributors who are new to {% data variables.product.prodname_dotcom %}**. Only users who are both new on {% data variables.product.prodname_dotcom %} and who have never had a commit or pull request merged into this repository will require approval to run workflows.  
   * **Require approval for first-time contributors**. Only users who have never had a commit or pull request merged into this repository will require approval to run workflows.
   * **Require approval for all external contributors** All users that are not a member or owner of this repository and not a member of the organization will require approval to run workflows.

1. Click **Save** to apply the settings.
````

### `data/reusables/actions/workflow-run-approve-link.md`

````markdown
For more information about approving workflow runs that this policy applies to, see [AUTOTITLE](/actions/how-tos/manage-workflow-runs/approve-runs-from-forks).
````

### `data/reusables/actions/private-repository-forks-overview.md`

````markdown
If you rely on using forks of your private repositories, you can configure policies that control how users can run workflows on `pull_request` events. {% ifversion fpt %}Available to private repositories only, you can configure these policy settings for organizations or repositories.{% else %}Available to private and internal repositories only, you can configure these policy settings for {% ifversion ghec %}enterprises{% else %}your enterprise{% endif %}, organizations, or repositories.{% endif %}
````

### `data/reusables/actions/private-repository-forks-options.md`

````markdown
* **Run workflows from fork pull requests** - Allows users to run workflows from fork pull requests, using a `GITHUB_TOKEN` with read-only permission, and with no access to secrets.
* **Send write tokens to workflows from pull requests** - Allows pull requests from forks to use a `GITHUB_TOKEN` with write permission.
* **Send secrets to workflows from pull requests** - Makes all secrets available to the pull request.
* **Require approval for fork pull request workflows** - Workflow runs on pull requests from collaborators without write permission will require approval from someone with write permission before they will run.
````

### `data/reusables/actions/private-repository-forks-configure.md`

````markdown
1. Under **Fork pull request workflows**, select your options.
1. Click **Save** to apply the settings.
````

### `data/reusables/actions/workflow-permissions-intro.md`

````markdown
You can set the default permissions granted to the `GITHUB_TOKEN`. For more information about the `GITHUB_TOKEN`, see [AUTOTITLE](/actions/tutorials/authenticate-with-github_token). You can choose a restricted set of permissions as the default, or apply permissive settings.
````

### `data/reusables/actions/workflow-permissions-modifying.md`

````markdown
Anyone with write access to a repository can modify the permissions granted to the `GITHUB_TOKEN`, adding or removing access as required, by editing the `permissions` key in the workflow file. For more information, see [`permissions`](/actions/reference/workflows-and-actions/workflow-syntax#permissions).
````

### `data/reusables/actions/workflows/github-token-access.md`

````markdown
1. Under "Workflow permissions", choose whether you want the `GITHUB_TOKEN` to have read and write access for all permissions (the permissive setting), or just read access for the `contents` and `packages` permissions (the restricted setting).
````

### `data/reusables/actions/workflow-pr-approval-permissions-intro.md`

````markdown
You can choose to allow or prevent {% data variables.product.prodname_actions %} workflows from creating or approving pull requests.
````

### `data/reusables/actions/about-artifact-log-retention.md`

````markdown
By default, checks, workflow runs, commit statuses, and the artifacts and log files generated by workflows are retained for 90 days before they are automatically deleted.

{% ifversion fpt or ghec %}

> [!IMPORTANT]
> Starting October 1, 2026, these policies will apply to checks, workflow runs, and commit statuses in addition to artifacts and logs. Until then, checks, workflow runs, and commit statuses are retained for 400+ days regardless of your configured retention period. Make sure to review your retention setting and make any adjustments before October 1. For more information, see [the {% data variables.product.company_short %} changelog](https://github.blog/changelog/2026-07-17-actions-retention-will-cover-checks-workflow-runs-and-statuses/).

{% endif %}

{% data reusables.actions.checks-and-statuses-retention-scope %}

{% ifversion fpt or ghec %}
You can adjust the retention period, depending on the type of repository:

* For public repositories: you can change this retention period to anywhere between 1 day or 90 days.
* For private{% ifversion ghec %} and internal{% endif %} repositories: you can change this retention period to anywhere between 1 day or 400 days.
{%- else %}
You can change this retention period to anywhere between 1 day or 400 days.
{%- endif %}

When you customize the retention period, it only applies to new checks, workflow runs, commit statuses, artifacts, and log files, and does not retroactively apply to existing objects. For managed repositories and organizations, the maximum retention period cannot exceed the limit set by the managing organization or enterprise.
````

### `data/reusables/actions/checks-and-statuses-retention-scope.md`

````markdown
These retention policies apply to checks data, including check suites and check runs, and to commit statuses, including those created by third-party integrations. The policies are not limited to data created by {% data variables.product.prodname_actions %}.
````

### `data/reusables/actions/change-retention-period-for-artifacts-logs.md`

````markdown
1. {% ifversion ghes %}In the "Check, workflow run, status, artifact, log, and cache settings" section, u{% else %}U{% endif %}nder **Check, workflow run, status, artifact and log retention**, enter a new value.
1. Click **Save** to apply the change.
````

### `data/reusables/actions/cache-default-size.md`

````markdown
By default, the total cache storage that {% data variables.product.prodname_actions %} uses on the external storage for {% data variables.product.github %} is limited to a maximum of 10 GB per repository, and the maximum allowed size that can be set for a repository is 25 GB.
````

### `data/reusables/actions/cache-eviction-process.md`

````markdown
If you exceed the limit, {% data variables.product.prodname_dotcom %} will save the new cache but will begin evicting caches until the total size is less than the repository limit.
````

### `data/reusables/actions/change-cache-size-limit.md`

````markdown
1. Under **Cache size limit**, enter a new value.
1. Click **Save** to apply the change.
````

### `data/features/actions-workflow-policy.yml`

````yaml
# Reference: #6478.
# Versioning for enterprise/org/repo policy settings for reusable workflow use.
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/internal-actions.yml`

````yaml
versions:
  ghec: '*'
  ghes: '>=3.5'
````

### `data/features/actions-blocklist-sha-pinning.yml`

````yaml
# Versioning for repo/org/enterprise policy settings for actions blocklist and SHA pinning policies.
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>=3.19'
````

### `data/features/actions-workflow-lockfiles.yml`

````yaml
# Issue 21194
# Versioning for GitHub Actions workflow dependency lockfiles
# Not currently scheduled for GHES
versions:
  fpt: '*'
  ghec: '*'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.contact.github_support %}` | GitHub Support |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_pro %}` | GitHub Pro |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.prodname_github_connect %}` | GitHub Connect |
| `{% data variables.product.prodname_marketplace %}` | GitHub Marketplace |
| `{% data variables.product.company_short %}` | GitHub |
