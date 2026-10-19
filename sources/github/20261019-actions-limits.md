# Source Snapshot: Actions limits

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/actions/reference/limits
- **Upstream file:** [`github/docs` → `content/actions/reference/limits.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/actions/reference/limits.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/billing/actions-included-quotas.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/billing/actions-included-quotas.md); [`data/reusables/rest-api/primary-rate-limit-unauthenticated-users.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/rest-api/primary-rate-limit-unauthenticated-users.md); [`data/reusables/rest-api/primary-rate-limit-authenticated-users.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/rest-api/primary-rate-limit-authenticated-users.md); [`data/reusables/rest-api/primary-rate-limit-github-app-installations.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/rest-api/primary-rate-limit-github-app-installations.md); [`data/reusables/rest-api/primary-rate-limit-oauth-apps.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/rest-api/primary-rate-limit-oauth-apps.md); [`data/reusables/rest-api/primary-rate-limit-github-token-in-actions.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/rest-api/primary-rate-limit-github-token-in-actions.md); [`data/features/actions-nga.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/actions-nga.yml); [`data/features/enterprise-installed-apps.yml`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/features/enterprise-installed-apps.yml)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Actions limits
intro: There are limits in {% data variables.product.prodname_actions %} which you may hit as you scale up, some may be increased by contacting support.
redirect_from:
  - /actions/monitoring-and-troubleshooting-workflows/troubleshooting-workflows/actions-limits
  - /actions/hosting-your-own-runners/managing-self-hosted-runners/usage-limits-for-self-hosted-runners
  - /actions/reference/usage-limits-for-self-hosted-runners
  - /actions/reference/actions-limits
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Limits
category:
  - Administer GitHub Actions
contentType: reference
---

You may be rate limited by {% data variables.product.prodname_actions %} when you scale your usage. Some limits can be increased by contacting {% data variables.contact.contact_support %}.

Unless otherwise stated, the expected behavior when a limit is reached is that the workflow/job will get cancelled.

These limits are subject to change.

## Existing system limits

| Limit category | Limit | Threshold | Description | Can {% data variables.product.github %} Support increase? |
| :---- | :---- | :---- | :---- | :---- |
| Workflow execution limit | Workflow run time | 35 days / workflow run | If a workflow run reaches this limit, the workflow run is cancelled. This period includes execution duration, and time spent on waiting and approval. | {% octicon "x" aria-label="No" %} |
| Workflow execution limit | Gate approval time | 30 days | A workflow may wait for up to [30 days on environment approvals](/actions/reference/workflows-and-actions/deployments-and-environments#wait-timer). | {% octicon "x" aria-label="No" %} |
| Workflow execution limit | Job Matrix | 256 jobs / workflow run | A job matrix can generate a maximum of 256 jobs per workflow run. This limit applies to both {% data variables.product.github %}-hosted and self-hosted runners. | {% octicon "x" aria-label="No" %} |
| Workflow execution limit | Re-run | 50 re-runs | A workflow run can be re-run a maximum of 50 times. This limit includes both full re-runs and re-runs of a subset of jobs. | {% octicon "check" aria-label="Yes" %} Support ticket |
| Workflow file | Workflow file size | 500 KB per file | A workflow file larger than 500 KB will not start runs. See [Workflow file size](#workflow-file-size). | {% octicon "x" aria-label="No" %} |
| Checks | Check runs per check suite | 50,000 check runs / check suite | A check suite can have a maximum of 50,000 check runs. This limit applies to check runs created through the Checks API and by {% data variables.product.prodname_actions %} workflow runs. When a check suite reaches this limit, additional check runs cannot be created for that check suite. | {% octicon "check" aria-label="Yes" %} Support ticket |
| Workflows queuing | Workflow trigger event rate limit | 1500 events / 10 seconds / repository | Each repository is limited to events triggering a workflow run. | {% octicon "check" aria-label="Yes" %} Support ticket |
| Workflows queuing | Workflow run queued | 500 workflow runs / 10 seconds | When the limit is reached, the workflow runs that were supposed to be triggered by the webhook events will be blocked and will not be queued. Reusable workflows are viewed as a single entity. For example, a run with 30 reusable workflows counts as 1 in this instance. | {% octicon "x" aria-label="No" %} |
| {% ifversion actions-nga %} |
| Workflows queuing | Concurrency group queue | 100 workflow runs / concurrency group | When using `queue: max` in the `concurrency` section, up to 100 jobs or workflow runs can be queued per concurrency group. Runs beyond this limit will be rejected. | {% octicon "x" aria-label="No" %} |
| {% endif %} |
| Self-hosted | Runner registrations | 1500 runners / 5 minutes / repository/org/enterprise | Runners can be registered per repository/organization/enterprise. | {% octicon "check" aria-label="Yes" %} Support ticket |
| Self-hosted | Runners per runner group | 10,000 runners | Runners registered at the same time per runner group. | {% octicon "x" aria-label="No" %} |
| Self-hosted | Job execution time | 5 days | Each job in a workflow can run for up to 5 days of execution time. If a job reaches this limit, the job is terminated and fails. | {% octicon "x" aria-label="No" %} |
| Self-hosted | Job queue time | 24 hours | A job can be in the queue for 24 hours before it is automatically cancelled. | {% octicon "x" aria-label="No" %} |
| All {% data variables.product.github %}-hosted runners | Job Concurrency | Varies | See [Job concurrency limits for {% data variables.product.github %}-hosted runners](#job-concurrency-limits-for-github-hosted-runners). | {% octicon "check" aria-label="Yes" %} Support ticket |
| All {% data variables.product.github %}-hosted runners | Job execution time | 6 hours | Each job in a workflow can run for up to 6 hours of execution time. If a job reaches this limit, the job is terminated and fails. | {% octicon "x" aria-label="No" %} |
| {% ifversion fpt or ghec %} |
| All {% data variables.product.github %}-hosted runners | Storage limits | Varies | For more information, see [Storage limits for all {% data variables.product.github %}-hosted runners](#storage-limits-for-all-github-hosted-runners). | {% octicon "x" aria-label="No" %} |
| {% endif %} |
| Larger runners | Per runner concurrency limit | Varies by runner type | Established when setting up a runner. Normally 1,000 max for Linux CPU runners, but varies by type. See [Job concurrency limits for {% data variables.product.github %}-hosted runners](#job-concurrency-limits-for-github-hosted-runners). | {% octicon "check" aria-label="Yes" %} Support ticket |
| Larger runners | Static IP limits | 10 IPs | 10 IPs per enterprise and organization. | {% octicon "check" aria-label="Yes" %} Support ticket |
| Larger runners | Private IP scaling for vnet injection | 30% buffer | You need a buffer to accommodate the maximum job concurrency you anticipate. See [Private IP scaling for vnet injection on larger runners](#private-ip-scaling-for-vnet-injection-on-larger-runners). | {% octicon "check" aria-label="Yes" %} Configurable Azure virtual network |
| Dependency caching | Uploads per minute | 200 per minute | Each repository is limited to 200 cache entry uploads per minute. If this limit is exceeded, subsequent cache upload attempts will fail until the rate limit resets. | {% octicon "x" aria-label="No" %} |
| Dependency caching | Downloads per minute | 1500 per minute | Each repository is limited to 1500 cache entry downloads per minute. If this limit is exceeded, subsequent cache download attempts will fail until the rate limit resets. | {% octicon "x" aria-label="No" %} |
| Dependency caching | Deletes per minute | 400 per minute | Each repository is limited to 400 cache delete operations per minute. If this limit is exceeded, subsequent cache delete attempts will fail until the rate limit resets. Each request to delete caches either by key or by ID counts towards this limit. | {% octicon "x" aria-label="No" %} |

### Workflow file size

Each workflow file in the `.github/workflows` directory must be 500 KB or smaller to trigger a run. To reduce the size of a workflow file, move shared logic into a reusable workflow or a composite action. See [AUTOTITLE](/actions/how-tos/reuse-automations/reuse-workflows) or [AUTOTITLE](/actions/tutorials/create-actions/create-a-composite-action).

### Job concurrency limits for {% data variables.product.github %}-hosted runners

{% data variables.product.github %} Support **can** increase job concurrency limits for {% data variables.product.prodname_actions %}. To request an increase, submit a support ticket.

| Runner type | {% data variables.product.github %} plan | Total concurrent jobs | Maximum concurrent macOS jobs | Maximum concurrent GPU jobs |
|---|---|---|---|---|
| Standard {% data variables.product.github %}-hosted runner | Free | 20 | 5 | Not applicable |
| Standard {% data variables.product.github %}-hosted runner | Pro | 40 | 5 | Not applicable |
| Standard {% data variables.product.github %}-hosted runner | Team | 60 | 5 | Not applicable |
| Standard {% data variables.product.github %}-hosted runner | Enterprise | 500 | 50 | Not applicable |
| Larger runner | Team | 1000 | 5 | 100 |
| Larger runner | Enterprise | 1000 | 50 | 100 |

> [!NOTE]
> The maximum concurrent macOS jobs is shared across standard {% data variables.product.github %}-hosted runners and {% data variables.product.github %}-hosted larger runners.

### Storage limits for all {% data variables.product.github %}-hosted runners

{% data variables.product.github %} Support **cannot** increase storage limits for {% data variables.product.prodname_actions %}.

{% data reusables.billing.actions-included-quotas %}

{% ifversion fpt or ghec %}

For information about cache storage limits and how to increase them, see [Usage limits and eviction policy](/actions/reference/workflows-and-actions/dependency-caching#usage-limits-and-eviction-policy).

{% endif %}

### Private IP scaling for vnet injection on larger runners

When using larger runners with vnet injection, you need to determine the appropriate subnet IP address range, for which we recommend adding a buffer to the maximum job concurrency you anticipate. For instance, if the network configuration's runners are set to a maximum job concurrency of 300, utilize a subnet IP address range that can accommodate at least 390 runners. Note that Azure reserves 5 IPs in every subnet (first 4 and last 1), which sets a minimum practical subnet size depending on runner requirements. Very small subnets (like /29 or smaller) may not provide enough usable addresses for your needs.

## Commonly hit dependent service limits

{% data variables.product.github %}'s [REST API rate limits](/rest/using-the-rest-api/rate-limits-for-the-rest-api) apply to {% data variables.product.prodname_actions %} users, those that are commonly hit are:

* **Unauthenticated users** \- {% data reusables.rest-api.primary-rate-limit-unauthenticated-users %}
* **Authenticated users** \- {% data reusables.rest-api.primary-rate-limit-authenticated-users %}
* **GitHub app installations** \- {% data reusables.rest-api.primary-rate-limit-github-app-installations %}
* **OAuth apps \-** {% data reusables.rest-api.primary-rate-limit-oauth-apps %}
* **GITHUB TOKEN** \- {% data reusables.rest-api.primary-rate-limit-github-token-in-actions %}
* **Secondary rate limits** \- In addition to primary rate limits, {% data variables.product.github %} enforces secondary rate limits in order to prevent abuse and keep the API available for all users, these are not configurable with GHEC. For more information, see [AUTOTITLE](/rest/using-the-rest-api/rate-limits-for-the-rest-api?apiVersion=2022-11-28#about-secondary-rate-limits).

### Docker Hub's rate limit for {% data variables.product.prodname_actions %}

* **{% data variables.product.github %}-hosted runners pulling public images:** Docker Hub's rate limit is not applied.
* **{% data variables.product.github %}-hosted runners pulling private images:** Pulling private images from Docker Hub is subject to the rate limit.
* **Self-hosted runners pulling public or private images:** Pulling images from Docker Hub is always subject to the rate limit.

---

## Included files

### `data/reusables/billing/actions-included-quotas.md`

````markdown
| Plan | Artifact storage | Minutes (per month) | Cache storage (per repository) | Custom image storage |
| ------- | ------- | --------- | ------- | ------- |
| {% data variables.product.prodname_free_user %} | 500 MB | 2,000 | 10 GB | Not applicable |
| {% data variables.product.prodname_pro %} | 1 GB | 3,000 | 10 GB | Not applicable |
| {% data variables.product.prodname_free_team %} for organizations | 500 MB | 2,000 | 10 GB | Not applicable |
| {% data variables.product.prodname_team %} | 2 GB | 3,000 | 10 GB | 75 GB |
| {% data variables.product.prodname_ghe_cloud %} | 50 GB | 50,000 | 10 GB | 150 GB |
````

### `data/reusables/rest-api/primary-rate-limit-unauthenticated-users.md`

````markdown
You can make unauthenticated requests if you are only fetching public data. Unauthenticated requests are associated with the originating IP address, not with the user or application that made the request.

  The primary rate limit for unauthenticated requests is 60 requests per hour.
  
````

### `data/reusables/rest-api/primary-rate-limit-authenticated-users.md`

````markdown
You can use a {% data variables.product.pat_generic %} to make API requests. Additionally, you can authorize a {% data variables.product.prodname_github_app %} or {% data variables.product.prodname_oauth_app %}, which can then make API requests on your behalf.

  All of these requests count towards your personal rate limit of 5,000 requests per hour. {% ifversion fpt or ghec %}Requests made on your behalf by a {% data variables.product.prodname_github_app %} that is owned by a {% data variables.product.prodname_ghe_cloud %} organization have a higher rate limit of 15,000 requests per hour. Similarly, requests made on your behalf by a {% data variables.product.prodname_oauth_app %} that is owned or approved by a {% data variables.product.prodname_ghe_cloud %} organization have a higher rate limit of 15,000 requests per hour if you are a member of the {% data variables.product.prodname_ghe_cloud %} organization. However, requests made by a higher-limit app reduce the remaining budget available for lower-limit authentication methods. For example, if an app with a 15,000 request limit makes 10,000 requests on your behalf, you will have exhausted the 5,000 request budget for your {% data variables.product.pat_generic_plural %}, even though the app has 5,000 requests remaining.{% endif %}
````

### `data/reusables/rest-api/primary-rate-limit-github-app-installations.md`

````markdown
{% data variables.product.prodname_github_apps %} authenticating with an installation access token use the installation's minimum rate limit of 5,000 requests per hour. If the installation is on a {% data variables.product.prodname_ghe_cloud %} organization{% ifversion enterprise-installed-apps %} or enterprise{% endif %}, the installation has a rate limit of 15,000 requests per hour.

  For installations that are not on a {% data variables.product.prodname_ghe_cloud %} organization{% ifversion enterprise-installed-apps %} or enterprise{% endif %}, the rate limit for the installation will scale with the number of users and repositories. Installations that have more than 20 repositories receive another 50 requests per hour for each repository. Installations that are on an organization that have more than 20 users receive another 50 requests per hour for each user. The rate limit cannot increase beyond 12,500 requests per hour.

  Primary rate limits for {% data variables.product.prodname_github_app %} user access tokens (as opposed to installation access tokens) are dictated by the primary rate limits for the authenticated user. This rate limit is combined with any requests that another {% data variables.product.prodname_github_app %} or {% data variables.product.prodname_oauth_app %} makes on that user's behalf and any requests that the user makes with a {% data variables.product.pat_generic %}. For more information, see [AUTOTITLE](/rest/using-the-rest-api/rate-limits-for-the-rest-api#primary-rate-limit-for-authenticated-users).
````

### `data/reusables/rest-api/primary-rate-limit-oauth-apps.md`

````markdown
For these requests, the rate limit is 5,000 requests per hour per {% data variables.product.prodname_oauth_app %}. If the app is owned by a {% data variables.product.prodname_ghe_cloud %} organization, the rate limit is 15,000 requests per hour.
````

### `data/reusables/rest-api/primary-rate-limit-github-token-in-actions.md`

````markdown
The rate limit for `GITHUB_TOKEN` is 1,000 requests per hour per repository.{% ifversion fpt or ghec %} For requests to resources that belong to a {% data variables.product.prodname_ghe_cloud %} account, the limit is 15,000 requests per hour per repository.{% endif %}
````

### `data/features/actions-nga.yml`

````yaml
# New feature: actions-nga
# Versioning for Actions NGA (Next Generation Architecture) features
versions:
  fpt: '*'
  ghec: '*'
````

### `data/features/enterprise-installed-apps.yml`

````yaml
# Reference: #docs-content/issues/16388
# GitHub Apps can now be installed at the enterprise level in addition to organizations
versions:
  ghec: '*'
  ghes: '>=3.19'
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_actions %}` | GitHub Actions |
| `{% data variables.contact.contact_support %}` | {% ifversion fpt or ghec %}us through the [GitHub Support portal](https://support.github.com){% elsif ghes %}your site administrator{% endif %} |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.product.prodname_free_user %}` | GitHub Free |
| `{% data variables.product.prodname_pro %}` | GitHub Pro |
| `{% data variables.product.prodname_free_team %}` | GitHub Free |
| `{% data variables.product.prodname_team %}` | GitHub Team |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.product.pat_generic %}` | personal access token |
| `{% data variables.product.prodname_github_app %}` | GitHub App |
| `{% data variables.product.prodname_oauth_app %}` | OAuth app |
| `{% data variables.product.pat_generic_plural %}` | personal access tokens |
| `{% data variables.product.prodname_github_apps %}` | GitHub Apps |
