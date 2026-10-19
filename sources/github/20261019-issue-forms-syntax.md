# Source Snapshot: Syntax for issue forms

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms
- **Upstream file:** [`github/docs` → `content/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/community/issue-forms-beta.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/community/issue-forms-beta.md); [`data/reusables/actions/learn-more-about-yaml.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/learn-more-about-yaml.md); [`data/reusables/community/issue-forms-sample.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/community/issue-forms-sample.md); [`data/features/issue-form-upload.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/issue-form-upload.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Syntax for issue forms
intro: 'You can define different input types, validations, default assignees, and default labels for your issue forms.'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Create issue and pull request templates
---

{% data reusables.community.issue-forms-beta %}

## About YAML syntax for issue forms

You can create custom issue forms by adding a YAML form definition file to the `/.github/ISSUE_TEMPLATE` folder in your repository. {% data reusables.actions.learn-more-about-yaml %} You can define different input types, validations, default assignees, and default labels for your issue forms.

When a contributor fills out an issue form, their responses for each input are converted to markdown and added to the body of an issue. Contributors can edit their issues that were created with issue forms and other people can interact with the issues like an issue created through other methods.

Issue forms are not supported for pull requests. You can create pull request templates in your repositories for collaborators to use. For more information, see [AUTOTITLE](/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository).

This example YAML configuration file defines an issue form using several inputs to report a bug.

{% data reusables.community.issue-forms-sample %}

## Top-level syntax

All issue form configuration files must begin with `name`, `description`, and `body` key-value pairs.

```yaml copy
name:
description:
body:
```

You can set the following top-level keys for each issue form.

| Key | Description | Required | Type |
| :-- | :-- | :-- | :-- |
| `name` | A name for the issue form template. Must be unique from all other templates, including Markdown templates. | Required | String |
| `description` | A description for the issue form template, which appears in the template chooser interface. | Required | String |
| `body` | Definition of the input types in the form. | Required | Array |
| `assignees` | People who will be automatically assigned to issues created with this template. | Optional | Array or comma-delimited string |
| `labels` | Labels that will automatically be added to issues created with this template. If a label does not already exist in the repository, it will not be automatically added to the issue. | Optional | Array or comma-delimited string |
| `title` | A default title that will be pre-populated in the issue submission form. | Optional | String |
| `type` |  The issue type that will be automatically added to issues created with this template. Issue types are defined at the organization level and can be used to create a shared syntax across repos. | Optional | String |
| `projects` | Projects that any issues created with this template will automatically be added to. The format of this key is `PROJECT-OWNER/PROJECT-NUMBER`. > [!NOTE] The person opening the issue must have write permissions for the specified projects. If you don't expect people using this template to have write access, consider enabling your project's auto-add workflow. For more information, see [Adding items automatically](/issues/planning-and-tracking-with-projects/automating-your-project/adding-items-automatically). | Optional | Array or comma-delimited string |

For the available `body` input types and their syntaxes, see [AUTOTITLE](/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-githubs-form-schema).

## Converting a Markdown issue template to a YAML issue form template

You can use both Markdown and YAML issue templates in your repository. If you want to convert a Markdown issue template to a YAML issue form template, you must create a new YAML file to define the issue form. You can manually transpose an existing Markdown issue template to a YAML issue form. For more information, see [AUTOTITLE](/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository#creating-issue-forms).

If you want to use the same file name for your YAML issue form, you must delete the Markdown issue template when you commit the new file to your repository.

An example of a Markdown issue template and a corresponding YAML issue form template are below.

### Markdown issue template

```markdown copy
---
name: 🐞 Bug
about: File a bug/issue
title: '[BUG] <title>'
labels: Bug, Needs Triage
assignees: ''

---

{% raw %}<{% endraw %}!--
Note: Please search to see if an issue already exists for the bug you encountered.
--{% raw %}>{% endraw %}

### Current Behavior:
{% raw %}<{% endraw %}!-- A concise description of what you're experiencing. --{% raw %}>{% endraw %}

### Expected Behavior:
{% raw %}<{% endraw %}!-- A concise description of what you expected to happen. --{% raw %}>{% endraw %}

### Steps To Reproduce:
{% raw %}<{% endraw %}!--
Example: steps to reproduce the behavior:
1. In this environment...
1. With this config...
1. Run '...'
1. See error...
--{% raw %}>{% endraw %}

### Environment:
{% raw %}<{% endraw %}!--
Example:
- OS: Ubuntu 20.04
- Node: 13.14.0
- npm: 7.6.3
--{% raw %}>{% endraw %}

### Anything else:
{% raw %}<{% endraw %}!--
Links? References? Anything that will give us more context about the issue that you are encountering!
--{% raw %}>{% endraw %}
```

### YAML issue form template

```yaml copy
name: 🐞 Bug
description: File a bug/issue
title: "[BUG] <title>"
labels: ["Bug", "Needs Triage"]
body:
- type: checkboxes
  attributes:
    label: Is there an existing issue for this?
    description: Please search to see if an issue already exists for the bug you encountered.
    options:
    - label: I have searched the existing issues
      required: true
- type: textarea
  attributes:
    label: Current Behavior
    description: A concise description of what you're experiencing.
  validations:
    required: false
- type: textarea
  attributes:
    label: Expected Behavior
    description: A concise description of what you expected to happen.
  validations:
    required: false
- type: textarea
  attributes:
    label: Steps To Reproduce
    description: Steps to reproduce the behavior.
    placeholder: |
      1. In this environment...
      1. With this config...
      1. Run '...'
      1. See error...
  validations:
    required: false
- type: textarea
  attributes:
    label: Environment
    description: |
      examples:
        - **OS**: Ubuntu 20.04
        - **Node**: 13.14.0
        - **npm**: 7.6.3
    value: |
        - OS:
        - Node:
        - npm:
    render: markdown
  validations:
    required: false
- type: textarea
  attributes:
    label: Anything else?
    description: |
      Links? References? Anything that will give us more context about the issue you are encountering!

      Tip: You can attach images or log files by clicking this area to highlight it and then dragging files in.
  validations:
    required: false
```

## Further reading

* [YAML](https://yaml.org/)
* [Common validation errors when creating issue forms](/communities/using-templates-to-encourage-useful-issues-and-pull-requests/common-validation-errors-when-creating-issue-forms)

---

## Included files

### `data/reusables/community/issue-forms-beta.md`

````markdown
> [!NOTE]
> Issue forms are currently in {% data variables.release-phases.public_preview %} and subject to change.
````

### `data/reusables/actions/learn-more-about-yaml.md`

````markdown
If you're new to YAML and want to learn more, see [Learn YAML in Y minutes](https://learnxinyminutes.com/docs/yaml/).
````

### `data/reusables/community/issue-forms-sample.md`

````markdown
```yaml copy
name: Bug Report
description: File a bug report.
title: "[Bug]: "
labels: ["bug", "triage"]
projects: ["octo-org/1", "octo-org/44"]
assignees:
  - octocat
type: bug
body:
  - type: markdown
    attributes:
      value: |
        Thanks for taking the time to fill out this bug report!
  - type: input
    id: contact
    attributes:
      label: Contact Details
      description: How can we get in touch with you if we need more info?
      placeholder: ex. email@example.com
    validations:
      required: false
  - type: textarea
    id: what-happened
    attributes:
      label: What happened?
      description: Also tell us, what did you expect to happen?
      placeholder: Tell us what you see!
      value: "A bug happened!"
    validations:
      required: true
  - type: dropdown
    id: version
    attributes:
      label: Version
      description: What version of our software are you running?
      options:
        - 1.0.2 (Default)
        - 1.0.3 (Edge)
      default: 0
    validations:
      required: true
  - type: dropdown
    id: browsers
    attributes:
      label: What browsers are you seeing the problem on?
      multiple: true
      options:
        - Firefox
        - Chrome
        - Safari
        - Microsoft Edge
  - type: textarea
    id: logs
    attributes:
      label: Relevant log output
      description: Please copy and paste any relevant log output. This will be automatically formatted into code, so no need for backticks.
      render: shell
  - type: checkboxes
    id: terms
    attributes:
      label: Code of Conduct
      description: By submitting this issue, you agree to follow our [Code of Conduct](https://example.com).
      options:
        - label: I agree to follow this project's Code of Conduct
          required: true{% ifversion issue-form-upload %}
  - type: upload
    id: screenshots
    attributes:
      label: Upload screenshots
      description: If applicable, add screenshots to help explain your problem.
    validations:
      required: false{% endif %}
```
````

### `data/features/issue-form-upload.yml`

````yaml
# Reference: https://github.com/github/releases/issues/7534
# File upload field in issue forms
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>= 3.21'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.release-phases.public_preview %}` | public preview |
