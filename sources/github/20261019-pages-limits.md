# Source Snapshot: GitHub Pages limits

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits
- **Upstream file:** [`github/docs` → `content/pages/getting-started-with-github-pages/github-pages-limits.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/pages/getting-started-with-github-pages/github-pages-limits.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/pages.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/pages.md); [`data/reusables/gated-features/more-info.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/more-info.md); [`data/reusables/pages/no_sensitive_data_pages.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/pages/no_sensitive_data_pages.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: GitHub Pages limits
intro: 'Learn about the limits and limitations of GitHub Pages.'
product: '{% data reusables.gated-features.pages %}'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Set up a GitHub Pages site
---

## Usage limits

{% data variables.product.prodname_pages %} is not intended for or allowed to be used as a free web-hosting service to run your online business, e-commerce site, or any other website that is primarily directed at either facilitating commercial transactions or providing commercial software as a service (SaaS). {% data reusables.pages.no_sensitive_data_pages %}

In addition, your use of {% data variables.product.prodname_pages %} is subject to the [GitHub Terms of Service](/free-pro-team@latest/site-policy/github-terms/github-terms-of-service), including the restrictions on get-rich-quick schemes, sexually obscene content, and violent or threatening content or activity.

{% data variables.product.prodname_pages %} sites are subject to the following usage limits:

* You can only create one user or organization site for each account on {% data variables.product.github %}.
* {% data variables.product.prodname_pages %} source repositories have a recommended limit of 1 GB. {% ifversion fpt or ghec %}For more information, see [AUTOTITLE](/repositories/working-with-files/managing-large-files/about-large-files-on-github){% endif %}.
* Published {% data variables.product.prodname_pages %} sites may be no larger than 1 GB.
* {% data variables.product.prodname_pages %} deployments will timeout if they take longer than 10 minutes.
{% ifversion fpt or ghec %}
* {% data variables.product.prodname_pages %} sites have a _soft_ bandwidth limit of 100 GB per month.
* {% data variables.product.prodname_pages %} sites have a _soft_ limit of 10 builds per hour. This limit does not apply if you build and publish your site with a custom {% data variables.product.prodname_actions %} workflow.
* In order to provide consistent quality of service for all {% data variables.product.prodname_pages %} sites, rate limits may apply. These rate limits are not intended to interfere with legitimate uses of {% data variables.product.prodname_pages %}. If your request triggers rate limiting, you will receive an appropriate response with an HTTP status code of `429`, along with an informative HTML body.

If your site exceeds these usage quotas, we may not be able to serve your site, or you may receive a polite email from {% data variables.contact.github_support %} suggesting strategies for reducing your site's impact on our servers, including putting a third-party content distribution network (CDN) in front of your site, making use of other {% data variables.product.prodname_dotcom %} features such as releases, or moving to a different hosting service that might better fit your needs.

{% endif %}

{% ifversion ghec %}

## Limits for {% data variables.product.prodname_emus %}

If you're a {% data variables.enterprise.prodname_managed_user %}, your use of {% data variables.product.prodname_pages %} is limited.

* {% data variables.product.prodname_pages %} sites can only be published from repositories owned by organizations.
* {% data variables.product.prodname_pages %} sites are always privately published, and you cannot change this visibility. For more information, see [AUTOTITLE](/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site).
* You cannot create an organization site (a site published from a repository named `<organization>.github.io`)

For more information about {% data variables.product.prodname_emus %}, see [AUTOTITLE](/admin/concepts/identity-and-access-management/enterprise-managed-users).

{% endif %}

## Educational exercises

Using {% data variables.product.prodname_pages %} to create a copy of an existing website as a learning exercise is not prohibited. However, in addition to complying with the [GitHub Terms of Service](/free-pro-team@latest/site-policy/github-terms/github-terms-of-service), you must write the code yourself, the site must not collect any user data, and you must include a prominent disclaimer on the site indicating that the project is not associated with the original and was only created for educational purposes.

---

## Included files

### `data/reusables/gated-features/pages.md`

````markdown
{% data variables.product.prodname_pages %} is available in public repositories with {% data variables.product.prodname_free_user %} and {% data variables.product.prodname_free_team %} for organizations, and in public and private repositories with {% data variables.product.prodname_pro %}, {% data variables.product.prodname_team %}, {% data variables.product.prodname_ghe_cloud %}, and {% data variables.product.prodname_ghe_server %}. {% ifversion fpt or ghec %}{% data reusables.gated-features.more-info %}{% endif %}
````

### `data/reusables/gated-features/more-info.md`

````markdown
See [AUTOTITLE](/get-started/learning-about-github/githubs-plans).
````

### `data/reusables/pages/no_sensitive_data_pages.md`

````markdown
{% data variables.product.prodname_pages %} sites shouldn't be used for sensitive transactions like sending passwords or credit card numbers.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_pages %}` | GitHub Pages |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.contact.github_support %}` | GitHub Support |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_emus %}` | Enterprise Managed Users |
| `{% data variables.enterprise.prodname_managed_user %}` | managed user account |
| `{% data variables.product.prodname_free_user %}` | GitHub Free |
| `{% data variables.product.prodname_free_team %}` | GitHub Free |
| `{% data variables.product.prodname_pro %}` | GitHub Pro |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
