# Source Snapshot: Code scanning

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/code-security/concepts/code-scanning/code-scanning
- **Upstream file:** [`github/docs` → `content/code-security/concepts/code-scanning/code-scanning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/code-security/concepts/code-scanning/code-scanning.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/code-scanning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/code-scanning.md); [`data/reusables/code-scanning/enterprise-enable-code-scanning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/enterprise-enable-code-scanning.md); [`data/reusables/code-scanning/about-code-scanning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/about-code-scanning.md); [`data/reusables/advanced-security/ghas-trial.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/advanced-security/ghas-trial.md); [`data/reusables/code-scanning/about-codeql-analysis.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/about-codeql-analysis.md); [`data/reusables/code-scanning/interoperable-with-tools-that-output-sarif.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/interoperable-with-tools-that-output-sarif.md); [`data/features/code-scanning-autofix.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/code-scanning-autofix.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Code scanning
shortTitle: Code scanning
intro: You can use {% data variables.product.prodname_code_scanning %} to find security vulnerabilities and errors in the code for your project on {% data variables.product.prodname_dotcom %}.
product: '{% data reusables.gated-features.code-scanning %}'
redirect_from:
  - /github/managing-security-vulnerabilities/about-automated-code-scanning
  - /github/finding-security-vulnerabilities-and-errors-in-your-code/about-code-scanning
  - /code-security/secure-coding/about-code-scanning
  - /code-security/secure-coding/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning
  - /github/finding-security-vulnerabilities-and-errors-in-your-code/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning
  - /code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning
  - /code-security/code-scanning/introduction-to-code-scanning/about-code-scanning
  - /code-security/concepts/code-scanning/about-code-scanning
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
contentType: concepts
category:
  - Find and fix code vulnerabilities
---

{% data reusables.code-scanning.enterprise-enable-code-scanning %}

{% data reusables.code-scanning.about-code-scanning %}

You can use {% data variables.product.prodname_code_scanning %} to find, triage, and prioritize fixes for existing problems in your code. {% data variables.product.prodname_code_scanning_caps %} also prevents developers from introducing new problems. You can schedule scans for specific days and times, or trigger scans when a specific event occurs in the repository, such as a push.

If {% data variables.product.prodname_code_scanning %} finds a potential vulnerability or error in your code, {% data variables.product.prodname_dotcom %} displays an alert in the repository. After you fix the code that triggered the alert, {% data variables.product.prodname_dotcom %} closes the alert. For more information, see [AUTOTITLE](/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/resolve-alerts).

{% ifversion code-scanning-autofix %}

{% data variables.copilot.copilot_autofix %} will suggest fixes for alerts from {% data variables.product.prodname_code_scanning %} analysis, allowing developers to prevent and reduce vulnerabilities with less effort. For more information, see [AUTOTITLE](/code-security/responsible-use/security-and-quality-ai-features).

{% endif %}

To monitor results from {% data variables.product.prodname_code_scanning %} across your repositories or your organization, you can use webhooks and the {% data variables.product.prodname_code_scanning %} API. For information about the webhooks for {% data variables.product.prodname_code_scanning %}, see
[AUTOTITLE](/webhooks/webhook-events-and-payloads#code_scanning_alert). For information about API endpoints, see [AUTOTITLE](/rest/code-scanning/code-scanning).

{% ifversion fpt or ghec %}

{% data variables.product.prodname_code_scanning_caps %} uses {% data variables.product.prodname_actions %}, with each workflow run consuming {% data variables.product.prodname_actions %} minutes. If you want to use {% data variables.product.prodname_code_scanning %} on private repositories, you need a {% data variables.product.prodname_GH_code_security %} license. For more information, see [AUTOTITLE](/billing/concepts/product-billing/github-actions). {% data reusables.advanced-security.ghas-trial %}

If you want to assess your organization's exposure to vulnerabilities before purchasing a license, you can run a free {% data variables.product.prodname_code_security_risk_assessment %}. See [AUTOTITLE](/code-security/concepts/code-scanning/risk-assessment).

{% endif %}

To get started with {% data variables.product.prodname_code_scanning %}, see [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configure-code-scanning).

## About tools for {% data variables.product.prodname_code_scanning %}

You can configure {% data variables.product.prodname_code_scanning %} to use the {% data variables.product.prodname_codeql %} product maintained by {% data variables.product.company_short %} or a third-party {% data variables.product.prodname_code_scanning %} tool.

### About {% data variables.product.prodname_codeql %} analysis

{% data reusables.code-scanning.about-codeql-analysis %} For more information about {% data variables.product.prodname_codeql %}, see [AUTOTITLE](/code-security/concepts/code-scanning/codeql/codeql-code-scanning).

### About third-party {% data variables.product.prodname_code_scanning %} tools

{% data reusables.code-scanning.interoperable-with-tools-that-output-sarif %}

You can run third-party analysis tools within {% data variables.product.github %} using actions or within an external CI system. For more information, see [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configuring-advanced-setup-for-code-scanning#configuring-code-scanning-using-third-party-actions) or [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/integrate-with-existing-tools/upload-sarif-file).

## About the {% data variables.code-scanning.tool_status_page %}

The {% data variables.code-scanning.tool_status_page %} shows useful information about all of your code scanning tools. If code scanning is not working as you'd expect, the {% data variables.code-scanning.tool_status_page %} is a good starting point for debugging problems. For more information, see [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning).

---

## Included files

### `data/reusables/gated-features/code-scanning.md`

````markdown
{% data variables.product.prodname_code_scanning_caps %} is available for the following repository types:

* Public repositories on {% data variables.product.prodname_dotcom_the_website %}
* Organization-owned repositories on {% data variables.product.prodname_team %}, {% data variables.product.prodname_ghe_cloud %}, or {% data variables.product.prodname_ghe_server %}, with [{% data variables.product.prodname_GH_code_security %}](/get-started/learning-about-github/about-github-advanced-security) enabled.
````

### `data/reusables/code-scanning/enterprise-enable-code-scanning.md`

````markdown
{% ifversion ghes %}

> [!NOTE]
> Your site administrator must enable {% data variables.product.prodname_code_scanning %} before you can use this feature. For more information, see [AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/configuring-code-scanning-for-your-appliance).
>
> You may not be able to enable or disable {% data variables.product.prodname_code_scanning %} if an enterprise owner has set a {% data variables.product.prodname_GH_code_security %} policy at the enterprise level. For more information, see [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-security-and-analysis-for-your-enterprise).

{% endif %}
````

### `data/reusables/code-scanning/about-code-scanning.md`

````markdown
{% data variables.product.prodname_code_scanning_caps %} is a feature that you use to analyze the code in a {% data variables.product.prodname_dotcom %} repository to find security vulnerabilities and coding errors. Any problems identified by the analysis are shown in your repository.
````

### `data/reusables/advanced-security/ghas-trial.md`

````markdown
{% ifversion ghec %}For information about how you can try {% data variables.product.prodname_GHAS %} for free, see [AUTOTITLE](/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security).
{% elsif fpt %}For information about how you can try {% data variables.product.prodname_enterprise %} with {% data variables.product.prodname_GHAS %} for free, see [AUTOTITLE](/enterprise-cloud@latest/admin/overview/setting-up-a-trial-of-github-enterprise-cloud) and [AUTOTITLE](/enterprise-cloud@latest/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security#setting-up-your-trial-of-github-advanced-security) in the {% data variables.product.prodname_ghe_cloud %} documentation.{% endif %}
````

### `data/reusables/code-scanning/about-codeql-analysis.md`

````markdown
{% data variables.product.prodname_codeql %} is the code analysis engine developed by {% data variables.product.company_short %} to automate security checks. You can analyze your code using {% data variables.product.prodname_codeql %} and display the results as {% data variables.product.prodname_code_scanning %} alerts.
````

### `data/reusables/code-scanning/interoperable-with-tools-that-output-sarif.md`

````markdown
{% data variables.product.prodname_code_scanning_caps %} is interoperable with third-party code scanning tools that output Static Analysis Results Interchange Format (SARIF) data. SARIF is an open standard. For more information, see [AUTOTITLE](/code-security/reference/code-scanning/sarif-files/sarif-support).
````

### `data/features/code-scanning-autofix.yml`

````yaml
# Reference: #11173, and 14966
# This feature is not yet available for GitHub Enterprise Server.
versions:
  ghec: '*'
  fpt: '*'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_code_scanning_caps %}` | Code scanning |
| `{% data variables.copilot.copilot_autofix %}` | GitHub Copilot Autofix |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_GH_code_security %}` | GitHub Code Security |
| `{% data variables.product.prodname_code_security_risk_assessment %}` | code security risk assessment |
| `{% data variables.product.prodname_codeql %}` | CodeQL |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.code-scanning.tool_status_page %}` | tool status page |
| `{% data variables.product.prodname_dotcom_the_website %}` | GitHub.com |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.prodname_GHAS %}` | GitHub Advanced Security |
| `{% data variables.product.prodname_enterprise %}` | GitHub Enterprise |
