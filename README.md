# public

Public source archive for a personal knowledge base.

Every reference in the knowledge base cites its sources. This repo keeps a **snapshot**
of each source exactly as it was read, so a claim can always be checked against what the
source said at that time, even if the original page changes or disappears.

## Layout

```
sources/
└── <topic>/
    ├── README.md             # list of snapshots for the topic, with original URLs
    ├── LICENSE-<origin>      # license of the copied material, when required
    ├── assets/               # images used by the snapshots (only when there are any)
    └── YYYYMMDD-<slug>.md    # one snapshot per source page
```

## Snapshot format

Each snapshot starts with a header, then the source content:

```markdown
# Source Snapshot: <exact page title>

- **Accessed:** YYYY-MM-DD
- **Type:** official documentation | standard | law | paper | article
- **URL:** <original URL>
- **Upstream file:** <repo, path, and commit — when the page is built from a Git repo>
- **License:** <license and copyright holder; how the content is reproduced>

---

<source content>
```

Rules:
- **Images included.** Images that a source page shows are copied into `assets/`, and
  their paths in the snapshot point to those copies. The header lists each copy with its
  original path. Nothing else in the text is changed.
- **Immutable.** A snapshot is never edited after it is added. If the source changes,
  a new dated snapshot is added next to the old one.
- **Publicly accessible sources.** This repo holds snapshots of sources anyone can open
  without a login or payment, for non-commercial reference. Each snapshot names its
  origin, copyright holder, and license (when there is one). Open-license texts include
  their license file.
- **Takedown.** If a copyright holder asks for a snapshot to be removed, it is removed
  from this repo.
- **No personal data or secrets.** This repo is public.

## Topics

| Topic | Snapshots | Origin |
|-------|-----------|--------|
| [cybersecurity](sources/cybersecurity/README.md) | 54 | OWASP Top 10:2025, Cheat Sheet Series, Developer Guide, WSTG (CC BY-SA 4.0); NIST SP 800-63B-4, CSF 2.0, SP 800-53r5, SP 800-61r3, FIPS 203–205, NICE (public domain); CISA KEV (CC0) — accessed 2026-10-19 |
| [docker](sources/docker/README.md) | 54 | Docker Docs (`docker/docs` @ `31d174d`, 2026-10-16), Apache-2.0 |
| [elastic-stack](sources/elastic-stack/README.md) | 20 | Elastic docs (`elastic/docs-content` @ `55f05da`, `elastic/elasticsearch` @ `6d7cefb`, `elastic/logstash` @ `5ad00e8`, `elastic/docs-builder` @ `879aace`), CC BY-NC-ND 4.0 / AGPL-3.0 / Apache-2.0 |
| [llm-security](sources/llm-security/README.md) | 15 | OWASP Top 10 for LLM Applications 2025 (`OWASP/www-project-top-10-for-large-language-model-applications` @ `99f4395`) and OWASP GenAI resource pages, CC BY-SA 4.0; Google SAIF pages (all rights reserved) |
| [mcp](sources/mcp/README.md) | 10 | MCP docs (`modelcontextprotocol/modelcontextprotocol` @ `1155ca4`, 2026-10-17), CC BY 4.0 / Apache-2.0 |
| [splunk](sources/splunk/README.md) | 1 | Splunk Help portal (fetched 2026-10-19), all rights reserved |
| [llm-wiki](sources/llm-wiki/README.md) | 1 | Karpathy's `llm-wiki` gist (`ac46de1`, 2026-04-04), no license stated |
