# Source Snapshot: About GitHub Advanced Security

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security
- **Upstream file:** [`github/docs` → `content/get-started/learning-about-github/about-github-advanced-security.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/get-started/learning-about-github/about-github-advanced-security.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/ghas-ghec.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/ghas-ghec.md); [`data/reusables/advanced-security/ghas-for-azdo-link.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/advanced-security/ghas-for-azdo-link.md); [`data/reusables/advanced-security/ghas-products-bullets.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/advanced-security/ghas-products-bullets.md); [`data/reusables/secret-protection/product-list.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/secret-protection/product-list.md); [`data/reusables/security-configurations/enable-security-features-with-gh-config.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/security-configurations/enable-security-features-with-gh-config.md); [`data/features/code-scanning-autofix.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/code-scanning-autofix.yml); [`data/features/ai-powered-security-detections.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/ai-powered-security-detections.yml); [`data/features/security-campaigns.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/security-campaigns.yml); [`data/features/ghas-products-cloud.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/ghas-products-cloud.yml); [`data/features/secret-scanning-ai-generic-secret-detection.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/secret-scanning-ai-generic-secret-detection.yml); [`data/features/security-campaigns-secrets.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/security-campaigns-secrets.yml); [`data/features/code-security-risk-assessment.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/code-security-risk-assessment.yml); [`data/features/disable-ghas-button.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/disable-ghas-button.yml); [`data/features/copilot-chat-ghas-alerts.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/copilot-chat-ghas-alerts.yml); [`data/features/github-certification.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/github-certification.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About GitHub Advanced Security
intro: '{% data variables.product.github %} makes extra security features available to customers who purchase {% data variables.product.prodname_GH_code_security %} or {% data variables.product.prodname_GH_secret_protection %}.{% ifversion fpt or ghec %} Some features are enabled for public repositories by default.{% endif %}'
product: '{% data reusables.gated-features.ghas-ghec %}'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
redirect_from:
  - /github/getting-started-with-github/about-github-advanced-security
  - /github/getting-started-with-github/learning-about-github/about-github-advanced-security
shortTitle: GitHub Advanced Security
category:
  - Explore GitHub plans and features
---

## About {% data variables.product.prodname_GHAS %} products

{% data variables.product.github %} has many features that help you improve and maintain the quality of your code. Some of these are included in all plans, such as dependency graph and {% data variables.product.prodname_dependabot_alerts %}.

Other security features require you to purchase one of {% data variables.product.github %}'s {% data variables.product.prodname_AS %} products:

{% data reusables.advanced-security.ghas-products-bullets+ghas %}

{% ifversion fpt or ghec %}Some of these features, such as {% data variables.product.prodname_code_scanning %} and {% data variables.product.prodname_secret_scanning %}, are enabled for public repositories by default. To run the feature on your private or internal repositories, you must purchase the relevant {% data variables.product.prodname_GHAS %} product.{% endif %}

You must be on a {% data variables.product.prodname_team %} or {% data variables.product.prodname_enterprise %} plan in order to purchase {% data variables.product.prodname_GH_code_security %} or {% data variables.product.prodname_GH_secret_protection %}. For more information, see [AUTOTITLE](/get-started/learning-about-github/githubs-plans) and [AUTOTITLE](/billing/concepts/product-billing/github-advanced-security).

## {% data variables.product.prodname_GH_code_security %}

You get the following features with {% data variables.product.prodname_GH_code_security %}:

* **{% data variables.product.prodname_code_scanning_caps %}**: Search for potential security vulnerabilities and coding errors in your code using {% data variables.product.prodname_codeql %} or a third-party tool.

* **{% data variables.product.prodname_codeql_cli %}**: Run {% data variables.product.prodname_codeql %} processes locally on software projects or to generate {% data variables.product.prodname_code_scanning %} results for upload to {% data variables.product.github %}.{% ifversion code-scanning-autofix %}

* **{% data variables.copilot.copilot_autofix_short %}**: Get automatically generated fixes for {% data variables.product.prodname_code_scanning %} alerts.{% ifversion ai-powered-security-detections %}

* **AI Scan**: Find vulnerabilities in languages and frameworks not covered by {% data variables.product.prodname_codeql %} with an AI-based scanning engine that runs during pull request review.{% endif %}{% endif %}{% ifversion security-campaigns %}

* **Security campaigns**: Reduce security debt at scale.{% endif %}

* **{% data variables.dependabot.custom_rules_caps %} for {% data variables.product.prodname_dependabot %}**: Manage your {% data variables.product.prodname_dependabot_alerts %} at scale, by automating which alerts you want to ignore, snooze, or trigger a {% data variables.product.prodname_dependabot %} security update for.

* **Dependency review**: Show the full impact of changes to dependencies and see details of any vulnerable versions before you merge a pull request.

* **Security overview**: Understand the distribution of risk across your organization.

{% ifversion fpt or ghec %}

The table below summarizes the availability of {% data variables.product.prodname_GH_code_security %} features for public and private repositories.

{% rowheaders %}

| | Public repository <br>without {% data variables.product.prodname_GH_code_security %} | Private repository <br>without {% data variables.product.prodname_GH_code_security %} | Public or private repository <br>with {% data variables.product.prodname_GH_code_security %} |
| --- | --- | --- | --- |
| {% data variables.product.prodname_code_scanning_caps %} | {% octicon "check" aria-label="Yes" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
| {% data variables.product.prodname_codeql_cli %} | {% octicon "check" aria-label="Yes" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% ifversion code-scanning-autofix %}|
| {% data variables.copilot.copilot_autofix_short %} | {% octicon "check" aria-label="Yes" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% endif %}|
|{% ifversion security-campaigns %}|
| Security campaigns | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% endif %}|
| {% data variables.dependabot.custom_rules_caps %} | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
| Dependency review | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
| Security overview | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
{% endrowheaders %}

{% endif %}

For more information about features, see [AUTOTITLE](/code-security/getting-started/github-security-features).

## {% data variables.product.prodname_GH_secret_protection %}

You get the following features with {% data variables.product.prodname_GH_secret_protection %}:

{% data reusables.secret-protection.product-list %}

{% ifversion ghas-products-cloud %}

The table below summarizes the availability of {% data variables.product.prodname_GH_secret_protection %} features for public and private repositories.

{% rowheaders %}

| | Public repository <br>without {% data variables.product.prodname_GH_secret_protection %} | Private repository <br>without {% data variables.product.prodname_GH_secret_protection %} | Public or private repository <br>with {% data variables.product.prodname_GH_secret_protection %} |
| --- | --- | --- | --- |
| Secret scanning   | {% octicon "check" aria-label="Yes" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
| Push protection   | {% octicon "check" aria-label="Yes" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% ifversion secret-scanning-ai-generic-secret-detection %}|
| AI-detected secrets  | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% endif %}|
| Custom patterns   | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
| Delegated bypass for push protection    | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% ifversion security-campaigns-secrets %}|
| Security campaigns | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |
|{% endif %}|
| Security overview   | {% octicon "x" aria-label="No" %} | {% octicon "x" aria-label="No" %} | {% octicon "check" aria-label="Yes" %} |

{% endrowheaders %}

{% endif %}

For more information about individual features, see [AUTOTITLE](/code-security/getting-started/github-security-features).

## Run a free security risk assessment

<a href="https://github.com/get_started?with=risk-assessment&ref_product=code-scanning&ref_type=engagement&ref_style=button" target="_blank" class="btn btn-primary mt-3 mr-3 no-underline"><span>Get started with security risk assessments</span> {% octicon "link-external" height:16 %}</a>

Organizations on {% data variables.product.prodname_team %} and {% data variables.product.prodname_enterprise %} can run free security risk assessments to understand their exposure to security vulnerabilities:

* **Secret leaks**: Scan your organization for leaked secrets and see how many could have been prevented by {% data variables.product.prodname_GH_secret_protection %}. See [AUTOTITLE](/code-security/concepts/secret-security/secret-security-with-github#secret-risk-assessment).
{% ifversion code-security-risk-assessment %}
* **Code vulnerabilities**: Scan up to 20 of your most active repositories and see how many vulnerabilities could be automatically fixed with {% data variables.copilot.copilot_autofix_short %} if you enable {% data variables.product.prodname_GH_code_security %}. See [AUTOTITLE](/code-security/concepts/code-scanning/risk-assessment).
{% endif %}

## Deploying {% data variables.product.prodname_GH_code_security %} and {% data variables.product.prodname_GH_secret_protection %}

To learn about what you need to know to plan your deployment of {% data variables.product.prodname_GH_code_security %} and {% data variables.product.prodname_GH_secret_protection %} at a high level and to review the rollout phases we recommended, see [AUTOTITLE](/code-security/tutorials/adopting-github-advanced-security-at-scale).

## Enabling features

{% data reusables.security-configurations.enable-security-features-with-gh-config %}

If you are on a {% data variables.product.prodname_team %} or {% data variables.product.prodname_enterprise %} plan, license use for the entire team or enterprise is shown on your license page. {% ifversion fpt or ghec %}See [AUTOTITLE](/billing/how-tos/products/view-productlicense-use).{% endif %}

{% ifversion disable-ghas-button %}

## Managing {% data variables.product.prodname_GHAS %}

Enterprise owners can manage {% data variables.product.prodname_GHAS %} licensing and access for their enterprise, including disabling {% data variables.product.prodname_GHAS %} across all repositories and preventing future re-enablement. See [AUTOTITLE](/billing/how-tos/products/disable-ghas-for-enterprise).

For information about managing your {% data variables.product.prodname_GHAS %} license, see [AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/managing-your-github-advanced-security-license-usage).

{% endif %}

{% ifversion copilot-chat-ghas-alerts %}

## Leveraging {% data variables.copilot.copilot_chat %} to understand security alerts

Additionally, with a {% data variables.copilot.copilot_enterprise %} license, you can ask {% data variables.copilot.copilot_chat %} for help to better understand security alerts in repositories in your organization ({% data variables.product.prodname_code_scanning %}, {% data variables.product.prodname_secret_scanning %}, and {% data variables.product.prodname_dependabot_alerts %}). See [AUTOTITLE](/copilot/how-tos/chat-with-copilot/get-started-with-chat-in-your-ide#ask-questions-about-alerts-from-github-advanced-security-features).
{% endif %}

{% ifversion github-certification %}

## About {% data variables.product.prodname_GHAS %} Certification

You can highlight your knowledge by earning a {% data variables.product.prodname_GHAS %} certificate with {% data variables.product.prodname_certifications %}. The certification validates your expertise in vulnerability identification, workflow security, and robust security implementation. See [AUTOTITLE](/get-started/showcase-your-expertise-with-github-certifications/about-github-certifications).

{% endif %}

## About {% data variables.product.prodname_GHAS %} with Azure Repos

If you want to use {% data variables.product.prodname_GHAS %} with Azure Repos, see [{% data variables.product.prodname_GHAS %} & Azure DevOps](https://resources.github.com/topics/github-advanced-security/) in our resources site. For documentation, see [Configure {% data variables.product.prodname_ghas_azdo %}](https://learn.microsoft.com/en-us/azure/devops/repos/security/configure-github-advanced-security-features) in Microsoft Learn.

## Further reading

* [AUTOTITLE](/code-security/getting-started/github-security-features)
* [{% data variables.product.github %} public roadmap](https://github.com/github/roadmap){%- ifversion ghec or ghes %}
* [AUTOTITLE](/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-security-and-analysis-for-your-enterprise){% endif %}

---

## Included files

### `data/reusables/gated-features/ghas-ghec.md`

````markdown

{% data variables.product.prodname_GH_code_security %} and {% data variables.product.prodname_GH_secret_protection %} are available for {% ifversion fpt or ghec %}accounts on {% data variables.product.prodname_team %} and {% data variables.product.prodname_ghe_cloud %}{% elsif ghes %}accounts on {% data variables.product.prodname_ghe_server %}{% endif %}.

{% ifversion fpt or ghec %} Some features are also available for free for public repositories on {% data variables.product.prodname_dotcom_the_website %}.{% endif %} For more information, see [AUTOTITLE](/get-started/learning-about-github/githubs-plans).

{% data reusables.advanced-security.ghas-for-azdo-link %}
````

### `data/reusables/advanced-security/ghas-for-azdo-link.md`

````markdown
For information about {% data variables.product.prodname_ghas_azdo %}, see [Configure {% data variables.product.prodname_ghas_azdo %}](https://learn.microsoft.com/en-us/azure/devops/repos/security/configure-github-advanced-security-features) in Microsoft Learn.
````

### `data/reusables/advanced-security/ghas-products-bullets.md`

````markdown
* **{% data variables.product.prodname_GH_secret_protection %}**, which includes features that help you detect and prevent secret leaks, such as {% data variables.product.prodname_secret_scanning %} and push protection.
* **{% data variables.product.prodname_GH_code_security %}**, which includes features that help you find and fix vulnerabilities, like {% data variables.product.prodname_code_scanning %}, premium {% data variables.product.prodname_dependabot %} features, and dependency review.
````

### `data/reusables/secret-protection/product-list.md`

````markdown
* **{% data variables.product.prodname_secret_scanning_caps %}**: Detect secrets, for example keys and tokens, that have been checked into a repository and receive alerts.
* **Push protection**: Prevent secret leaks before they happen by blocking commits containing secrets.{% ifversion secret-scanning-ai-generic-secret-detection %}
* **{% data variables.secret-scanning.ai-detected-secrets-caps %}**: Leverage AI to detect unstructured credentials, such as passwords, that have been checked into a repository.{% endif %}
* **Custom patterns**: Detect and prevent leaks for organization-specific secrets.
* **Delegated bypass for push protection** and **Delegated alert dismissal**:  Implement an approval process for better control over who in your enterprise can perform sensitive actions, supporting governance at scale.{% ifversion security-campaigns-secrets %}
* **Security campaigns**: Remediate exposed secrets at scale by creating a campaign and collaborating to fix them.{% endif %}
* **Security overview**: Understand the distribution of risk across your organization.
````

### `data/reusables/security-configurations/enable-security-features-with-gh-config.md`

````markdown
You can quickly enable security features at scale with a {% data variables.product.prodname_security_configuration %}, a collection of security enablement settings you can apply to repositories in an organization. You can customize {% data variables.product.prodname_AS %} features at the organization level with {% data variables.product.prodname_global_settings %}. See [AUTOTITLE](/code-security/concepts/security-at-scale/organization-security).
````

### `data/features/code-scanning-autofix.yml`

````yaml
# Reference: #11173, and 14966
# This feature is not yet available for GitHub Enterprise Server.
versions:
  ghec: '*'
  fpt: '*'
````

### `data/features/ai-powered-security-detections.yml`

````yaml
# Reference: #20824
versions:
  ghec: '*'
  fpt: '*'
````

### `data/features/security-campaigns.yml`

````yaml
# Reference: #14514
# Documentation for security campaigns for code scanning alerts
# Ref 17108 Advanced Security available to Team plans
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/ghas-products-cloud.yml`

````yaml
# Reference: #16634
# Use for content that is only available in GitHub Cloud.
# GitHub Advanced Security products available as two separate SKUS: Secret Protection and Code Security
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/secret-scanning-ai-generic-secret-detection.yml`

````yaml
# Reference: #11292
# Documentation for generic secret detection using AI
# Ref 17108 Advanced Security available to Team plans
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>=3.23'
````

### `data/features/security-campaigns-secrets.yml`

````yaml
# Reference: #18650
# Documentation for security campaigns for secret scanning alerts
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/code-security-risk-assessment.yml`

````yaml
# Reference: #19489
# This feature is not yet available for GitHub Enterprise Server.
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

### `data/features/copilot-chat-ghas-alerts.yml`

````yaml
# Reference: #15479
versions:
  ghec: '*'
````

### `data/features/github-certification.yml`

````yaml
# Reference: #12157.
# Documentation for the GitHub Certification program

versions:
  fpt: '*'
  ghec: '*'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_GH_code_security %}` | GitHub Code Security |
| `{% data variables.product.prodname_GH_secret_protection %}` | GitHub Secret Protection |
| `{% data variables.product.prodname_GHAS %}` | GitHub Advanced Security |
| `{% data variables.product.prodname_dependabot_alerts %}` | Dependabot alerts |
| `{% data variables.product.prodname_AS %}` | Advanced Security |
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_secret_scanning %}` | secret scanning |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_enterprise %}` | GitHub Enterprise |
| `{% data variables.product.prodname_code_scanning_caps %}` | Code scanning |
| `{% data variables.product.prodname_codeql %}` | CodeQL |
| `{% data variables.product.prodname_codeql_cli %}` | CodeQL CLI |
| `{% data variables.copilot.copilot_autofix_short %}` | Copilot Autofix |
| `{% data variables.dependabot.custom_rules_caps %}` | Custom auto-triage rules |
| `{% data variables.product.prodname_dependabot %}` | Dependabot |
| `{% data variables.copilot.copilot_chat %}` | GitHub Copilot Chat |
| `{% data variables.copilot.copilot_enterprise %}` | GitHub Copilot Enterprise |
| `{% data variables.product.prodname_certifications %}` | GitHub Certifications |
| `{% data variables.product.prodname_ghas_azdo %}` | GitHub Advanced Security for Azure DevOps |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.prodname_dotcom_the_website %}` | GitHub.com |
| `{% data variables.product.prodname_secret_scanning_caps %}` | Secret scanning |
| `{% data variables.secret-scanning.ai-detected-secrets-caps %}` | AI-detected secrets |
| `{% data variables.product.prodname_security_configuration %}` | security configuration |
| `{% data variables.product.prodname_global_settings %}` | global settings |
