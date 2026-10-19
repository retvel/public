# Source Snapshot: Elasticsearch local development quickstart

- **Accessed:** 2026-10-19
- **Type:** official documentation (Elastic Docs)
- **URL:** https://www.elastic.co/docs/deploy-manage/deploy/self-managed/local-development-installation-quickstart
- **Author / publisher:** Elastic N.V. (Elastic documentation team)
- **Published / updated:** no date shown on the page; upstream file at commit dated 2026-10-16
- **Upstream file:** [`elastic/docs-content` → `deploy-manage/deploy/self-managed/local-development-installation-quickstart.md`](https://github.com/elastic/docs-content/blob/55f05da44f1e68caf6b83d60715f6a41bcdaa2d3/deploy-manage/deploy/self-managed/local-development-installation-quickstart.md) at commit `55f05da` (2026-10-16)
- **Note:** Placeholders such as `{{es}}`, `{{kib}}`, `{{agent}}`, `{{ls}}`, `{{fleet}}`, `{{stack}}` are substitutions defined in the repo's `docset.yml` (es = Elasticsearch, kib = Kibana, agent = Elastic Agent, ls = Logstash, fleet = Fleet, stack = Elastic Stack, beats = Beats, watcher = Watcher, serverless-full = Elastic Cloud Serverless, ech = Elastic Cloud Hosted, edot = Elastic OpenTelemetry). `{{version.stack}}` is filled in by the docs build from a central version file.

---

---
navigation_title: Local installation (quickstart)
mapped_pages:
  - https://www.elastic.co/guide/en/elasticsearch/reference/current/run-elasticsearch-locally.html
applies_to:
  deployment:
    self:
products:
  - id: elasticsearch
---

# {{es}} local development quickstart [run-elasticsearch-locally]

::::{warning}
**DO NOT USE THESE INSTRUCTIONS FOR PRODUCTION DEPLOYMENTS**

The instructions on this page are for **local development only**. Do not use this configuration for production deployments, because it is not secure. Refer to [deployment options](/get-started/deployment-options.md) for a list of production deployment options.
::::

Quickly set up {{es}} and {{kib}} in Docker for local development or testing, using this one-liner in the command line. This setup comes with a one-month trial license that includes all {{es}} features.

As an alternative, you can also explore {{es}} and {{kib}} by [signing up for a free {{ecloud}} trial](https://cloud.elastic.co/registration).

## Prerequisites [local-dev-prerequisites]

* [Install Docker Compose](https://docs.docker.com/compose/install/). 
   
   In most cases, you need to install Docker Desktop or Docker Engine to access Docker Compose.
   
   Docker Compose V2 or later is recommended, and is included in Docker Desktop 3.4 and later, and Docker Engine 20.10.13 or later.
 
   The minimum supported version of Docker Compose is 1.29.0.
* If you’re using Microsoft Windows, then install [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install).

## Step 1: Run `start-local` script [local-dev-quick-start]

To set up {{es}} and {{kib}} locally, run the `start-local` script in the command line:

```sh
curl -fsSL https://elastic.co/start-local | sh
```

After running the script, you can access Elastic services at the following endpoints:

* **{{es}}**: [http://localhost:9200](http://localhost:9200)
* **{{kib}}**: [http://localhost:5601](http://localhost:5601)

That's it! There's no step 2.

## Learn more [local-dev-additional-info]

For more detailed information about the `start-local` setup, refer to the [README on GitHub](https://github.com/elastic/start-local). Learn about customizing the setup, logging, and more.

## Next steps [local-dev-next-steps]

Use our [quick start guides](/solutions/search/get-started/quickstarts.md) to learn the basics of {{es}}.
