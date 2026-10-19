# Source Snapshot: Ingest: Bring your data to Elastic

- **Accessed:** 2026-10-19
- **Type:** official documentation (Elastic Docs)
- **URL:** https://www.elastic.co/docs/manage-data/ingest
- **Author / publisher:** Elastic N.V. (Elastic documentation team)
- **Published / updated:** no date shown on the page; upstream file at commit dated 2026-10-16
- **Upstream file:** [`elastic/docs-content` → `manage-data/ingest.md`](https://github.com/elastic/docs-content/blob/55f05da44f1e68caf6b83d60715f6a41bcdaa2d3/manage-data/ingest.md) at commit `55f05da` (2026-10-16)
- **License:** Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0) — Copyright Elasticsearch B.V. See [LICENSE-elastic-docs-content](LICENSE-elastic-docs-content). Shared non-commercially as an unmodified copy. Reproduced verbatim below this line.
- **Note:** Placeholders such as `{{es}}`, `{{kib}}`, `{{agent}}`, `{{ls}}`, `{{fleet}}`, `{{stack}}` are substitutions defined in the repo's `docset.yml` (es = Elasticsearch, kib = Kibana, agent = Elastic Agent, ls = Logstash, fleet = Fleet, stack = Elastic Stack, beats = Beats, watcher = Watcher, serverless-full = Elastic Cloud Serverless, ech = Elastic Cloud Hosted, edot = Elastic OpenTelemetry). `{{version.stack}}` is filled in by the docs build from a central version file.

---

---
mapped_pages:
  - https://www.elastic.co/guide/en/cloud/current/ec-cloud-ingest-data.html
  - https://www.elastic.co/guide/en/kibana/current/connect-to-elasticsearch.html
  - https://www.elastic.co/guide/en/serverless/current/elasticsearch-ingest-your-data.html
  - https://www.elastic.co/guide/en/elasticsearch/reference/current/es-ingestion-overview.html
  - https://www.elastic.co/guide/en/ingest-overview/current/ingest-intro.html
applies_to:
  stack: ga
  serverless: ga
products:
  - id: cloud-hosted
  - id: kibana
  - id: cloud-serverless
  - id: elasticsearch
---

# Ingest: Bring your data to Elastic

Whether you call it *adding*, *indexing*, or *ingesting* data, you have to get the data into {{es}} before you can search it, visualize it, and use it for insights.

Our ingest tools are flexible, and support a wide range of scenarios. We can help you with everything from popular and straightforward use cases, all the way to advanced use cases that require additional processing to modify or reshape your data before it goes to {{es}}.

You can ingest:

* **General content** (data without timestamps), such as HTML pages, catalogs, and files
* **Time series (timestamped) data**, such as logs, metrics, and traces for Elastic Security, Observability, Search solutions, or for your own custom solutions


## Ingesting general content [ingest-general]

Elastic offer tools designed to ingest specific types of general content. The content type determines the best ingest option.

* To index **documents** directly into {{es}}, use the {{es}} [document APIs]({{es-apis}}group/endpoint-document).
* To send **application data** directly to {{es}}, use an [{{es}} language client](/reference/elasticsearch-clients/index.md).
* To index **web page content**, use the Elastic [web crawler](https://www.elastic.co/web-crawler).
* To sync **data from third-party sources**, use [connectors](elasticsearch://reference/search-connectors/index.md). A connector syncs content from an original data source to an {{es}} index. Using connectors you can create *searchable*, read-only replicas of your data sources.
* To index **single files** for testing in a non-production environment, use the {{kib}} [file uploader](ingest/upload-data-files.md).

If you would like to try things out before you add your own data, try using our [sample data](ingest/sample-data.md).


## Ingesting time series data [ingest-time-series]

::::{admonition} What's the best approach for ingesting time series data?
The best approach for ingesting data is the *simplest option* that *meets your needs* and *satisfies your use case*.

Usually, the *simplest option* for ingesting time series data is using {{agent}} paired with an Elastic integration.

* Install [Elastic Agent](/reference/fleet/index.md) on the computer(s) from which you want to collect data.
* Add the [Elastic integration](https://docs.elastic.co/en/integrations) for the data source to your deployment.

Integrations are available for many popular platforms and services, and are a good place to start for ingesting data into Elastic solutions—Observability, Security, and Search—or your own search application.

Check out the [Integration quick reference](https://docs.elastic.co/en/integrations/all_integrations) to search for available integrations. If you don’t find an integration for your data source, you can use [Automatic Import](/explore-analyze/ai-features/automatic-import.md) to generate a custom integration from a sample of your data using an LLM. If you need additional processing to extend an existing integration, refer to [Transform and enrich data](ingest/transform-enrich.md) to learn more.

::::
