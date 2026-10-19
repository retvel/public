# Source Snapshot: Secrets reference

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/actions/reference/security/secrets
- **Upstream file:** [`github/docs` → `content/actions/reference/security/secrets.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/actions/reference/security/secrets.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/actions/actions-secrets-and-variables-naming.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/actions-secrets-and-variables-naming.md); [`data/reusables/codespaces/secret-precedence.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/codespaces/secret-precedence.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Secrets reference
shortTitle: Secrets
intro: Find technical information about secrets in {% data variables.product.prodname_actions %}.
versions:
  fpt: '*'
  ghec: '*'
  ghes: '*'
redirect_from:
  - /actions/reference/secrets-reference
category:
  - Secure your workflows
contentType: reference
---

## Naming your secrets

>[!TIP]
> To help ensure that {% data variables.product.prodname_dotcom %} redacts your secrets in logs correctly, avoid using structured data as the values of secrets.

The following rules apply to secret names:

{% data reusables.actions.actions-secrets-and-variables-naming %}

{% data reusables.codespaces.secret-precedence %} Similarly, if an organization, repository, and environment all have a secret with the same name, the environment-level secret takes precedence.

## Limits for secrets

You can store up to 1,000 organization secrets, 100 repository secrets, and 100 environment secrets.

A workflow created in a repository can access the following number of secrets:

* All 100 repository secrets.
* If the repository is assigned access to more than 100 organization secrets, the workflow can only use the first 100 organization secrets (sorted alphabetically by secret name).
* All 100 environment secrets.

Secrets are limited to 48 KB in size. To store larger secrets, see [AUTOTITLE](/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets#storing-large-secrets).

## When {% data variables.product.prodname_actions %} reads secrets

Organization and repository secrets are read when a workflow run is queued, and environment secrets are read when a job referencing the environment starts.

## Automatically redacted secrets

{% data variables.product.prodname_dotcom %} automatically redacts the following sensitive information from workflow logs.

> [!NOTE] If you would like other types of sensitive information to be automatically redacted, please reach out to us in our [community discussions](https://github.com/orgs/community/discussions?discussions_q=is%3Aopen+label%3AActions).

* 32-byte and 64-byte Azure keys
* Azure AD client app passwords
* Azure Cache keys
* Azure Container Registry keys
* Azure Function host keys
* Azure Search keys
* Database connection strings
* HTTP Bearer token headers
* JWTs
* NPM author tokens
* NuGet API keys
* v1 GitHub installation tokens
* v2 GitHub installation tokens (`ghp`, `gho`, `ghu`, `ghs`, `ghr`)
* v2 GitHub PATs

## Security

For security best practices using secrets, see [AUTOTITLE](/actions/reference/security/secure-use#use-secrets-for-sensitive-information).

---

## Included files

### `data/reusables/actions/actions-secrets-and-variables-naming.md`

````markdown
* Can only contain alphanumeric characters (`[a-z]`, `[A-Z]`, `[0-9]`) or underscores (`_`). Spaces are not allowed.
* Must not start with the `GITHUB_` prefix.
* Must not start with a number.
* Are case insensitive when referenced. {% data variables.product.github %} stores secret names as uppercase regardless of how they are entered.
* Must be unique to the repository, organization, or enterprise where they are created.
````

### `data/reusables/codespaces/secret-precedence.md`

````markdown
If a secret with the same name exists at multiple levels, the secret at the lowest level takes precedence. For example, if an organization-level secret has the same name as a repository-level secret, then the repository-level secret takes precedence.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.github %}` | GitHub |
