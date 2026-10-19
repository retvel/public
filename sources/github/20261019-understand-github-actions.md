# Source Snapshot: Understanding GitHub Actions

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/actions/get-started/understand-github-actions
- **Upstream file:** [`github/docs` → `content/actions/get-started/understand-github-actions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/actions/get-started/understand-github-actions.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/actions/enterprise-github-hosted-runners.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/enterprise-github-hosted-runners.md); [`data/reusables/actions/about-actions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/about-actions.md); [`data/reusables/actions/about-workflows-long.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/about-workflows-long.md); [`data/reusables/actions/internal-actions-summary.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/internal-actions-summary.md); [`data/reusables/actions/onboarding-next-steps.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/actions/onboarding-next-steps.md); [`data/features/actions-nga.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-nga.yml); [`data/features/actions-hosted-runners.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-hosted-runners.yml); [`data/features/copilot.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/copilot.yml); [`data/features/internal-actions.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/internal-actions.yml); [`data/features/github-certification.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/github-certification.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Understanding GitHub Actions
shortTitle: Understand GitHub Actions
intro: Learn the basics of core concepts and essential terminology in {% data variables.product.prodname_actions %}.
redirect_from:
  - /github/automating-your-workflow-with-github-actions/core-concepts-for-github-actions
  - /actions/automating-your-workflow-with-github-actions/core-concepts-for-github-actions
  - /actions/getting-started-with-github-actions/core-concepts-for-github-actions
  - /actions/learn-github-actions/introduction-to-github-actions
  - /actions/learn-github-actions/understanding-github-actions
  - /actions/learn-github-actions/essential-features-of-github-actions
  - /articles/getting-started-with-github-actions
  - /actions/about-github-actions/understanding-github-actions
  - /actions/get-started/understanding-github-actions
  - /enterprise-onboarding/github-actions-for-your-enterprise/actions-components
  - /enterprise-onboarding/github-actions-for-your-enterprise/understanding-github-actions
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
contentType: get-started
category:
  - Get started with GitHub Actions
---

{% data reusables.actions.enterprise-github-hosted-runners %}

## Overview

{% data reusables.actions.about-actions %} You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

{% data variables.product.prodname_actions %} goes beyond just DevOps and lets you run workflows when other events happen in your repository. For example, you can run a workflow to automatically add the appropriate labels whenever someone creates a new issue in your repository.

{% ifversion fpt or ghec %}

{% data variables.product.prodname_dotcom %} provides Linux, Windows, and macOS virtual machines to run your workflows, or you can host your own self-hosted runners in your own data center or cloud infrastructure.

{% elsif ghes %}

You must host your own Linux, Windows, or macOS virtual machines to run workflows for {% data variables.location.product_location %}.

{% endif %}

{% ifversion ghec or ghes %}

For more information about introducing {% data variables.product.prodname_actions %} to your enterprise, see [AUTOTITLE](/admin/managing-github-actions-for-your-enterprise/getting-started-with-github-actions-for-your-enterprise/introducing-github-actions-to-your-enterprise).

{% endif %}

## The components of {% data variables.product.prodname_actions %}

You can configure a {% data variables.product.prodname_actions %} **workflow** to be triggered when an **event** occurs in your repository, such as a pull request being opened or an issue being created. Your workflow contains one or more **jobs** which can run in sequential order or in parallel. Each job will run inside its own virtual machine **runner**, or inside a container, and has one or more **steps** that either run a script that you define or run an **action**, which is a reusable extension that can simplify your workflow.

![Diagram of an event triggering Runner 1 to run Job 1, which triggers Runner 2 to run Job 2. Each of the jobs is broken into multiple steps.](assets/overview-actions-simple.png)

### Workflows

{% data reusables.actions.about-workflows-long %}

You can reference a workflow within another workflow. For more information, see [AUTOTITLE](/actions/how-tos/reuse-automations/reuse-workflows).

For more information, see [AUTOTITLE](/actions/how-tos/write-workflows).

### Events

An **event** is a specific activity in a repository that triggers a **workflow** run. For example, an activity can originate from {% data variables.product.prodname_dotcom %} when someone creates a pull request, opens an issue, or pushes a commit to a repository. You can also trigger a workflow to run on a [schedule](/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule), by [posting to a REST API](/rest/repos/repos#create-a-repository-dispatch-event), or manually.

For a complete list of events that can be used to trigger workflows, see [Events that trigger workflows](/actions/reference/workflows-and-actions/events-that-trigger-workflows).

### Jobs

A **job** is a set of **steps** in a workflow that is executed on the same **runner**. Each step is either a shell script that will be executed, or an **action** that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another. For example, you can have a step that builds your application followed by a step that tests the application that was built.

{% ifversion actions-nga %}
Steps run in order by default, but you can also run selected steps concurrently when your workflow benefits from parallel execution, such as starting a long-running service while later steps continue. For more information, see [AUTOTITLE](/actions/reference/workflows-and-actions/workflow-syntax#jobsjob_idstepsbackground).
{% endif %}

You can configure a job's dependencies with other jobs; by default, jobs have no dependencies and run in parallel. When a job takes a dependency on another job, it waits for the dependent job to complete before running.

You can also use a **matrix** to run the same job multiple times, each with a different combination of variables—like operating systems or language versions.

For example, you might configure multiple build jobs for different architectures without any job dependencies and a packaging job that depends on those builds. The build jobs run in parallel, and once they complete successfully, the packaging job runs.

For more information, see [AUTOTITLE](/actions/how-tos/write-workflows/choose-what-workflows-do).

### Actions

An **action** is a pre-defined, reusable set of jobs or code that performs specific tasks within a **workflow**, reducing the amount of repetitive code you write in your workflow files. Actions can perform tasks such as:

* Pulling your Git repository from {% data variables.product.prodname_dotcom %}
* Setting up the correct toolchain for your build environment
* Setting up authentication to your cloud provider

You can write your own actions, or you can find actions to use in your workflows in the {% data variables.product.prodname_marketplace %}.

{% data reusables.actions.internal-actions-summary %}

For more information on actions, see [AUTOTITLE](/actions/how-tos/reuse-automations).

### Runners

A **runner** is a server that runs your workflows when they're triggered. Each runner can run a single **job** at a time.
{% ifversion ghes %} You must host your own runners for {% data variables.product.prodname_ghe_server %}.
{% elsif fpt or ghec %}{% data variables.product.company_short %} provides Ubuntu Linux, Microsoft Windows, and macOS runners to run your **workflows**. Each workflow run executes in a fresh, newly-provisioned virtual machine.

{% ifversion actions-hosted-runners %} {% data variables.product.prodname_dotcom %} also offers {% data variables.actions.hosted_runner %}s, which are available in larger configurations. For more information, see [AUTOTITLE](/actions/how-tos/manage-runners/larger-runners).
{% endif %}
If you need a different operating system or require a specific hardware configuration, you can host your own runners.
{% endif %}

For more information{% ifversion fpt or ghec %} about self-hosted runners{% endif %}, see [AUTOTITLE](/actions/how-tos/manage-runners/self-hosted-runners).

## Next steps

{% data reusables.actions.onboarding-next-steps %}

{% ifversion copilot %}

> [!NOTE]
> For automations that require contextual judgment about your repository's content, you can also author {% data variables.copilot.agentic_workflows_short %} in natural language instead of a traditional {% data variables.product.prodname_actions %} workflow. For more information, see [AUTOTITLE](/copilot/how-tos/github-agentic-workflows/quickstart) and [AUTOTITLE](/copilot/how-tos/github-agentic-workflows/creating-github-agentic-workflows).

{% endif %}

{% ifversion ghec or ghes %}

## Further reading

* [AUTOTITLE](/admin/managing-github-actions-for-your-enterprise/getting-started-with-github-actions-for-your-enterprise/about-github-actions-for-enterprises)
{% endif %}

---

## Included files

### `data/reusables/actions/enterprise-github-hosted-runners.md`

````markdown
{% ifversion ghes %}

> [!NOTE]
> {% data variables.product.prodname_ghe_server %} users should use self-hosted runners. {% data variables.product.prodname_dotcom %}-hosted runners are **not** supported.

{% endif %}
````

### `data/reusables/actions/about-actions.md`

````markdown
{% data variables.product.prodname_actions %} is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline.
````

### `data/reusables/actions/about-workflows-long.md`

````markdown
A **workflow** is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule.

Workflows are defined in the `.github/workflows` directory in a repository. A repository can have multiple workflows, each of which can perform a different set of tasks such as:
* Building and testing pull requests
* Deploying your application every time a release is created
* Adding a label whenever a new issue is opened
````

### `data/reusables/actions/internal-actions-summary.md`

````markdown
{% ifversion internal-actions %}
To share actions across your enterprise without publishing the actions publicly, you can store the actions in an internal repository, then configure the repository to allow access to {% data variables.product.prodname_actions %} workflows in other repositories owned by the same organization or by any organization in the enterprise. For more information, see [AUTOTITLE](/actions/how-tos/reuse-automations/share-with-your-enterprise).
{% endif %}
````

### `data/reusables/actions/onboarding-next-steps.md`

````markdown
{% data variables.product.prodname_actions %} can help you automate nearly every aspect of your application development processes. Ready to get started? Here are some helpful resources for taking your next steps with {% data variables.product.prodname_actions %}:

* To create a {% data variables.product.prodname_actions %} workflow, see [AUTOTITLE](/actions/how-tos/write-workflows/use-workflow-templates).
* For continuous integration (CI) workflows, see [AUTOTITLE](/actions/tutorials/build-and-test-code).
* For building and publishing packages, see [AUTOTITLE](/actions/tutorials/publish-packages).
* For deploying projects, see [AUTOTITLE](/actions/how-tos/deploy/deploy-to-third-party-platforms).
* For automating tasks and processes on {% data variables.product.prodname_dotcom %}, see [AUTOTITLE](/actions/tutorials/manage-your-work).
* For examples that demonstrate more complex features of {% data variables.product.prodname_actions %}, see [AUTOTITLE](/actions/how-tos/write-workflows/choose-what-workflows-do). These detailed examples explain how to test your code on a runner, access the {% data variables.product.prodname_dotcom %} CLI, and use advanced features such as concurrency and test matrices.{% ifversion github-certification %}
* To certify your proficiency in automating workflows and accelerating development with {% data variables.product.prodname_actions %}, earn a {% data variables.product.prodname_actions %} certificate with {% data variables.product.prodname_certifications %}. For more information, see [AUTOTITLE](/get-started/showcase-your-expertise-with-github-certifications/about-github-certifications).{% endif %}
````

### `data/features/actions-nga.yml`

````yaml
# New feature: actions-nga
# Versioning for Actions NGA (Next Generation Architecture) features
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/actions-hosted-runners.yml`

````yaml
# Reference: #6458
# Larger GitHub-hosted runners
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/copilot.yml`

````yaml
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/internal-actions.yml`

````yaml
versions:
  ghec: '*'
  ghes: '>=3.5'
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
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.product.prodname_marketplace %}` | GitHub Marketplace |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.actions.hosted_runner %}` | larger runner |
| `{% data variables.copilot.agentic_workflows_short %}` | agentic workflows |
| `{% data variables.product.prodname_certifications %}` | GitHub Certifications |
