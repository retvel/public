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
- **Immutable.** A snapshot is never edited after it is added. If the source changes,
  a new dated snapshot is added next to the old one.
- **Respect the license.** When the license allows it (e.g. Apache-2.0, CC BY), the full
  original text is reproduced verbatim with attribution. Otherwise the snapshot keeps
  only short quotes and faithful notes.
- **No personal data or secrets.** This repo is public.

## Topics

| Topic | Snapshots | Origin |
|-------|-----------|--------|
| [docker](sources/docker/README.md) | 54 | Docker Docs (`docker/docs` @ `31d174d`, 2026-10-16), Apache-2.0 |
