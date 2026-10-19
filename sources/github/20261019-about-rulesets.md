# Source Snapshot: About rulesets

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets
- **Upstream file:** [`github/docs` → `content/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/gated-features/repo-rules.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/repo-rules.md); [`data/reusables/gated-features/more-info.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/more-info.md); [`data/reusables/repositories/repo-rules-permissions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/repo-rules-permissions.md); [`data/reusables/repositories/about-push-rule-delegated-bypass.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/about-push-rule-delegated-bypass.md); [`data/reusables/repositories/push-rulesets-overview.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/push-rulesets-overview.md); [`data/reusables/repositories/rulesets-push-rules-path-example.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/rulesets-push-rules-path-example.md); [`data/reusables/repositories/rulesets-push-rulesets-fork-network-information.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/rulesets-push-rulesets-fork-network-information.md); [`data/reusables/repositories/rulesets-convert-branch-protection-rule.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/rulesets-convert-branch-protection-rule.md); [`data/reusables/repositories/rulesets-about-enforcement-statuses.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/repositories/rulesets-about-enforcement-statuses.md); [`data/features/enterprise-code-rulesets.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/enterprise-code-rulesets.yml); [`data/features/push-rule-delegated-bypass.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/push-rule-delegated-bypass.yml); [`data/features/repo-rules-enterprise.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/repo-rules-enterprise.yml); [`data/features/push-rule-allowed-exceptions.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/push-rule-allowed-exceptions.yml); [`data/features/branch-protection-ruleset-conversion.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/branch-protection-ruleset-conversion.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About rulesets
intro: Rulesets help you to control how people can interact with branches and tags in a repository.
product: '{% data reusables.gated-features.repo-rules %}'
versions:
  fpt: '*'
  ghec: '*'
  ghes: '*'
permissions: '{% data reusables.repositories.repo-rules-permissions %}'
shortTitle: About rulesets
category:
  - Manage branches and protect code
---

## About rulesets

A ruleset is a named list of rules that applies to a repository or to multiple repositories in an organization for customers on {% data variables.product.prodname_team %} and {% data variables.product.prodname_enterprise %} plans. You can have up to 75 rulesets per repository, and 75 organization-wide rulesets.

When you create a ruleset, you can allow certain users to bypass the rules in the ruleset. This can be users with a certain role, such as repository administrator, or it can be specific teams or {% data variables.product.prodname_github_apps %}. For more information about granting bypass permissions, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/creating-rulesets-for-a-repository).

{% ifversion not ghes %}

For organizations on the {% data variables.product.prodname_enterprise %} plan, you can set up rulesets at the {% ifversion enterprise-code-rulesets %} enterprise or {% endif %}organization level to target multiple repositories in your organization. See [AUTOTITLE](/enterprise-cloud@latest/organizations/managing-organization-settings/managing-rulesets-for-repositories-in-your-organization){% ifversion not ghec %} in the {% data variables.product.prodname_ghe_cloud %} documentation{% endif %}.

{% endif %}

You can use rulesets to target branches or tags in a repository or to block pushes to a repository and the repository's entire fork network.

{% ifversion push-rule-delegated-bypass %}

{% data reusables.repositories.about-push-rule-delegated-bypass %}

{% endif %}

### Branch and tag rulesets

You can create rulesets to control how people can interact with selected branches and tags in a repository. You can control things like who can push commits to a certain branch{% ifversion repo-rules-enterprise %} and how the commits must be formatted{% endif %}, or who can delete or rename a tag. For example, you could set up a ruleset for your repository's `feature` branch that requires signed commits and blocks force pushes for all users except repository administrators.

For each ruleset you create, you specify which branches or tags in your repository{% ifversion repo-rules-enterprise %}, or which repositories in your organization,{% endif %} the ruleset applies to. You can use `fnmatch` syntax to define a pattern to target specific {% ifversion repo-rules-enterprise %}branches, tags, and repositories{% else %}branches and tags{% endif %}. For example, you could use the pattern `releases/**/*` to target all branches in your repository whose name starts with the string `releases/`. For more information on `fnmatch` syntax, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/creating-rulesets-for-a-repository#using-fnmatch-syntax).

### Push rulesets

{% data reusables.repositories.push-rulesets-overview %}

## About rulesets and protected branches

Rulesets and branch protection rules can both protect branches in a repository. They work alongside each other, and all applicable rules are enforced. For more information, see [About rule layering](#about-rule-layering).

Rulesets offer more flexible ways to manage and understand protections:

* Multiple rulesets can apply to the same branch at the same time, while only one branch protection rule applies.
* You can change a ruleset's enforcement status without deleting the ruleset.
* Anyone with read access to a repository can view its active rulesets. This helps developers understand which rules apply and allows auditors to review protections without administrator access.
* Rulesets can also control commit metadata, such as commit messages and author email addresses. For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets){% ifversion ghec %}."{% else %} in the {% data variables.product.prodname_ghe_cloud %} documentation.{% endif %}

{% data reusables.repositories.rulesets-convert-branch-protection-rule %}

## Using ruleset enforcement statuses

{% data reusables.repositories.rulesets-about-enforcement-statuses %}

## About rule layering

A ruleset does not have a priority. Instead, if multiple rulesets target the same branch or tag in a repository, the rules in each of these rulesets are aggregated. If the same rule is defined in different ways across the aggregated rulesets, the most restrictive version of the rule applies. As well as layering with each other, rulesets also layer with protection rules targeting the same branch or tag.

For example, consider the following situation for the `my-feature` branch of the `octo-org/octo-repo` repository.

* An administrator of the repository has set up a ruleset targeting the `my-feature` branch. This ruleset requires signed commits, and three reviews on pull requests before they can be merged.
* An existing branch protection rule for the `my-feature` branch requires a linear commit history, and two reviews on pull requests before they can be merged.{% ifversion repo-rules-enterprise %}
* An administrator of the `octo-org` organization has also set up a ruleset targeting the `my-feature` branch of the `octo-repo` repository. The ruleset blocks force pushes, and requires one review on pull requests before they can be merged.{% endif %}

The rules from each source are aggregated, and all rules apply. Where multiple different versions of the same rule exist, the result is that the most restrictive version of the rule applies. Therefore, the `my-feature` branch requires signed commits and a linear commit history{% ifversion repo-rules-enterprise %}, force pushes are blocked{% endif %}, and pull requests targeting the branch will require three reviews before they can be merged.

---

## Included files

### `data/reusables/gated-features/repo-rules.md`

````markdown
Rulesets are available in public repositories with {% data variables.product.prodname_free_user %} and {% data variables.product.prodname_free_team %} for organizations, and in public and private repositories with {% data variables.product.prodname_pro %}, {% data variables.product.prodname_team %}, and {% data variables.product.prodname_ghe_cloud %}. {% data reusables.gated-features.more-info %}

{% ifversion fpt %}Push rulesets are available for the {% data variables.product.prodname_team %} plan in internal and private repositories, and forks of repositories that have push rulesets enabled.{% else %}Push rulesets are available for the {% data variables.product.prodname_ghe_cloud %} plan in internal and private repositories, forks of repositories that have push rulesets enabled, and organizations in your enterprise.{% endif %}
````

### `data/reusables/gated-features/more-info.md`

````markdown
See [AUTOTITLE](/get-started/learning-about-github/githubs-plans).
````

### `data/reusables/repositories/repo-rules-permissions.md`

````markdown
Anyone with read access to a repository can view the repository's rulesets. People with admin access to a repository, or a custom role with the "edit repository rules" permission, can create, edit, and delete rulesets for a repository{% ifversion fpt %}.{% else %} and view ruleset insights. For more information, see [AUTOTITLE](/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/about-custom-repository-roles).{% endif %}
````

### `data/reusables/repositories/about-push-rule-delegated-bypass.md`

````markdown
Delegated bypass for push rulesets lets you control who can bypass push protection and which blocked pushes should be allowed.

 With delegated bypass, contributors to a repository must request "bypass privileges" when pushing commits that contain restricted content. The request is sent to a designated group of reviewers, who either approve or deny the request to bypass push rules.

If the request to bypass push rules is approved, the contributor can push the commit containing restricted content. If the request is denied, the contributor must remove the content from the commit (or commits) containing the restricted content before pushing again.

To configure delegated bypass, organization owners or repository administrators first create a "bypass list". The bypass list includes specific roles and teams, such as team or repository administrators, who oversee requests to bypass push protection. For more information, see [AUTOTITLE](/organizations/managing-organization-settings/managing-rulesets-for-repositories-in-your-organization) and [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets).
````

### `data/reusables/repositories/push-rulesets-overview.md`

````markdown
With push rulesets, you can block pushes to a private or internal repository and that repository's entire fork network based on file extensions, file path lengths, file and folder paths, and file sizes.

Push rules do not require any branch targeting because they apply to every push to the repository.

Push rulesets allow you to:

* **Restrict file paths:** Prevent commits that include changes in specified file paths from being pushed.

  {% data reusables.repositories.rulesets-push-rules-path-example %}
  
  {% ifversion push-rule-allowed-exceptions %}You can add allowed exceptions for paths that should remain pushable.{% endif %}
* **Restrict file path length:** Prevent commits that include file paths that exceed a specified character limit from being pushed.
* **Restrict file extensions:** Prevent commits that include files with specified file extensions from being pushed.
* **Restrict file size:** Prevent commits that exceed a specified file size limit from being pushed.{% ifversion push-rule-allowed-exceptions %} You can add allowed exceptions for files that may exceed the limit.{% endif %}

### About push rulesets for forked repositories

{% data reusables.repositories.rulesets-push-rulesets-fork-network-information %}
````

### `data/reusables/repositories/rulesets-push-rules-path-example.md`

````markdown
You can use `fnmatch` syntax for this. For example, a restriction targeting `test/demo/**/*` prevents any pushes to files or folders in the `test/demo/` directory. A restriction targeting `test/docs/pushrules.md` prevents pushes specifically to the `pushrules.md` file in the `test/docs/` directory. For more information, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/creating-rulesets-for-a-repository#using-fnmatch-syntax).
````

### `data/reusables/repositories/rulesets-push-rulesets-fork-network-information.md`

````markdown
Push rules apply to the entire fork network for a repository, ensuring every entry point to the repository is protected. For example, if you fork a repository that has push rulesets enabled, the same push rulesets will also apply to your forked repository.

For a forked repository, the only people who have bypass permissions for a push rule are the people who have bypass permissions in the root repository.
````

### `data/reusables/repositories/rulesets-convert-branch-protection-rule.md`

````markdown
{% ifversion branch-protection-ruleset-conversion %}To convert an existing branch protection rule to rulesets, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/converting-branch-protections-to-rulesets).{% endif %}
````

### `data/reusables/repositories/rulesets-about-enforcement-statuses.md`

````markdown
While creating or editing your ruleset, you can use enforcement statuses to configure how your ruleset will be enforced.

You can select any of the following enforcement statuses for your ruleset.

   * **{% octicon "play" aria-hidden="true" aria-label="play" %} Active:** your ruleset will be enforced upon creation.{% ifversion repo-rules-enterprise %}
   * **{% octicon "meter" aria-hidden="true" aria-label="meter" %} Evaluate:** your ruleset will not be enforced, but you will be able to monitor which actions would or would not violate rules on the "Rule Insights" page.{% endif %}
   * **{% octicon "skip" aria-hidden="true" aria-label="skip" %} Disabled:** your ruleset will not be enforced{% ifversion repo-rules-enterprise %} or evaluated{% endif %}.

{% ifversion repo-rules-enterprise %}

Using "Evaluate" mode is a great option for testing your ruleset without enforcing it. You can use the "Rule Insights" page to see if the contribution would have violated the rule.

{% endif %}
````

### `data/features/enterprise-code-rulesets.yml`

````yaml
# Reference: #16569
# Enterprise code rulesets
versions:
  ghec: '*'
````

### `data/features/push-rule-delegated-bypass.yml`

````yaml
# issue 14684 push rule delegated bypass
versions:
  ghec: '*'
  ghes: '>3.15'
````

### `data/features/repo-rules-enterprise.yml`

````yaml
# Reference: #9228
# Public beta for repository rulesets.
# Feature flag for enterprise-only features (metadata restrictions, setting rulesets at org level, ruleset insights)
versions:
  ghec: '*'
  ghes: '>3.10'
````

### `data/features/push-rule-allowed-exceptions.yml`

````yaml
# Reference: github/releases#9966
# "Allowed exceptions" (ignored_file_paths) for the Restrict file paths
# and Restrict file size push rules.
# GHES availability TBC — add a ghes key once confirmed.
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/branch-protection-ruleset-conversion.yml`

````yaml
# Reference: docs-content#23257
# Convert a repository's branch protections to rulesets
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>=3.23'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_enterprise %}` | GitHub Enterprise |
| `{% data variables.product.prodname_github_apps %}` | GitHub Apps |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.prodname_free_user %}` | GitHub Free |
| `{% data variables.product.prodname_free_team %}` | GitHub Free |
| `{% data variables.product.prodname_pro %}` | GitHub Pro |
