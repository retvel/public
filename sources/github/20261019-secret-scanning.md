# Source Snapshot: Secret scanning

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/code-security/concepts/secret-security/secret-scanning
- **Upstream file:** [`github/docs` → `content/code-security/concepts/secret-security/secret-scanning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/code-security/concepts/secret-security/secret-scanning.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/security-overview/navigate-to-risk-assessment.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/security-overview/navigate-to-risk-assessment.md); [`data/reusables/secret-scanning/what-is-scanned.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/secret-scanning/what-is-scanned.md); [`data/reusables/gated-features/secret-scanning.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/secret-scanning.md); [`data/features/secret-scanning-validity-check-partner-patterns.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/secret-scanning-validity-check-partner-patterns.yml); [`data/features/secret-scanning-ai-generic-secret-detection.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/secret-scanning-ai-generic-secret-detection.yml); [`data/features/secret-scanning-custom-pattern-ai-generated.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/secret-scanning-custom-pattern-ai-generated.yml); [`data/features/secret-scanning-public-monitoring.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/secret-scanning-public-monitoring.yml); [`data/features/secret-scanning-enhancements-wikis.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/secret-scanning-enhancements-wikis.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Secret scanning
intro: Prevent fraudulent use of your secrets by automatically detecting exposed credentials before they can be exploited.
redirect_from:
  - /github/administering-a-repository/about-token-scanning
  - /articles/about-token-scanning
  - /articles/about-token-scanning-for-private-repositories
  - /github/administering-a-repository/about-secret-scanning
  - /code-security/secret-security/about-secret-scanning
  - /code-security/secret-scanning/about-secret-scanning
  - /code-security/secret-scanning/introduction/about-secret-scanning
  - /code-security/concepts/secret-security/about-secret-scanning
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Secret scanning
contentType: concepts
category:
  - Protect your secrets
---

When credentials like API keys and passwords are committed to repositories as hardcoded secrets, they become targets for unauthorized access. {% data variables.product.prodname_secret_scanning_caps %} automatically detects credential leaks so you can secure them before they're exploited.

> [!TIP]
> At any time, you can run a free assessment of your organization's code for leaked secrets. 
>
> To generate a report, open {% data reusables.security-overview.navigate-to-risk-assessment %}.

## How secret scanning protects your code

{% data variables.product.prodname_secret_scanning_caps %} scans your entire Git history on all branches of your repository for hardcoded credentials, including API keys, passwords, tokens, and other known secret types. This helps you identify secret sprawl, the uncontrolled proliferation of credentials across repositories, before it becomes a security risk. {% data variables.product.github %} also periodically rescans repositories when new secret types are added.

{% data variables.product.github %} also automatically scans:

{% data reusables.secret-scanning.what-is-scanned %}

### {% data variables.product.prodname_secret_scanning_caps %} alerts and remediation

When {% data variables.product.prodname_secret_scanning %} detects a credential leak, {% data variables.product.github %} generates an alert on your repository's **{% data variables.product.prodname_security_and_quality_tab %}** tab with details about the exposed credential.

When you receive an alert, rotate the affected credential immediately to prevent unauthorized access. While you can also remove secrets from your Git history, this is time-intensive and often unnecessary if you've already revoked the credential.

{% ifversion fpt or ghec %}

### Partner integration

{% data variables.product.company_short %} partners with a large variety of service providers to validate detected secrets. When a partner secret is detected, we notify the provider so they can take action, such as revoking the credential. Partner secrets are reported directly to the provider and aren't displayed in your repository alerts. For more information, see [AUTOTITLE](/code-security/tutorials/secret-scanning-partner-program).

{% endif %}

## Customizability

Beyond the default detection of partner and provider secrets, you can expand and customize {% data variables.product.prodname_secret_scanning %} to fit your needs.

* **Generic patterns.** Expand detection to secrets that aren't tied to a specific service provider, such as private keys, connection strings, and generic API keys.
* **Custom patterns.** Define your own regular expressions to detect organization-specific secrets that aren't covered by default patterns.
{% ifversion secret-scanning-validity-check-partner-patterns %}
* **Validity checks.** Prioritize remediation by checking whether detected secrets are still active.
{% endif %}
{% ifversion secret-scanning-ai-generic-secret-detection %}
* **{% data variables.secret-scanning.ai-detected-secrets-caps %}.** Use AI to detect unstructured secrets like passwords.
{% endif %}
{% ifversion secret-scanning-custom-pattern-ai-generated %}
* **AI-generated regular expressions.** Use AI to generate regular expressions for custom patterns.
{% endif %}

{% ifversion secret-scanning-validity-check-partner-patterns %}

### About validity checks

Validity checks help you prioritize which secrets to remediate first by verifying whether a detected secret is still active. When you enable validity checks, {% data variables.product.prodname_secret_scanning %} may contact the secret's issuing service to determine if the credential has been revoked. For more information, see [AUTOTITLE](/code-security/concepts/secret-security/validity-checks).

{% endif %}

## How can I access this feature?

{% data reusables.gated-features.secret-scanning %}

{% ifversion secret-scanning-public-monitoring %}

## Public monitoring

In addition to scanning repositories your enterprise owns, you can enable public monitoring to detect secrets leaked by your enterprise members in public repositories across {% data variables.product.github %}. This extends {% data variables.product.prodname_secret_scanning %} beyond the repositories your enterprise owns to follow your members' activity across the platform. See [AUTOTITLE](/code-security/concepts/secret-security/public-monitoring).

{% endif %}

---

## Included files

### `data/reusables/security-overview/navigate-to-risk-assessment.md`

````markdown
the **{% data variables.product.prodname_security_and_quality_tab %}** tab for your organization, display the **{% octicon "key" aria-hidden="true" aria-label="key" %} Assessments** page, then click **Scan your organization**
````

### `data/reusables/secret-scanning/what-is-scanned.md`

````markdown
* Descriptions and comments in issues
* Titles, descriptions, and comments, in open and closed _historical_ issues
* Titles, descriptions, and comments in pull requests
* Titles, descriptions, and comments in {% data variables.product.prodname_discussions %}{% ifversion secret-scanning-enhancements-wikis %}
* Wikis{% endif %}
* Secret gists
````

### `data/reusables/gated-features/secret-scanning.md`

````markdown
{% data variables.product.prodname_secret_scanning_caps %} is available for the following repository types:

* **Public repositories**: {% data variables.product.prodname_secret_scanning_caps %} runs automatically for free.
* **Organization-owned private and internal repositories**: Available with [{% data variables.product.prodname_GH_secret_protection %}](/get-started/learning-about-github/about-github-advanced-security) enabled on {% data variables.product.prodname_team %} or {% data variables.product.prodname_ghe_cloud %}.
* **User-owned repositories**: Available on {% data variables.product.prodname_ghe_cloud %} with {% data variables.product.prodname_emus %}. Available on {% data variables.product.prodname_ghe_server %} when the enterprise has [{% data variables.product.prodname_GH_secret_protection %}](/get-started/learning-about-github/about-github-advanced-security) enabled.
````

### `data/features/secret-scanning-validity-check-partner-patterns.yml`

````yaml
# Reference: #9861.
# Documentation for secret scanning: validity check for partner patterns (GHAS).
# Ref 17108 Advanced Security available to Team plans
# Ref 19224 Secret scanning validity checks available on GHES 3.20 [GA]
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>=3.20'
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

### `data/features/secret-scanning-custom-pattern-ai-generated.yml`

````yaml
# Reference: #11322
# Secret scanning: Generate regex for custom patterns using AI [Limited Public Beta]
# Ref 17108 Advanced Security available to Team plans
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/secret-scanning-public-monitoring.yml`

````yaml
# Reference: #21498
# Secret scanning: public monitoring for enterprises (public preview)
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/secret-scanning-enhancements-wikis.yml`

````yaml
# Reference: #13325 and #19222
# Secret Scanning Detection for GitHub Wikis
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>3.18'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_secret_scanning_caps %}` | Secret scanning |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_secret_scanning %}` | secret scanning |
| `{% data variables.product.prodname_security_and_quality_tab %}` | {% octicon "shield" aria-hidden="true" aria-label="shield" %} {% ifversion security-and-quality-tab %}Security and quality{% else %}Security{% endif %} |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.secret-scanning.ai-detected-secrets-caps %}` | AI-detected secrets |
| `{% data variables.product.prodname_discussions %}` | GitHub Discussions |
| `{% data variables.product.prodname_GH_secret_protection %}` | GitHub Secret Protection |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_emus %}` | Enterprise Managed Users |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
