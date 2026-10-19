# Source Snapshot: GitHub Advanced Security license billing

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/billing/concepts/product-billing/github-advanced-security
- **Upstream file:** [`github/docs` → `content/billing/concepts/product-billing/github-advanced-security.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/billing/concepts/product-billing/github-advanced-security.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/ghas-billing.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/ghas-billing.md); [`data/reusables/advanced-security/ghas-products-bullets.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/advanced-security/ghas-products-bullets.md); [`data/reusables/advanced-security/control-use-cost-links.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/advanced-security/control-use-cost-links.md); [`data/reusables/billing/actions-usage-delay.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/billing/actions-usage-delay.md); [`data/features/code-security-risk-assessment.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/code-security-risk-assessment.yml); [`data/features/enhanced-billing-platform.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/enhanced-billing-platform.yml); [`data/features/disable-ghas-button.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/disable-ghas-button.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: '{% data variables.product.prodname_GHAS %} license billing'
intro: 'Understand how {% data variables.product.prodname_AS %} licenses{% ifversion fpt or ghec %} and AI-credit usage{% endif %} are billed.'
product: '{% data reusables.gated-features.ghas-billing %}'
redirect_from:
# Article on migrating to two separate SKUs
  - /billing/managing-billing-for-your-products/managing-billing-for-github-advanced-security/migrating-from-ghas-to-cs-and-sp
  - /billing/how-tos/products/migrate-from-ghas
# This article
  - /admin/advanced-security/about-licensing-for-github-advanced-security
  - /billing/managing-licensing-for-github-advanced-security/about-licensing-for-github-advanced-security
  - /github/setting-up-and-managing-billing-and-payments-on-github/about-licensing-for-github-advanced-security
  - /github/setting-up-and-managing-billing-and-payments-on-github/managing-licensing-for-github-advanced-security/about-licensing-for-github-advanced-security
  - /billing/managing-billing-for-github-advanced-security/about-billing-for-github-advanced-security
  - /billing/managing-billing-for-your-products/managing-billing-for-github-advanced-security/about-billing-for-github-advanced-security
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: GitHub Advanced Security
contentType: concepts
category:
  - Understand product costs
---

## Licenses for {% data variables.product.prodname_GHAS %}

The {% data variables.product.prodname_AS %} product has two license SKUs (stock keeping units):

{% data reusables.advanced-security.ghas-products-bullets+ghas %}

For more information, see [feature summary and pricing information](https://github.com/enterprise/advanced-security#pricing) and [AUTOTITLE](/get-started/learning-about-github/about-github-advanced-security).

## How usage of {% data variables.product.prodname_GHAS %} licenses is measured

A subset of {% data variables.product.prodname_AS %} features are available to **all public repositories** on {% data variables.product.prodname_dotcom_the_website %} **free of charge**. If you change the visibility of a public repository to private and don't pay for {% data variables.product.prodname_AS %}, {% data variables.product.prodname_AS %} features will be disabled for that repository.

Use of {% data variables.product.prodname_AS %} features in **all other repositories requires a license**. Your license usage is calculated based on the number of **unique, active committers** to repositories with {% data variables.product.prodname_GH_cs_or_sp %} features enabled. {% data variables.product.prodname_github_app %} bots are ignored. For information about differences between bot and machine accounts, see [AUTOTITLE](/apps/oauth-apps/building-oauth-apps/differences-between-github-apps-and-oauth-apps#machine-vs-bot-accounts).

### Active and unique committers

Each **active committer** to at least one repository with an {% data variables.product.prodname_AS %} feature enabled uses **one license**. A committer is considered active if one of their commits has been pushed to the repository within the last 90 days, regardless of when it was originally authored.

* **Active committers** are committers who contributed to at least one repository  and have a {% data variables.product.prodname_team %} or {% data variables.product.prodname_enterprise %} license with your organization or enterprise. That is, they are also a member, an enterprise-managed user, an external collaborator, or have a pending invitation to join your organization or enterprise.
* **Unique committers** is the number of active committers who contributed only to one repository, or only to repositories in one organization. You can free up this number of licenses by disabling {% data variables.product.prodname_GH_cs_or_sp %} for that repository or organization.

> [!NOTE] When a repository is migrated to {% data variables.product.github %} using {% data variables.product.prodname_importer_proper_name %}, {% data variables.product.prodname_GHAS %} only consumes licenses for commits and pushes made _after_ migration. Historic contributions from _before_ the migration are not considered. For more information, see [AUTOTITLE](/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/about-github-enterprise-importer).

You can see the active and unique committers to an organization on the Global settings page for {% data variables.product.UI_advanced_security %}. Under "{% data variables.product.prodname_secret_protection %} repositories" and "{% data variables.product.prodname_code_security %} repositories", summaries and repository-level details are reported. See [AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/configure-global-settings).

## Free use of {% data variables.product.prodname_GHAS %} features

{% data variables.product.github %} makes some {% data variables.product.prodname_AS %} features available free of charge on {% data variables.product.prodname_dotcom_the_website %}.

* **All public repositories** have access to code scanning, secret scanning, and dependency review.
* **{% data variables.product.prodname_secret_risk_assessment_caps %}** is available for organizations on {% data variables.product.prodname_dotcom_the_website %}. See {% ifversion fpt or ghec %}[AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/viewing-your-security-risk-assessment-reports){% elsif ghes %}[AUTOTITLE](/enterprise-cloud@latest/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/viewing-your-security-risk-assessment-reports) in the {% data variables.product.prodname_ghe_cloud %} documentation{% endif %}.{% ifversion code-security-risk-assessment %}
* **{% data variables.product.prodname_code_security_risk_assessment_caps %}** is available for organizations on  {% data variables.product.prodname_dotcom_the_website %}. See [AUTOTITLE](/code-security/concepts/code-scanning/risk-assessment).{% endif %}

For full details of available features, see [AUTOTITLE](/get-started/learning-about-github/about-github-advanced-security).

You need to **pay** to use {% data variables.product.prodname_AS %} features in **private repositories** on {% data variables.product.prodname_dotcom_the_website %}, and in all repositories hosted by {% data variables.enterprise.data_residency_site %} and {% data variables.product.prodname_ghe_server %}.

{% ifversion fpt or ghec %}

## How AI feature usage is billed

Some {% data variables.product.prodname_AS %} features consume {% data variables.product.prodname_ai_credits_short %} in addition to the active-committer licenses described in this article. AI Scan and agentic autofix consume the **Code Security AI Credits** SKU.

These features consume Code Security AI Credits even when the repository is public and does not require active-committer licenses.

If the account being billed has included {% data variables.product.prodname_ai_credits_short %} from a {% data variables.product.prodname_copilot %} entitlement, eligible usage draws from that allowance first. After the included allowance is exhausted, further usage is metered. If the account doesn't have included {% data variables.product.prodname_ai_credits_short %}, all usage is metered.

For an organization-owned repository, usage is attributed to the account that pays for the organization's usage. This is the standalone organization account or its enterprise account. The included {% data variables.product.prodname_ai_credits_short %} and budgets for that account apply, including for public repositories.

Repositories in the personal namespace of a {% data variables.enterprise.prodname_managed_user %} are not treated as ordinary personal-account repositories for Code Security AI Credits. AI Scan and agentic autofix are not currently available for these repositories and do not consume Code Security AI Credits there. Purchasing {% data variables.product.prodname_code_security %}, having included {% data variables.product.prodname_ai_credits_short %}, or configuring a Code Security AI Credits budget does not make these features available.

This limitation does not affect classic {% data variables.copilot.copilot_autofix_short %}, which is distinct from agentic autofix and does not consume {% data variables.product.prodname_ai_credits_short %}.

Before security administrators enable AI Scan or agentic autofix broadly, billing administrators should review the account's included {% data variables.product.prodname_ai_credits_short %} and set budgets for metered usage. After the included allowance is exhausted, a hard budget can prevent further metered usage. For more information, see [AUTOTITLE](/billing/concepts/budgets-and-alerts).

For information about features that consume Code Security AI Credits, see [AUTOTITLE](/code-security/concepts/code-scanning/ai-powered-security-detections) and [AUTOTITLE](/code-security/concepts/code-scanning/autofix-for-code-scanning).

{% endif %}

## Using more than your planned licenses

Your account may have a limit on the number of licenses you can use. For example, volume billing specifies a set number of licenses.

If your number of unique, active committers exceeds your license limit, features controlled by {% data variables.product.prodname_AS %} licensing continue to work on all repositories where they are already enabled.

However, you will not be able to enable {% data variables.product.prodname_GHAS_cs_or_sp %} on any additional repositories. Any new repositories created in organizations where {% data variables.product.prodname_GHAS_cs_or_sp %} are configured to be enabled automatically will be created with the products disabled.

## Paying for {% data variables.product.prodname_GHAS %} licenses

You pay for additional licenses using the payment method set up for your {% data variables.product.github %} account.{% ifversion fpt or ghec %} See [AUTOTITLE](/billing/how-tos/set-up-payment/manage-payment-info).{% endif %}

There are two different ways to pay for licenses.

* **Metered billing** available for {% data variables.product.prodname_ghe_cloud %} and from {% data variables.product.prodname_ghe_server %} 3.13 onward with {% data variables.product.prodname_github_connect %}

  * Users can enable {% data variables.product.prodname_GH_cs_or_sp %} independently.
  * Monthly bill for the number of licenses used by active committers.
  * No pre-defined license limit.
  * No overage state, you pay only for what you use.
  > [!NOTE]
  > On {% data variables.product.prodname_ghe_server %}, metered use of {% data variables.product.prodname_AS %} products is billed through the linked enterprise account on {% data variables.product.prodname_ghe_cloud %}.

* **Volume/subscription billing** available for {% data variables.product.prodname_enterprise %} plans only

  * Purchase a specific number of {% data variables.product.prodname_GHAS_cs_or_sp %} licenses that last for a defined period, typically at least a year, see {% ifversion fpt or ghec %}[AUTOTITLE](/billing/how-tos/products/buy-advanced-security){% elsif ghes %}[AUTOTITLE](/enterprise-cloud@latest/billing/how-tos/products/buy-advanced-security) in the {% data variables.product.prodname_ghe_cloud %} documentation{% endif %}.
  * If the usage of {% data variables.product.prodname_AS %} by active committers exceeds the number of licenses purchased, you need to purchase additional licenses to cover this overage usage.

To view your current license usage, see [AUTOTITLE](/billing/how-tos/products/view-productlicense-use).

### Understanding usage

Users can contribute to multiple repositories or organizations. Usage is measured across the whole organization or enterprise to ensure that each member uses one license regardless of how many repositories or organizations the user contributes to.

When you enable or disable {% data variables.product.prodname_GH_cs_or_sp %} for one or more repositories, {% data variables.product.github %} displays an overview of how this will change your usage.

* Metered billing, showing an increase or reduction in the number of active committers using licenses.
* Volume/subscription billing, showing the number of licenses used or freed by unique active committers.

### Example showing how the active committer count changes over time

The following example timeline demonstrates how the unique, active committer count for {% data variables.product.prodname_AS %} licenses could change over time in an organization or enterprise. For each month, you will find events, along with the resulting committer count and the effect on usage-based billing.

| Date | Events during the month | Unique, active committers | Effect on usage-based billing |
| :- | :- | -: | :- |
| <span style="white-space: nowrap;">April 15</span> | A member of your enterprise enables {% data variables.product.prodname_GH_cs_and_sp %} for repository **X**. Repository **X** has 50 committers over the past 90 days. | **50** | Billing begins for 50 committers. |
| <span style="white-space: nowrap;">May 1</span> | Developer **A** switches teams and stops committing to repository **X**. Developer **A**'s contributions continue to count for 90 days. | **50** | No immediate change. Developer **A** continues to be billed until their contributions are inactive for 90 days. |
| <span style="white-space: nowrap;">August 1</span> | Developer **A**'s contributions no longer count towards the licenses required, because 90 days have passed. | 50 - 1 =<br>**49** | Developer **A** is removed from the billing count, reducing the billable committers to 49. |
| <span style="white-space: nowrap;">August 15</span> | A member of your enterprise enables {% data variables.product.prodname_GH_cs_and_sp %} for a second repository, repository **Y**. In the last 90 days, a total of 20 developers contributed to that repository. Of those 20 developers, 10 also recently worked on repo **X** and do not require additional licenses. | 49 + 10 =<br>**59** | Billing increases to 59 committers, accounting for the 10 additional unique contributors. |
| <span style="white-space: nowrap;">August 16</span> | A member of your enterprise disables {% data variables.product.prodname_GH_cs_and_sp %} for repository **X**. Of the 49 developers who were working on repository **X**, 10 still also work on repository **Y**, which has a total of 20 developers contributing in the last 90 days. | 49 - 29 =<br>**20** | Billing for repository **X** continues until the end of the monthly billing cycle, but the overall billing count decreases to 20 committers for the next cycle. |

## Managing your budget for {% data variables.product.prodname_AS %}

The options available for managing committers and costs depend on your billing model.

### Metered billing

You can control usage and costs with budgets and alerts. If you use {% data variables.product.prodname_ghe_cloud %}, then you can also use cost centers and policies to control costs.
See {% data reusables.advanced-security.control-use-cost-links %}.

{% ifversion enhanced-billing-platform %}

#### Hard budgets for {% data variables.product.prodname_GHAS %} SKUs

SKU-level budgets for {% data variables.product.prodname_AS %} products ({% data variables.product.prodname_secret_protection %} and {% data variables.product.prodname_code_security %}) support the **Limit usage when budget limit is reached** option. For {% data variables.product.prodname_AS %}, this option prevents new enablement. It does **not** disable {% data variables.product.prodname_AS %} on repositories where it is already active.

When the budget limit is reached:

* Repositories where {% data variables.product.prodname_AS %} is already enabled continue to function normally. Active committers in those repositories are still counted and billed.
* {% data variables.product.prodname_AS %} cannot be enabled on any additional repositories until the budget is increased or a new billing cycle begins.

There are two scenarios where usage may exceed the budget:

* A new committer becomes active in a repository where {% data variables.product.prodname_AS %} is already enabled. You are billed for the additional license cost.
* When you enable {% data variables.product.prodname_AS %} on a repository with more active committers than the remaining budget allows, the enablement succeeds but you are billed for any usage beyond the budget limit.

For more information about budgets, see [AUTOTITLE](/billing/concepts/budgets-and-alerts).

{% endif %}

{% data reusables.billing.actions-usage-delay %}

If your enterprise uses {% data variables.product.prodname_AS %} on both {% data variables.product.prodname_ghe_server %} and {% data variables.product.prodname_ghe_cloud %}, you can ensure users don't consume multiple licenses unnecessarily by synchronizing license usage between environments. See [AUTOTITLE]({% ifversion fpt %}/enterprise-cloud@latest{% endif %}/billing/how-tos/manage-server-licenses/sync-license-usage).

### Volume/subscription billing

Each license specifies a maximum number of accounts that can use {% data variables.product.prodname_AS %}. Each active committer to at least one repository with the product enabled consumes one license. When you remove a user from your {% data variables.enterprise.enterprise_or_org %} account, the user's license is freed within 24 hours.

As soon as you make licenses available, by disabling {% data variables.product.prodname_GHAS_cs_or_sp %} in some repositories, or by increasing your license size, the options for enabling {% data variables.product.prodname_GHAS_cs_and_sp %} will work again as normal.

You can enforce policies to allow or disallow the use of {% data variables.product.prodname_AS %} by organizations owned by your enterprise account. See [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-security-and-analysis-for-your-enterprise).

> [!TIP]
> All standalone instances of {% data variables.product.prodname_ghe_server %} use volume/subscription licenses. Contact [{% data variables.product.github %}'s Sales team](https://enterprise.github.com/contact) if you want to make changes to your license.

{% ifversion disable-ghas-button %}

## Disabling {% data variables.product.prodname_GHAS %} in an enterprise

To disable {% data variables.product.prodname_GHAS %} and prevent accidental re-enablement across your enterprise, enterprise owners can use the **Disable {% data variables.product.prodname_AS %}** option available in the enterprise licensing page. This is particularly useful for metered users who want to ensure {% data variables.product.prodname_GHAS %} is completely disabled and cannot be re-enabled without explicit approval.

The **Disable {% data variables.product.prodname_AS %}** option:
* Disables {% data variables.product.prodname_GHAS %} in all private and internal repositories
* Sets a policy to prevent future paid adoption
* Stops billing for future usage (metered billing only)

See [AUTOTITLE](/billing/how-tos/products/disable-ghas-for-enterprise).

{% endif %}

## Further reading

* [AUTOTITLE](/code-security/tutorials/trialing-github-advanced-security/planning-a-trial-of-ghas)
* [AUTOTITLE](/code-security/concepts/security-at-scale/organization-security)

* [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-security-and-analysis-for-your-enterprise)

---

## Included files

### `data/reusables/gated-features/ghas-billing.md`

````markdown
{% ifversion fpt or ghec %}
Requires {% data variables.product.prodname_team %} or {% data variables.product.prodname_enterprise %}
{% endif %}
````

### `data/reusables/advanced-security/ghas-products-bullets.md`

````markdown
* **{% data variables.product.prodname_GH_secret_protection %}**, which includes features that help you detect and prevent secret leaks, such as {% data variables.product.prodname_secret_scanning %} and push protection.
* **{% data variables.product.prodname_GH_code_security %}**, which includes features that help you find and fix vulnerabilities, like {% data variables.product.prodname_code_scanning %}, premium {% data variables.product.prodname_dependabot %} features, and dependency review.
````

### `data/reusables/advanced-security/control-use-cost-links.md`

````markdown
{% ifversion fpt or ghec %}[AUTOTITLE](/billing/how-tos/set-up-budgets){% ifversion ghec %} and [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-security-and-analysis-for-your-enterprise){% endif %}
{% elsif ghes %}[AUTOTITLE](/enterprise-cloud@latest/billing/how-tos/set-up-budgets) in the {% data variables.product.prodname_ghe_cloud %} docs
{% endif %}
````

### `data/reusables/billing/actions-usage-delay.md`

````markdown
> [!NOTE] When you enable {% data variables.product.prodname_GHAS_cs_or_sp %}, there is a delay of up to two hours before the change is shown in the usage data on the "Billing and licensing" tab.
````

### `data/features/code-security-risk-assessment.yml`

````yaml
# Reference: #19489
# This feature is not yet available for GitHub Enterprise Server.
versions:
  ghec: '*'
  fpt: '*'
````

### `data/features/enhanced-billing-platform.yml`

````yaml
# Versions for which the new billing platform (FKA enhanced billing platform) is available (GitHub Enterprise plan from June 2024 and GitHub Team plan from Nov 2024)
versions:
  ghec: '*'
  fpt: '*'
````

### `data/features/disable-ghas-button.yml`

````yaml
# Reference: #21435
# Disable GHAS button on the Enterprise licensing page [GA]
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>= 3.22'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_GHAS %}` | GitHub Advanced Security |
| `{% data variables.product.prodname_AS %}` | Advanced Security |
| `{% data variables.product.prodname_dotcom_the_website %}` | GitHub.com |
| `{% data variables.product.prodname_GH_cs_or_sp %}` | GitHub Secret Protection or GitHub Code Security |
| `{% data variables.product.prodname_github_app %}` | GitHub App |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_enterprise %}` | GitHub Enterprise |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_importer_proper_name %}` | GitHub Enterprise Importer |
| `{% data variables.product.UI_advanced_security %}` | {% data variables.product.prodname_AS %} |
| `{% data variables.product.prodname_secret_protection %}` | Secret Protection |
| `{% data variables.product.prodname_code_security %}` | Code Security |
| `{% data variables.product.prodname_secret_risk_assessment_caps %}` | Secret risk assessment |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_code_security_risk_assessment_caps %}` | Code security risk assessment |
| `{% data variables.enterprise.data_residency_site %}` | GHE.com |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.prodname_ai_credits_short %}` | AI credits |
| `{% data variables.product.prodname_copilot %}` | GitHub Copilot |
| `{% data variables.enterprise.prodname_managed_user %}` | managed user account |
| `{% data variables.copilot.copilot_autofix_short %}` | Copilot Autofix |
| `{% data variables.product.prodname_GHAS_cs_or_sp %}` | GitHub Secret Protection, GitHub Code Security, or GitHub Advanced Security |
| `{% data variables.product.prodname_github_connect %}` | GitHub Connect |
| `{% data variables.product.prodname_GH_cs_and_sp %}` | GitHub Secret Protection and GitHub Code Security |
| `{% data variables.enterprise.enterprise_or_org %}` | {% ifversion fpt %}organization{% elsif ghec or ghes %}enterprise{% endif %} |
| `{% data variables.product.prodname_GHAS_cs_and_sp %}` | GitHub Secret Protection, GitHub Code Security, and GitHub Advanced Security |
| `{% data variables.product.prodname_GH_secret_protection %}` | GitHub Secret Protection |
| `{% data variables.product.prodname_secret_scanning %}` | secret scanning |
| `{% data variables.product.prodname_GH_code_security %}` | GitHub Code Security |
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_dependabot %}` | Dependabot |
