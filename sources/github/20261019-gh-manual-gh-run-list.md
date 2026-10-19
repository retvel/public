# Source Snapshot: gh run list (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_run_list
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh run list

    gh run list [flags]

List recent workflow runs.

Note that providing the `workflow_name` to the `-w` flag will not fetch disabled workflows. Also pass the `-a` flag to fetch disabled workflow runs using the `workflow_name` and the `-w` flag.

Runs created by organization and enterprise ruleset workflows will not display a workflow name due to GitHub API limitations.

To see runs associated with a pull request, users should run `gh pr checks`.

### Options

`-a`, `--all`  
Include disabled workflows

`-b`, `--branch <string>`  
Filter runs by branch

`-c`, `--commit <SHA>`  
Filter runs by the SHA of the commit

`--created <date>`  
Filter runs by the date it was created

`-e`, `--event <event>`  
Filter runs by which event triggered the run

`-q`, `--jq <expression>`  
Filter JSON output using a jq expression

`--json <fields>`  
Output JSON with the specified fields

`-L`, `--limit <int> (default 20)`  
Maximum number of runs to fetch

`-s`, `--status <string>`  
Filter runs by status: {queued\|completed\|in_progress\|requested\|waiting\|pending\|action_required\|cancelled\|failure\|neutral\|skipped\|stale\|startup_failure\|success\|timed_out}

`-t`, `--template <string>`  
Format JSON output using a Go template; see "gh help formatting"

`-u`, `--user <string>`  
Filter runs by user who triggered the run

`-w`, `--workflow <string>`  
Filter runs by workflow

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### ALIASES

gh run ls

### JSON Fields

`attempt`, `conclusion`, `createdAt`, `databaseId`, `displayTitle`, `event`, `headBranch`, `headSha`, `name`, `number`, `startedAt`, `status`, `updatedAt`, `url`, `workflowDatabaseId`, `workflowName`

### See also

- [gh run](./gh_run)

<!-- -->

- © 2026 GitHub, Inc.
- <a href="https://help.github.com/en/articles/github-terms-of-service/" class="color-fg-muted">Terms</a>
- <a href="https://help.github.com/en/articles/github-privacy-statement/" class="color-fg-muted">Privacy</a>
- <a href="https://docs.github.com/en/github-cli/github-cli/github-cli-telemetry" class="color-fg-muted">Telemetry</a>

<!-- -->

- <a href="https://twitter.com/github" class="color-fg-muted" title="GitHub on Twitter"></a>
- <a href="https://www.facebook.com/GitHub" class="color-fg-muted" title="GitHub on Facebook"></a>
- <a href="https://www.youtube.com/github" class="color-fg-muted" title="GitHub on YouTube"></a>
- <a href="https://www.linkedin.com/company/github" class="color-fg-muted" title="GitHub on Linkedin"></a>
- <a href="https://github.com/github" class="color-fg-muted" title="GitHub&#39;s organization"></a>
