# Source Snapshot: Dependabot version updates

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/code-security/concepts/supply-chain-security/dependabot-version-updates
- **Upstream file:** [`github/docs` → `content/code-security/concepts/supply-chain-security/dependabot-version-updates.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/code-security/concepts/supply-chain-security/dependabot-version-updates.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/dependabot-version-updates.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/dependabot-version-updates.md); [`data/reusables/dependabot/enterprise-enable-dependabot.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/enterprise-enable-dependabot.md); [`data/reusables/dependabot/pull-request-security-vs-version-updates.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/pull-request-security-vs-version-updates.md); [`data/reusables/dependabot/dependabot-tos.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-tos.md); [`data/reusables/dependabot/dependabot-updates-supported-repos-ecosystems.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/dependabot-updates-supported-repos-ecosystems.md); [`data/reusables/dependabot/default-cooldown-period.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/default-cooldown-period.md); [`data/reusables/dependabot/automatic-deactivation-link.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/dependabot/automatic-deactivation-link.md); [`data/features/dependabot-cooldown-default-days.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/dependabot-cooldown-default-days.yml); [`data/features/actions-workflow-lockfiles.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-workflow-lockfiles.yml); [`data/features/security-feature-enablement-policies-dependabot.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/security-feature-enablement-policies-dependabot.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Dependabot version updates
intro: You can use {% data variables.product.prodname_dependabot %} to keep the packages you use updated to the latest versions.
product: '{% data reusables.gated-features.dependabot-version-updates %}'
redirect_from:
  - /github/administering-a-repository/about-dependabot
  - /github/administering-a-repository/about-github-dependabot
  - /github/administering-a-repository/about-github-dependabot-version-updates
  - /github/administering-a-repository/about-dependabot-version-updates
  - /code-security/supply-chain-security/about-dependabot-version-updates
  - /code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/upgrading-from-dependabotcom-to-github-native-dependabot
  - /code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/about-dependabot-version-updates
  - /code-security/dependabot/dependabot-version-updates/about-dependabot-version-updates
  - /code-security/dependabot/dependabot-version-updates
  - /code-security/supply-chain-security/keeping-your-dependencies-updated-automatically
  - /administering-a-repository/keeping-your-dependencies-updated-automatically
  - /code-security/concepts/supply-chain-security/about-dependabot-version-updates
versions:
  fpt: '*'
  ghec: '*'
  ghes: '*'
shortTitle: Dependabot version updates
contentType: concepts
category:
  - Secure your dependencies
---

{% data reusables.dependabot.enterprise-enable-dependabot %}

## About {% data variables.product.prodname_dependabot_version_updates %}

{% data variables.product.prodname_dependabot %} takes the effort out of maintaining your dependencies. You can use it to ensure that your repository automatically keeps up with the latest releases of the packages and applications it depends on.

{% data reusables.dependabot.pull-request-security-vs-version-updates %}

You enable {% data variables.product.prodname_dependabot_version_updates %} by checking a `dependabot.yml` configuration file into your repository.

{% data reusables.dependabot.dependabot-tos %}

## Updates for packages

The `dependabot.yml` configuration file specifies the location of the manifest, or of other package definition files, stored in your repository. {% data variables.product.prodname_dependabot %} uses this information to check for outdated packages and applications. {% data variables.product.prodname_dependabot %} determines if there is a new version of a dependency by looking at the semantic versioning ([semver](https://semver.org/)) of the dependency to decide whether it should update to that version. {% data reusables.dependabot.dependabot-updates-supported-repos-ecosystems %}

The `dependabot.yml` file can also be configured to tell {% data variables.product.prodname_dependabot %} how to maintain your dependencies. For more information, see [AUTOTITLE](/code-security/concepts/supply-chain-security/about-the-dependabot-yml-file).

For certain package managers, {% data variables.product.prodname_dependabot_version_updates %} also supports vendoring. Vendored (or cached) dependencies are dependencies that are checked in to a specific directory in a repository rather than referenced in a manifest. Vendored dependencies are available at build time even if package servers are unavailable. {% data variables.product.prodname_dependabot_version_updates %} can be configured to check vendored dependencies for new versions and update them if necessary.

When {% data variables.product.prodname_dependabot %} identifies an outdated dependency, it raises a pull request to update the manifest to the latest version of the dependency. For vendored dependencies, {% data variables.product.prodname_dependabot %} raises a pull request to replace the outdated dependency with the new version directly. You check that your tests pass, review the changelog and release notes included in the pull request summary, and then merge it. For more information, see [AUTOTITLE](/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-version-updates).

{% ifversion dependabot-cooldown-default-days %}

{% data reusables.dependabot.default-cooldown-period %} This gives new releases time to stabilize before you receive a pull request. You can customize the cooldown periods, and the dependencies they apply to, with the `cooldown` option. For more information, see [AUTOTITLE](/code-security/reference/supply-chain-security/dependabot-options-reference#cooldown-).

{% endif %}

If you enable _security updates_, {% data variables.product.prodname_dependabot %} also raises pull requests to update vulnerable dependencies. For more information, see [AUTOTITLE](/code-security/concepts/supply-chain-security/dependabot-security-updates).

## Updates for actions

Actions are often updated with bug fixes and new features to make automated processes more reliable, faster, and safer. When you enable {% data variables.product.prodname_dependabot_version_updates %} for {% data variables.product.prodname_actions %}, {% data variables.product.prodname_dependabot %} will help ensure that references to actions in a repository's _workflow.yml_ file and reusable workflows used inside workflows are kept up to date.

For each action in the file, {% data variables.product.prodname_dependabot %} checks the action's reference (typically a version number or commit identifier associated with the action) against the latest version. If a more recent version of the action is available, {% data variables.product.prodname_dependabot %} will send you a pull request that updates the reference in the workflow file to the latest version.

{% data variables.product.prodname_dependabot %} also checks workflow files for uses of reusable workflows, and updates the Git reference for these called reusable workflows.

{% ifversion actions-workflow-lockfiles %}

If a workflow has been onboarded to a workflow dependency lockfile, {% data variables.product.prodname_dependabot %} also regenerates the matching lockfile entry in the same pull request, so the pinned commit in the lockfile always matches the updated reference in the workflow file. This needs no additional configuration. For more information, see [AUTOTITLE](/actions/how-tos/secure-your-work/lock-workflow-dependencies).

{% endif %}

To enable this feature, see [AUTOTITLE](/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/auto-update-actions).

## About automatic deactivation of {% data variables.product.prodname_dependabot_updates %}

{% data reusables.dependabot.automatic-deactivation-link %}

## About notifications for {% data variables.product.prodname_dependabot %} version updates

You can filter your notifications on {% data variables.product.company_short %} to show notifications for pull requests created by {% data variables.product.prodname_dependabot %}. For more information, see [AUTOTITLE](/subscriptions-and-notifications/how-tos/viewing-and-triaging-notifications/managing-notifications-from-your-inbox).

---

## Included files

### `data/reusables/gated-features/dependabot-version-updates.md`

````markdown
{% data variables.product.prodname_dependabot_version_updates %} is available for the following repositories:

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

### `data/reusables/dependabot/pull-request-security-vs-version-updates.md`

````markdown
When {% data variables.product.prodname_dependabot %} raises pull requests, these pull requests could be for _security_ or _version_ updates:

* _{% data variables.product.prodname_dependabot_security_updates %}_ are automated pull requests that help you update dependencies with known vulnerabilities.
* _{% data variables.product.prodname_dependabot_version_updates %}_ are automated pull requests that keep your dependencies updated, even when they don’t have any vulnerabilities. To check the status of version updates, navigate to the **Insights** tab of your repository, then select **Dependency Graph**, and {% data variables.product.prodname_dependabot %}.
````

### `data/reusables/dependabot/dependabot-tos.md`

````markdown
{% ifversion fpt %}
{% data variables.product.prodname_dependabot %} and all related features are covered by [{% data variables.product.prodname_dotcom %}'s Terms of Service](/free-pro-team@latest/site-policy/github-terms/github-terms-of-service).
{% elsif ghec %}
{% data variables.product.prodname_dependabot %} and all related features are covered by your license agreement. For more information, see [{% data variables.product.company_short %} Enterprise Customer Terms](https://github.com/customer-terms).
{% endif %}
````

### `data/reusables/dependabot/dependabot-updates-supported-repos-ecosystems.md`

````markdown
For information on the supported repositories and ecosystems, see [AUTOTITLE](/code-security/reference/supply-chain-security/supported-ecosystems-and-repositories).
````

### `data/reusables/dependabot/default-cooldown-period.md`

````markdown
By default, {% data variables.product.prodname_dependabot %} applies a cooldown period of 3 days to version updates, so a new version is not considered for a version update until 3 days after its release. **This default cooldown does not apply to security updates.**
````

### `data/reusables/dependabot/automatic-deactivation-link.md`

````markdown
When maintainers of a repository stop interacting with {% data variables.product.prodname_dependabot %} pull requests, {% data variables.product.prodname_dependabot %} temporarily pauses its updates and lets you know, see [AUTOTITLE](/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-updates-stopped).
````

### `data/features/dependabot-cooldown-default-days.yml`

````yaml
# Default cooldown period of 3 days applied to Dependabot version updates
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>3.21'
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
| `{% data variables.product.prodname_dependabot_version_updates %}` | Dependabot version updates |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_dependabot_updates %}` | Dependabot updates |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.product.prodname_dependabot_security_updates %}` | Dependabot security updates |
