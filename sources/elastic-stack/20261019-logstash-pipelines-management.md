# Source Snapshot: Logstash pipelines

- **Accessed:** 2026-10-19
- **Type:** official documentation (Elastic Docs)
- **URL:** https://www.elastic.co/docs/manage-data/ingest/transform-enrich/logstash-pipelines
- **Author / publisher:** Elastic N.V. (Elastic documentation team)
- **Published / updated:** no date shown on the page; upstream file at commit dated 2026-10-16
- **Upstream file:** [`elastic/docs-content` → `manage-data/ingest/transform-enrich/logstash-pipelines.md`](https://github.com/elastic/docs-content/blob/55f05da44f1e68caf6b83d60715f6a41bcdaa2d3/manage-data/ingest/transform-enrich/logstash-pipelines.md) at commit `55f05da` (2026-10-16)
- **License:** Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0) — Copyright Elasticsearch B.V. See [LICENSE-elastic-docs-content](LICENSE-elastic-docs-content). Shared non-commercially as an unmodified copy. Reproduced verbatim below this line, except image paths (see Images).
- **Note:** Placeholders such as `{{es}}`, `{{kib}}`, `{{agent}}`, `{{ls}}`, `{{fleet}}`, `{{stack}}` are substitutions defined in the repo's `docset.yml` (es = Elasticsearch, kib = Kibana, agent = Elastic Agent, ls = Logstash, fleet = Fleet, stack = Elastic Stack, beats = Beats, watcher = Watcher, serverless-full = Elastic Cloud Serverless, ech = Elastic Cloud Hosted, edot = Elastic OpenTelemetry). `{{version.stack}}` is filled in by the docs build from a central version file.
- **Images:** copied from the same commit into [`assets/`](assets/). Only the image paths in the text below were changed to point to these copies; the text is otherwise verbatim. Copies: [`serverless-logstash-pipelines-management.png`](assets/serverless-logstash-pipelines-management.png) ← [`manage-data/images/serverless-logstash-pipelines-management.png`](https://github.com/elastic/docs-content/blob/55f05da44f1e68caf6b83d60715f6a41bcdaa2d3/manage-data/images/serverless-logstash-pipelines-management.png)

---

---
mapped_pages:
  - https://www.elastic.co/guide/en/serverless/current/logstash-pipelines.html
applies_to:
  stack: ga
  serverless:
    elasticsearch: ga
    observability: ga
    security: ga
products:
  - id: cloud-serverless
---

# Logstash pipelines [logstash-pipelines]

On the **{{ls-pipelines-app}}** management page, you can control multiple {{ls}} instances and pipeline configurations.

:::{image} assets/serverless-logstash-pipelines-management.png
:alt: {{ls-pipelines-app}}"
:screenshot:
:::

On the {{ls}} side, you must enable configuration management and register {{ls}} to use the centrally managed pipeline configurations.

::::{important}
After you configure {{ls}} to use centralized pipeline management, you can no longer specify local pipeline configurations. The `pipelines.yml` file and settings such as `path.config` and `config.string` are inactive when centralized pipeline management is enabled.

::::



## Manage pipelines [logstash-pipelines-manage-pipelines]

1. [Configure centralized pipeline management](logstash://reference/configuring-centralized-pipelines.md).
1. To add a new pipeline, go to the **{{ls-pipelines-app}}** management page using the navigation menu or the [global search field](/explore-analyze/find-and-organize/find-apps-and-objects.md).
1. Click **Create pipeline**.
1. Provide the following details, then click **Create and deploy**.

    Pipeline ID
    :   A name that uniquely identifies the pipeline. This is the ID that you used when you configured centralized pipeline management and specified a list of pipeline IDs in the `xpack.management.pipeline.id` setting.

    Description
    :   A description of the pipeline configuration. This information is for your use.

    Pipeline
    :   The pipeline configuration. You can treat the editor like any other editor. You don’t have to worry about whitespace or indentation.

    Pipeline workers
    :   The number of parallel workers used to run the filter and output stages of the pipeline.

    Pipeline batch size
    :   The maximum number of events an individual worker thread collects before executing filters and outputs.

    Pipeline batch delay
    :   Time in milliseconds to wait for each event before sending an undersized batch to pipeline workers.

    Queue type
    :   The internal queueing model for event buffering. Options are `memory` for in-memory queueing and `persisted` for disk-based acknowledged queueing.

    Queue max bytes
    :   The total capacity of the queue when persistent queues are enabled.

    Queue checkpoint writes
    :   The maximum number of events written before a checkpoint is forced when persistent queues are enabled.


To delete one or more pipelines, select their checkboxes then click **Delete**.

For more information about pipeline behavior, go to [Centralized Pipeline Management](logstash://reference/logstash-centralized-pipeline-management.md#_pipeline_behavior).
