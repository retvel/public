# Source Snapshot: Secrets

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/actions/concepts/security/secrets
- **Upstream file:** [`github/docs` → `content/actions/concepts/security/secrets.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/actions/concepts/security/secrets.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/actions/secrets-org-level-overview.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/secrets-org-level-overview.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Secrets
intro: Learn about secrets as they are used in {% data variables.product.prodname_actions %} workflows.
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
redirect_from:
  - /actions/security-for-github-actions/security-guides/about-secrets
  - /actions/concepts/security/about-secrets
category:
  - Secure your workflows
contentType: concepts
---

## About secrets

Secrets allow you to store sensitive information in your organization, repository, or repository environments. Secrets are variables that you create to use in {% data variables.product.prodname_actions %} workflows in an organization, repository, or repository environment.

{% data variables.product.prodname_actions %} can only read a secret if you explicitly include the secret in a workflow.

{% ifversion fpt or ghec %}

## How secrets work

Secrets use [Libsodium sealed boxes](https://libsodium.gitbook.io/doc/public-key_cryptography/sealed_boxes), so that they are encrypted before reaching {% data variables.product.github %}. This occurs when the secret is submitted [using the UI](/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets#creating-secrets-for-a-repository) or through the [REST API](/rest/actions/secrets). This client-side encryption helps minimize the risks related to accidental logging (for example, exception logs and request logs, among others) within {% data variables.product.github %}'s infrastructure. Once the secret is uploaded, {% data variables.product.github %} is then able to decrypt it so that it can be injected into the workflow runtime.

{% endif %}

## Organization-level secrets

{% data reusables.actions.secrets-org-level-overview %}

When creating a secret for an organization, you can use a policy to limit access by repository. For example, you can grant access to all repositories, or limit access to only private repositories or a specified list of repositories.

For environment secrets, you can enable required reviewers to control access to the secrets. A workflow job cannot access environment secrets until approval is granted by required approvers.

To make a secret available to an action, you must set the secret as an input or environment variable in your workflow file. Review the action's README file to learn about which inputs and environment variables the action expects. See [AUTOTITLE](/actions/reference/workflows-and-actions/workflow-syntax#jobsjob_idstepsenv).

## Limiting credential permissions

When generating credentials, we recommend that you grant the minimum permissions possible. For example, instead of using personal credentials, use [deploy keys](/authentication/connecting-to-github-with-ssh/managing-deploy-keys#deploy-keys) or a service account. Consider granting read-only permissions if that's all that is needed, and limit access as much as possible.

When generating a {% data variables.product.pat_v1 %}, select the fewest scopes necessary. When generating a {% data variables.product.pat_v2 %}, select the minimum permissions and repository access required.

Instead of using a {% data variables.product.pat_generic %}, consider using a {% data variables.product.prodname_github_app %}, which uses fine-grained permissions and short lived tokens, similar to a {% data variables.product.pat_v2 %}. Unlike a {% data variables.product.pat_generic %}, a {% data variables.product.prodname_github_app %} is not tied to a user, so the workflow will continue to work even if the user who installed the app leaves your organization. For more information, see [AUTOTITLE](/apps/creating-github-apps/authenticating-with-a-github-app/making-authenticated-api-requests-with-a-github-app-in-a-github-actions-workflow).

## Automatically redacted secrets

{% data variables.product.prodname_actions %} automatically redacts the contents of all {% data variables.product.prodname_dotcom %} secrets that are printed to workflow logs.

{% data variables.product.prodname_actions %} also redacts information that is recognized as sensitive, but is not stored as a secret. For a list of automatically redacted secrets, see [AUTOTITLE](/actions/reference/security/secrets#automatically-redacted-secrets).

Because there are multiple ways a secret value can be transformed, this redaction is not guaranteed. Additionally, the runner can only redact secrets used within the current job. As a result, there are certain security proactive steps you should follow to help ensure secrets are redacted, and to limit other risks associated with secrets. For a reference list of security best practices with secrets, see [AUTOTITLE](/actions/reference/security/secure-use#use-secrets-for-sensitive-information).

## Further reading

* [AUTOTITLE](/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets)
* [AUTOTITLE](/rest/actions/secrets)

---

## Included files

### `data/reusables/actions/secrets-org-level-overview.md`

````markdown
Organization-level secrets let you share secrets between multiple repositories, which reduces the need for creating duplicate secrets. Updating an organization secret in one location also ensures that the change takes effect in all repository workflows that use that secret.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.pat_v1 %}` | personal access token (classic) |
| `{% data variables.product.pat_v2 %}` | fine-grained personal access token |
| `{% data variables.product.pat_generic %}` | personal access token |
| `{% data variables.product.prodname_github_app %}` | GitHub App |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
