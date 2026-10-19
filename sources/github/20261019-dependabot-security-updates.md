# Source Snapshot: Dependabot security updates

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/code-security/concepts/supply-chain-security/dependabot-security-updates
- **Upstream file:** [`github/docs` → `content/code-security/concepts/supply-chain-security/dependabot-security-updates.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/code-security/concepts/supply-chain-security/dependabot-security-updates.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/dependabot-security-updates.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/dependabot-security-updates.md); [`data/reusables/dependabot/enterprise-enable-dependabot.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/enterprise-enable-dependabot.md); [`data/reusables/dependabot/dependabot-updates-supported-repos-ecosystems.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-updates-supported-repos-ecosystems.md); [`data/reusables/dependabot/dependabot-updates-signed-commits.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-updates-signed-commits.md); [`data/reusables/dependabot/dependabot-security-updates-disable-for-alert-rules.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-security-updates-disable-for-alert-rules.md); [`data/reusables/security-advisory/link-browsing-advisory-db.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/security-advisory/link-browsing-advisory-db.md); [`data/reusables/dependabot/pull-request-security-vs-version-updates.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/pull-request-security-vs-version-updates.md); [`data/reusables/dependabot/dependabot-updates-prs-and-actions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-updates-prs-and-actions.md); [`data/reusables/dependabot/enabling-actions-for-ghes.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/enabling-actions-for-ghes.md); [`data/reusables/dependabot/dependabot-actions-support.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-actions-support.md); [`data/reusables/dependabot/dependabot-grouped-security-updates-how-enable.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-grouped-security-updates-how-enable.md); [`data/reusables/dependabot/dependabot-grouped-security-updates-order.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-grouped-security-updates-order.md); [`data/reusables/dependabot/automatic-deactivation-link.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/automatic-deactivation-link.md); [`data/features/security-feature-enablement-policies-dependabot.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/security-feature-enablement-policies-dependabot.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Dependabot security updates
intro: '{% data variables.product.prodname_dependabot %} can fix vulnerable dependencies for you by raising pull requests with security updates.'
product: '{% data reusables.gated-features.dependabot-security-updates %}'
shortTitle: Dependabot security updates
redirect_from:
  - /github/managing-security-vulnerabilities/about-github-dependabot-security-updates
  - /github/managing-security-vulnerabilities/about-dependabot-security-updates
  - /code-security/supply-chain-security/about-dependabot-security-updates
  - /code-security/supply-chain-security/managing-vulnerabilities-in-your-projects-dependencies/about-dependabot-security-updates
  - /code-security/dependabot/dependabot-security-updates/about-dependabot-security-updates
  - /code-security/concepts/supply-chain-security/about-dependabot-security-updates
versions:
  fpt: '*'
  ghec: '*'
  ghes: '*'
contentType: concepts
category:
  - Secure your dependencies
---

<!--Marketing-LINK: From /features/security/software-supply-chain page "About Dependabot security updates".-->

{% data reusables.dependabot.enterprise-enable-dependabot %}

## About {% data variables.product.prodname_dependabot_security_updates %}

{% data variables.product.prodname_dependabot_security_updates %} make it easier for you to fix vulnerable dependencies in your repository.

If you enable {% data variables.product.prodname_dependabot_security_updates %}, when a {% data variables.product.prodname_dependabot %} alert is raised for a vulnerable dependency in the dependency graph of your repository, {% data variables.product.prodname_dependabot %} automatically tries to fix it. For more information, see [AUTOTITLE](/code-security/concepts/supply-chain-security/dependabot-alerts) and [AUTOTITLE](/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-security-updates).

You can add a `dependabot.yml` configuration file to your repository to customize {% data variables.product.prodname_dependabot %} behavior, including update schedules, pull request settings, and which dependencies to monitor.  For more information, see [AUTOTITLE](/code-security/concepts/supply-chain-security/about-the-dependabot-yml-file). You then configure options in this file to tell {% data variables.product.prodname_dependabot %} how to secure the dependencies your repository relies on.

{% data reusables.dependabot.dependabot-updates-supported-repos-ecosystems %}



> [!NOTE]
> There is no interaction between the settings specified in the `dependabot.yml` file and {% data variables.product.prodname_dependabot %} security alerts, other than the fact that alerts will be closed when related pull requests generated by {% data variables.product.prodname_dependabot %} for security updates are merged.

{% data reusables.dependabot.dependabot-updates-signed-commits %}

{% data reusables.dependabot.dependabot-security-updates-disable-for-alert-rules %}

{% data variables.product.prodname_dotcom %} may send {% data variables.product.prodname_dependabot_alerts %} to repositories affected by a vulnerability disclosed by a recently published {% data variables.product.prodname_dotcom %} security advisory. {% data reusables.security-advisory.link-browsing-advisory-db %}

{% data variables.product.prodname_dependabot %} checks whether it's possible to upgrade the vulnerable dependency to a fixed version without disrupting the dependency graph for the repository. Then {% data variables.product.prodname_dependabot %} raises a pull request to update the dependency to the minimum version that includes the patch and links the pull request to the {% data variables.product.prodname_dependabot %} alert, or reports an error on the alert. For more information, see [AUTOTITLE](/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-errors).

The {% data variables.product.prodname_dependabot_security_updates %} feature is available for repositories where you have enabled the dependency graph and {% data variables.product.prodname_dependabot_alerts %}. You will see a {% data variables.product.prodname_dependabot %} alert for every vulnerable dependency identified in your full dependency graph. However, security updates are triggered only for dependencies that are specified in a manifest or lock file. For more information, see [AUTOTITLE](/code-security/concepts/supply-chain-security/dependency-graph).

> [!NOTE]
> For npm, {% data variables.product.prodname_dependabot %} will raise a pull request to update an explicitly defined dependency to a secure version, even if it means updating the parent dependency or dependencies, or even removing a sub-dependency that is no longer needed by the parent. For other ecosystems, {% data variables.product.prodname_dependabot %} is unable to update an indirect or transitive dependency if it would also require an update to the parent dependency. For more information, see [AUTOTITLE](/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-errors#updates-dependencies-without-an-alert).

You can enable a related feature, {% data variables.product.prodname_dependabot_version_updates %}, so that {% data variables.product.prodname_dependabot %} raises pull requests to update the manifest to the latest version of the dependency, whenever it detects an outdated dependency. For more information, see [AUTOTITLE](/code-security/concepts/supply-chain-security/dependabot-version-updates).

{% data reusables.dependabot.pull-request-security-vs-version-updates %}

If you enable _{% data variables.product.prodname_dependabot_security_updates %}_, parts of the configuration may also affect pull requests created for _{% data variables.product.prodname_dependabot_version_updates %}_. This is because some configuration settings are common to both types of updates. For more information, see [AUTOTITLE](/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/customizing-dependabot-security-prs).

{% data reusables.dependabot.dependabot-updates-prs-and-actions %}

{% data reusables.dependabot.dependabot-actions-support %}

## About grouped security updates

To further reduce the number of pull requests you may be seeing, you can enable grouped security updates to group sets of dependencies together (per package ecosystem). {% data variables.product.prodname_dependabot %} then raises a single pull request to update as many vulnerable dependencies as possible in the group to secure versions at the same time.

For security updates, {% data variables.product.prodname_dependabot %} will only group dependencies from different directories per ecosystem under certain conditions and configurations. {% data variables.product.prodname_dependabot %} **will not** group dependencies from different package ecosystems together, and it **will not** group security updates with version updates.

{% data reusables.dependabot.dependabot-grouped-security-updates-how-enable %}
{% data reusables.dependabot.dependabot-grouped-security-updates-order %}

 For more information, see [AUTOTITLE](/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-security-updates#grouping-dependabot-security-updates-into-a-single-pull-request).

{% ifversion fpt or ghec %}

## About compatibility scores

{% data variables.product.prodname_dependabot_security_updates %} may include compatibility scores to let you know whether updating a dependency could cause breaking changes to your project. These are calculated from CI tests in other public repositories where the same security update has been generated. An update's compatibility score is the percentage of CI runs that passed when updating between specific versions of the dependency.

{% endif %}

## About automatic deactivation of {% data variables.product.prodname_dependabot_updates %}

{% data reusables.dependabot.automatic-deactivation-link %}

## About notifications for {% data variables.product.prodname_dependabot %} security updates

You can filter your notifications on {% data variables.product.company_short %} to show {% data variables.product.prodname_dependabot %} security updates. For more information, see [AUTOTITLE](/subscriptions-and-notifications/reference/inbox-filters).

---

## Included files

### `data/reusables/gated-features/dependabot-security-updates.md`

````markdown
{% data variables.product.prodname_dependabot_security_updates %} is available for the following repositories:

{% ifversion fpt or ghec %}

* All repositories on {% data variables.product.prodname_dotcom %}

{% else %}

* All repositories on {% data variables.product.prodname_ghe_server %}

{% endif %}
````

### `data/reusables/dependabot/enterprise-enable-dependabot.md`

````markdown
{% ifversion ghes %}

> [!NOTE]
> Your site administrator must set up {% data variables.product.prodname_dependabot_updates %} for {% data variables.location.product_location %} before you can use this feature. For more information, see [AUTOTITLE](/admin/configuring-settings/configuring-github-connect/enabling-dependabot-for-your-enterprise).{% ifversion security-feature-enablement-policies-dependabot %}
>
> You may not be able to enable or disable {% data variables.product.prodname_dependabot_updates %} if an enterprise owner has set a policy at the enterprise level. For more information, see [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-security-and-analysis-for-your-enterprise).
{% endif %}

{% endif %}
````

### `data/reusables/dependabot/dependabot-updates-supported-repos-ecosystems.md`

````markdown
For information on the supported repositories and ecosystems, see [AUTOTITLE](/code-security/reference/supply-chain-security/supported-ecosystems-and-repositories).
````

### `data/reusables/dependabot/dependabot-updates-signed-commits.md`

````markdown
{% data variables.product.prodname_dependabot %} signs its own commits by default, even if commit signing is not a requirement for the repository. For more information about verified commits, see [AUTOTITLE](/authentication/managing-commit-signature-verification/about-commit-signature-verification).
````

### `data/reusables/dependabot/dependabot-security-updates-disable-for-alert-rules.md`

````markdown

> [!NOTE]
> When {% data variables.product.prodname_dependabot_security_updates %} are enabled for a repository, {% data variables.product.prodname_dependabot %} will automatically try to open pull requests to resolve **every** open {% data variables.product.prodname_dependabot %} alert that has an available patch. If you prefer to customize which alerts {% data variables.product.prodname_dependabot %} opens pull requests for, you should leave {% data variables.product.prodname_dependabot_security_updates %} **disabled** and create an auto-triage rule. For more information, see [AUTOTITLE](/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/auto-triage-dependabot-alerts).
````

### `data/reusables/security-advisory/link-browsing-advisory-db.md`

````markdown
For more information, see [AUTOTITLE](/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/browse-advisory-database).
````

### `data/reusables/dependabot/pull-request-security-vs-version-updates.md`

````markdown
When {% data variables.product.prodname_dependabot %} raises pull requests, these pull requests could be for _security_ or _version_ updates:

* _{% data variables.product.prodname_dependabot_security_updates %}_ are automated pull requests that help you update dependencies with known vulnerabilities.
* _{% data variables.product.prodname_dependabot_version_updates %}_ are automated pull requests that keep your dependencies updated, even when they don’t have any vulnerabilities. To check the status of version updates, navigate to the **Insights** tab of your repository, then select **Dependency Graph**, and {% data variables.product.prodname_dependabot %}.
````

### `data/reusables/dependabot/dependabot-updates-prs-and-actions.md`

````markdown
{% ifversion fpt or ghec %}Pull requests opened by {% data variables.product.prodname_dependabot %} can trigger workflows that run actions. For more information, see [AUTOTITLE](/code-security/tutorials/secure-your-dependencies/automate-dependabot-with-actions).{% elsif ghes %} {% data reusables.dependabot.enabling-actions-for-ghes %} {% data variables.product.prodname_actions %} is required for {% data variables.product.prodname_dependabot_version_updates %} and {% data variables.product.prodname_dependabot_security_updates %} to run on {% data variables.product.github %}. For more information, see [AUTOTITLE](/admin/configuring-settings/configuring-github-connect/enabling-dependabot-for-your-enterprise).{% endif %}
````

### `data/reusables/dependabot/enabling-actions-for-ghes.md`

````markdown
Before you enable {% data variables.product.prodname_dependabot_updates %}, you must configure {% data variables.location.product_location %} to use {% data variables.product.prodname_actions %} with self-hosted runners.
````

### `data/reusables/dependabot/dependabot-actions-support.md`

````markdown
{% data variables.product.prodname_dependabot_security_updates %} can fix vulnerable dependencies in {% data variables.product.prodname_actions %}. When security updates are enabled, {% data variables.product.prodname_dependabot %} will automatically raise a pull request to update vulnerable {% data variables.product.prodname_actions %} used in your workflows to the minimum patched version.
````

### `data/reusables/dependabot/dependabot-grouped-security-updates-how-enable.md`

````markdown
You can enable grouped pull requests for {% data variables.product.prodname_dependabot_security_updates %} in one, or both, of the following ways.

* To group as many available security updates together as possible, across directories and per ecosystem, enable grouping in the "{% data variables.product.UI_advanced_security %}" settings for your repository, or in "Global settings" under {% data variables.product.UI_advanced_security %} for your organization.
* For more granular control of grouping, such as grouping by package name, development/production dependencies, SemVer level, or across multiple directories per ecosystem, add configuration options to the `dependabot.yml` configuration file in your repository.
````

### `data/reusables/dependabot/dependabot-grouped-security-updates-order.md`

````markdown
> [!NOTE]
> If you have configured group rules for {% data variables.product.prodname_dependabot_security_updates %} in a `dependabot.yml` file, all available updates will be grouped according to the rules you've specified. {% data variables.product.prodname_dependabot %} will only group across those directories not configured in your `dependabot.yml` if the setting for grouped security updates at the organization or repository level is also enabled.
````

### `data/reusables/dependabot/automatic-deactivation-link.md`

````markdown
When maintainers of a repository stop interacting with {% data variables.product.prodname_dependabot %} pull requests, {% data variables.product.prodname_dependabot %} temporarily pauses its updates and lets you know, see [AUTOTITLE](/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-updates-stopped).
````

### `data/features/security-feature-enablement-policies-dependabot.yml`

````yaml
# Reference: #10253. Related issue: #7661.
# Improvement issue to fix versioning for enforcing a policy for Dependabot.
versions:
  ghec: '*'
  ghes: '>=3.9'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_dependabot %}` | Dependabot |
| `{% data variables.product.prodname_dependabot_security_updates %}` | Dependabot security updates |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_dependabot_alerts %}` | Dependabot alerts |
| `{% data variables.product.prodname_dependabot_version_updates %}` | Dependabot version updates |
| `{% data variables.product.prodname_dependabot_updates %}` | Dependabot updates |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.UI_advanced_security %}` | {% data variables.product.prodname_AS %} |
