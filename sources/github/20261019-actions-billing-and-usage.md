# Source Snapshot: Billing and usage

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/actions/concepts/billing-and-usage
- **Upstream file:** [`github/docs` → `content/actions/concepts/billing-and-usage.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/actions/concepts/billing-and-usage.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/actions/actions-billing.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/actions-billing.md); [`data/reusables/gated-features/more-info.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/more-info.md); [`data/reusables/actions/actions-usage-metrics-not-billing-metrics.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/actions-usage-metrics-not-billing-metrics.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Billing and usage
intro: There are usage limits for {% data variables.product.prodname_actions %} workflows. Usage charges apply to repositories that go beyond the amount of free minutes and storage for a repository.
redirect_from:
  - /actions/getting-started-with-github-actions/usage-and-billing-information-for-github-actions
  - /actions/reference/usage-limits-billing-and-administration
  - /actions/learn-github-actions/usage-limits-billing-and-administration
  - /actions/administering-github-actions/usage-limits-billing-and-administration
  - /actions/concepts/overview/usage-limits-billing-and-administration
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Administer GitHub Actions
contentType: concepts
---

## About billing for {% data variables.product.prodname_actions %}

{% ifversion fpt or ghec %}
{% data reusables.actions.actions-billing %} For more information, see [AUTOTITLE](/billing/concepts/product-billing/github-actions).
{% else %}
{% data variables.product.prodname_actions %} usage is free for {% data variables.product.prodname_ghe_server %} instances that use self-hosted runners. For more information, see [AUTOTITLE](/actions/concepts/runners/self-hosted-runners).
{% endif %}

{% ifversion fpt or ghec %}

## Availability

{% data variables.product.prodname_actions %} is available on all {% data variables.product.prodname_dotcom %} products, but {% data variables.product.prodname_actions %} is not available for private repositories owned by accounts using legacy per-repository plans. {% data reusables.gated-features.more-info %}

{% endif %}

## Usage limits and policy

There are several limits on {% data variables.product.prodname_actions %} usage when using {% data variables.product.prodname_dotcom %}-hosted runners. See [AUTOTITLE](/actions/reference/limits).

In addition to the usage limits, you must ensure that you use {% data variables.product.prodname_actions %} within the [GitHub Terms of Service](/free-pro-team@latest/site-policy/github-terms/github-terms-of-service). For more information on {% data variables.product.prodname_actions %}-specific terms, see the [GitHub Additional Product Terms](/free-pro-team@latest/site-policy/github-terms/github-terms-for-additional-products-and-features#actions).

{% ifversion fpt or ghec %}

## {% data variables.product.prodname_actions %} usage metrics

Organization owners and users with the "View organization Actions metrics" permission can view {% data variables.product.prodname_actions %} usage metrics for their organization. These metrics can help you understand how and where your Actions minutes are being used. For more information, see [AUTOTITLE](/enterprise-cloud@latest/organizations/collaborating-with-groups-in-organizations/viewing-github-actions-metrics-for-your-organization).

When you view usage metrics, it is important to remember that {% data reusables.actions.actions-usage-metrics-not-billing-metrics %}

{% endif %}

## Billing for reusable workflows

If you reuse a workflow, billing is always associated with the caller workflow. Assignment of {% data variables.product.prodname_dotcom %}-hosted runners is always evaluated using only the caller's context. The caller cannot use {% data variables.product.prodname_dotcom %}-hosted runners from the called repository.

For more information see, [AUTOTITLE](/actions/how-tos/reuse-automations/reuse-workflows).

## Next steps

You can manage your {% data variables.product.prodname_actions %} usage and retention policies for your repository, organization, or enterprise account. For more information, see:
* [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository)
* [AUTOTITLE](/organizations/managing-organization-settings/configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-organization)
* [AUTOTITLE](/organizations/managing-organization-settings/disabling-or-limiting-github-actions-for-your-organization)
* [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-github-actions-in-your-enterprise)

---

## Included files

### `data/reusables/actions/actions-billing.md`

````markdown
{% data variables.product.prodname_actions %} usage is free for standard {% data variables.product.prodname_dotcom %}-hosted runners in public repositories, and for self-hosted runners. See [AUTOTITLE](/actions/how-tos/write-workflows/choose-where-workflows-run/choose-the-runner-for-a-job#standard-github-hosted-runners-for-public-repositories). For private repositories, each {% data variables.product.prodname_dotcom %} account receives a quota of free minutes and storage for use with {% data variables.product.prodname_dotcom %}-hosted runners, depending on the account's plan. Any usage beyond the included amounts is billed to your account.
````

### `data/reusables/gated-features/more-info.md`

````markdown
See [AUTOTITLE](/get-started/learning-about-github/githubs-plans).
````

### `data/reusables/actions/actions-usage-metrics-not-billing-metrics.md`

````markdown
{% data variables.product.prodname_actions %} usage metrics do not apply minute multipliers to the metrics displayed. While they _can_ help you understand your bill, their primary purpose is to help you understand how and where Actions minutes are being used in your organization.

For more information about minute multipliers, see [AUTOTITLE](/billing/concepts/product-billing/github-actions#baseline-minute-costs).
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
