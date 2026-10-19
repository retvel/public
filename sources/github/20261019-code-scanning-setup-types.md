# Source Snapshot: About setup types for code scanning

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/code-security/concepts/code-scanning/setup-types
- **Upstream file:** [`github/docs` → `content/code-security/concepts/code-scanning/setup-types.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/code-security/concepts/code-scanning/setup-types.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/code-scanning/default-setup-pre-enablement-explanation.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/default-setup-pre-enablement-explanation.md); [`data/reusables/code-scanning/config-file-merged-with-default-setup.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/config-file-merged-with-default-setup.md); [`data/reusables/code-scanning/about-multiple-configurations-link.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/code-scanning/about-multiple-configurations-link.md); [`data/features/code-scanning-scheduled-scan-activity.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/code-scanning-scheduled-scan-activity.yml); [`data/features/code-scanning-inactive-repos.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/code-scanning-inactive-repos.yml); [`data/features/codeql-config-property.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/codeql-config-property.yml); [`data/features/codeql-custom-properties.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/codeql-custom-properties.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: About setup types for code scanning
shortTitle: Setup types
intro: Depending on your needs, {% data variables.product.github %} offers a default or advanced setup for {% data variables.product.prodname_code_scanning %}.
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
contentType: concepts
category:
  - Find and fix code vulnerabilities
---

## About default setup

Default setup for {% data variables.product.prodname_code_scanning %} is the quickest, easiest, most low-maintenance way to enable {% data variables.product.prodname_code_scanning %} for your repository. Based on the code in your repository, default setup will automatically create a custom {% data variables.product.prodname_code_scanning %} configuration. You can also customize this configuration, including at scale across your organization, without creating or maintaining a workflow file. See [Customization of default setup](#customization-of-default-setup).

With default setup, the code written in {% data variables.product.prodname_codeql %}-supported languages in your repository will be scanned using {% data variables.product.prodname_codeql %}:

* When you enable it.
* On each push to the repository's default branch, or any protected branch. For more information on protected branches, see [AUTOTITLE](/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches).
* When creating or committing to a pull request based against the repository's default branch, or any protected branch, excluding pull requests from forks.
* On a weekly schedule{% ifversion code-scanning-scheduled-scan-activity %}, if a push or pull request has triggered a scan in the last 180 days{% endif %}.
{%- ifversion code-scanning-inactive-repos %}
* Every 30 days for inactive repositories, when enabled by an organization owner. See [AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/configure-global-settings#continuing-scans-on-inactive-repositories).
{%- endif %}

{% ifversion code-scanning-scheduled-scan-activity %}

Weekly scheduled scans start only after a push or pull request triggers a scan with default setup enabled. The initial scan and scans triggered by configuration or language changes do not start or extend the weekly schedule. Pushes and pull requests from before default setup was enabled do not count.

{% endif %}

### Supported languages

{% data reusables.code-scanning.default-setup-pre-enablement-explanation %}

If the code in a repository changes to include any {% data variables.product.prodname_codeql %}-supported languages, {% data variables.product.prodname_dotcom %} will automatically update the {% data variables.product.prodname_code_scanning %} configuration to include the new language. If {% data variables.product.prodname_code_scanning %} fails with the new configuration, {% data variables.product.prodname_dotcom %} will resume the previous configuration automatically so the repository does not lose {% data variables.product.prodname_code_scanning %} coverage.

## Customization of default setup

After running an initial analysis of your code with default setup, you can make changes to your configuration to better meet your needs.

### Configuration options

For existing configurations of default setup, you can edit:

* Which languages default setup will analyze.
* The query suite run during analysis. For more information on the available query suites, see [AUTOTITLE](/code-security/concepts/code-scanning/codeql/codeql-query-suites).
* The threat models ({% data variables.release-phases.public_preview %}) to use for analysis. Your choice of threat model determines which sources of tainted data are treated as a risk to your application. During the {% data variables.release-phases.public_preview %}, threat models are supported only for analysis of {% data variables.code-scanning.code_scanning_threat_model_support %}. For more information about threat models, see [Including local sources of tainted data in default setup](/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/edit-default-setup#including-local-sources-of-tainted-data-in-default-setup).

If your codebase depends on a library or framework that is not recognized by the standard libraries included with {% data variables.product.prodname_codeql %}, you can also extend the {% data variables.product.prodname_codeql %} coverage in default setup using {% data variables.product.prodname_codeql %} model packs. For more information, see [Extending CodeQL coverage with CodeQL model packs in default setup](/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/edit-default-setup#extending-codeql-coverage-with-codeql-model-packs-in-default-setup).

{% ifversion codeql-config-property %}

You can also apply a custom {% data variables.product.prodname_codeql %} configuration file to default setup across your organization at once, or for a single repository, by setting the `github-codeql-config-file` repository property. {% data reusables.code-scanning.config-file-merged-with-default-setup %} This lets you meet customization needs that previously required advanced setup, while keeping the low-maintenance benefits of default setup. See [AUTOTITLE](/code-security/concepts/code-scanning/repository-properties#custom-configuration-files) and [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/edit-default-setup#customizing-default-setup-with-a-configuration-file).

{% endif %}

{% ifversion codeql-custom-properties %}

Additional configuration options that are shared between all {% data variables.product.prodname_code_scanning %} setup types are available. See [AUTOTITLE](/code-security/concepts/code-scanning/repository-properties).

{% endif %}

### Available runners

You can use default setup for all {% data variables.product.prodname_codeql %}-supported languages on self-hosted runners or {% data variables.product.prodname_dotcom %}-hosted runners.

You can assign self-hosted runners for default setup by giving the runners the default `code-scanning` label, or you can optionally give them custom labels so that individual repositories can use different runners.

Unless you have a specific use case, we recommend that you only assign runners with the default `code-scanning` label. However, you may want to use custom labels to:

* Assign more powerful self-hosted runners to critical repositories for faster {% data variables.product.prodname_code_scanning %} analysis.
* Run your {% data variables.product.prodname_code_scanning %} analyses on a particular platform (for example, macOS).
* Have granular control over the workload for your {% data variables.product.prodname_dotcom %}-hosted runners and self-hosted runners.

## About advanced setup

{% ifversion codeql-config-property %}If the customization options available for default setup, including a custom configuration file, don't meet your needs{% else %}If you need more granular control over your {% data variables.product.prodname_code_scanning %} configuration{% endif %}, you should instead configure advanced setup. Advanced setup for {% data variables.product.prodname_code_scanning %} is helpful when you need to define your own {% data variables.product.prodname_actions %} workflow, for example to build compiled languages, use a matrix build, or change the analysis schedule. You can set up {% data variables.product.prodname_code_scanning %} with {% data variables.product.prodname_actions %} or an external continuous integration or continuous delivery/deployment (CI/CD) system.

{% data reusables.code-scanning.about-multiple-configurations-link %}

### With {% data variables.product.prodname_actions %}

By creating and editing a {% data variables.product.prodname_actions %} workflow file, you can define how to build compiled languages, choose which queries to run, select the languages to scan, use a matrix build, and more. You also have access to all the options for controlling workflows, for example: changing the scan schedule, defining workflow triggers, specifying specialist runners to use.

{% ifversion ghes %}
Your site administrator can also make third-party actions available to users for {% data variables.product.prodname_code_scanning %}, by setting up {% data variables.product.prodname_github_connect %}. For more information, see [AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/configuring-code-scanning-for-your-appliance#configuring-github-connect-to-sync-github-actions).
{% endif %}

### With a third-party CI/CD system

As an alternative to running {% data variables.product.prodname_code_scanning %} within {% data variables.product.github %} using {% data variables.product.prodname_actions %}, you can analyze code in an external CI/CD system, then upload the results to {% data variables.product.github %}.

The {% data variables.product.prodname_codeql_cli %} is a standalone, command-line tool that you can use to analyze code. You can add the {% data variables.product.prodname_codeql_cli %} to your third-party system, or use another third-party static analysis tool that can produce results as Static Analysis Results Interchange Format (SARIF) 2.1.0 data. For more information, see [AUTOTITLE](/code-security/concepts/code-scanning/codeql/codeql-cli) and [AUTOTITLE](/code-security/reference/code-scanning/sarif-files/sarif-support).

Alerts for {% data variables.product.prodname_code_scanning %} that you generate externally are displayed in the same way as those for {% data variables.product.prodname_code_scanning %} that you generate within {% data variables.product.github %}.

## Next steps

You can enable default setup for a single repository, multiple repositories, or all repositories in an organization at the same time.

* For a single repository, see [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configure-code-scanning).
* For bulk enablement, see [AUTOTITLE](/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/code-scanning-at-scale).

To configure advanced setup instead, see [AUTOTITLE](/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configuring-advanced-setup-for-code-scanning).

---

## Included files

### `data/reusables/code-scanning/default-setup-pre-enablement-explanation.md`

````markdown
We recommend enabling default setup for eligible repositories if there is any chance the repositories will include at least one {% data variables.product.prodname_codeql %}-supported language in the future. If you enable default setup on a repository that does not include any {% data variables.product.prodname_codeql %}-supported languages, default setup will not run any scans or use any {% data variables.product.prodname_actions %} minutes. If {% data variables.product.prodname_codeql %}-supported languages are added to the repository's default branch, default setup will automatically begin scanning {% data variables.product.prodname_codeql %}-supported languages and using {% data variables.product.prodname_actions %} minutes. For more information on {% data variables.product.prodname_codeql %}-supported languages, see [AUTOTITLE](/code-security/concepts/code-scanning/codeql/codeql-code-scanning#about-codeql).
````

### `data/reusables/code-scanning/config-file-merged-with-default-setup.md`

````markdown
A custom configuration file applied using the `github-codeql-config-file` property is merged with the configuration that {% data variables.product.prodname_code_scanning %} default setup generates automatically. {% data variables.product.prodname_code_scanning_caps %} default setup allows you to customize some analysis settings in the user interface, such as which threat models or {% data variables.product.prodname_codeql %} model packs to use. These selections are kept in the merged configuration: the threat models selected in the default setup UI are combined with any threat models specified in the configuration file, and model packs configured in the UI are kept.
````

### `data/reusables/code-scanning/about-multiple-configurations-link.md`

````markdown
If you run code scanning using multiple configurations, an alert will sometimes have multiple analysis origins. If an alert has multiple analysis origins, you can view the status of the alert for each analysis origin on the alert page. For more information, see [AUTOTITLE](/code-security/concepts/code-scanning/code-scanning-alerts#about-alerts-from-multiple-configurations).
````

### `data/features/code-scanning-scheduled-scan-activity.yml`

````yaml
# Reference: https://github.com/github/code-scanning/issues/24741
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>=3.24'
````

### `data/features/code-scanning-inactive-repos.yml`

````yaml
# Ref: 22601
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>= 3.22'
````

### `data/features/codeql-config-property.yml`

````yaml
# Allows the CodeQL Action to use the `github-codeql-config-file` property.
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>= 3.23'
````

### `data/features/codeql-custom-properties.yml`

````yaml
# Allows the CodeQL Action to use repository properties.
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>= 3.21'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_code_scanning %}` | code scanning |
| `{% data variables.product.prodname_codeql %}` | CodeQL |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.release-phases.public_preview %}` | public preview |
| `{% data variables.code-scanning.code_scanning_threat_model_support %}` | Java/Kotlin and C# |
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_github_connect %}` | GitHub Connect |
| `{% data variables.product.prodname_codeql_cli %}` | CodeQL CLI |
| `{% data variables.product.prodname_code_scanning_caps %}` | Code scanning |
