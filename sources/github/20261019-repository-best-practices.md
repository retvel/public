# Source Snapshot: Best practices for repositories

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/repositories/creating-and-managing-repositories/best-practices-for-repositories
- **Upstream file:** [`github/docs` → `content/repositories/creating-and-managing-repositories/best-practices-for-repositories.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/repositories/creating-and-managing-repositories/best-practices-for-repositories.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/repositories/about-READMEs.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/about-READMEs.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Best practices for repositories
shortTitle: Best practices
intro: Learn how to use repositories effectively and securely.
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Create and set up a repository
---

## Create a README file

To make it easier for people to understand and navigate your work, we recommend that you create a README file for every repository.

{% data reusables.repositories.about-READMEs %} For more information, see [AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes).

## Secure your repository

You should secure your repository using {% data variables.product.github %}'s available security features to protect your code from vulnerabilities, unauthorized access, and other potential security threats. At a minimum, you should enable the following features{% ifversion fpt or ghec %}, which are available for **free for public repositories**{% endif %}:

* **{% data variables.product.prodname_dependabot_alerts %}** notify you of security vulnerabilities in your project's dependency network, so that you can update the affected dependency to a more secure version.
* **{% data variables.product.prodname_secret_scanning_caps %}** scans your repository for secrets (such as API keys and tokens) and alerts you if a secret is found, so that you can remove the secret from your repository.
* **Push protection** prevents you (and your collaborators) from introducing secrets to the repository in the first place, by blocking pushes containing supported secrets.
* **{% data variables.product.prodname_code_scanning_caps %}** identifies vulnerabilities and errors in your repository's code, so that you can fix these issues early and prevent a vulnerability or error being exploited by malicious actors.

Additionally, you might also consider:

* Adding a `SECURITY.md` file to your repository. The `SECURITY.md` file provides instructions to collaborators on how to report security vulnerabilities found in your project and encourages responsible disclosure.{% ifversion fpt or ghec %}
* Enabling "Private vulnerability reporting" for the repository, which lets collaborators and security researchers privately disclose vulnerabilities found in your repository to you.{% endif %}

For more information, see [AUTOTITLE](/code-security/getting-started/quickstart-for-securing-your-repository).

## Favor branching over forking

To streamline collaboration, we recommend that regular collaborators work from a single repository, creating pull requests between branches instead of between repositories. Forking is best suited for accepting contributions from people that are unaffiliated with a project, such as open-source contributors.

To maintain quality of important branches, such as `main`, while using a branching workflow, you can use protected branches with required status checks and pull request reviews. For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches).

## Use {% data variables.large_files.product_name_long %}

To optimize performance, {% data variables.product.prodname_dotcom %} limits the sizes of files allowed in repositories. For more information, see [AUTOTITLE](/repositories/working-with-files/managing-large-files/about-large-files-on-github).

To track large files in a Git repository, we recommend using {% data variables.large_files.product_name_long %} ({% data variables.large_files.product_name_short %}). For more information, see [AUTOTITLE](/repositories/working-with-files/managing-large-files/about-git-large-file-storage).

## Hands-on practice

Try the [Introduction to Repository Management](https://github.com/skills/introduction-to-repository-management/) Skills exercise for practical experience with repository management.

---

## Included files

### `data/reusables/repositories/about-READMEs.md`

````markdown
You can add a README file to a repository to communicate important information about your project. A README, along with a repository license, citation file, contribution guidelines, and a code of conduct, communicates expectations for your project and helps you manage contributions.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_dependabot_alerts %}` | Dependabot alerts |
| `{% data variables.product.prodname_secret_scanning_caps %}` | Secret scanning |
| `{% data variables.product.prodname_code_scanning_caps %}` | Code scanning |
| `{% data variables.large_files.product_name_long %}` | Git Large File Storage |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.large_files.product_name_short %}` | Git LFS |
