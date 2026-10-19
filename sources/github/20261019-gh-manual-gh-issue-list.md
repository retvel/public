# Source Snapshot: gh issue list (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_issue_list
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh issue list

    gh issue list [flags]

List issues in a GitHub repository. By default, this only lists open issues.

The search query syntax is documented here: <https://docs.github.com/en/search-github/searching-on-github/searching-issues-and-pull-requests>

On supported GitHub hosts, advanced issue search syntax can be used in the `--search` query. For more information about advanced issue search, see: <https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/filtering-and-searching-issues-and-pull-requests#building-advanced-filters-for-issues>

### Options

`--app <string>`  
Filter by GitHub App author

`-a`, `--assignee <string>`  
Filter by assignee

`-A`, `--author <string>`  
Filter by author (use --app to filter by a GitHub App)

`-q`, `--jq <expression>`  
Filter JSON output using a jq expression

`--json <fields>`  
Output JSON with the specified fields

`-l`, `--label <strings>`  
Filter by label

`-L`, `--limit <int> (default 30)`  
Maximum number of issues to fetch

`--mention <string>`  
Filter by mention

`-m`, `--milestone <string>`  
Filter by milestone number or title

`-S`, `--search <query>`  
Search issues with query

`-s`, `--state <string> (default "open")`  
Filter by state: {open\|closed\|all}

`-t`, `--template <string>`  
Format JSON output using a Go template; see "gh help formatting"

`--type <name>`  
Filter by issue type name

`-w`, `--web`  
List issues in the web browser

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### ALIASES

gh issue ls

### JSON Fields

`assignees`, `author`, `blockedBy`, `blocking`, `body`, `closed`, `closedAt`, `closedByPullRequestsReferences`, `comments`, `createdAt`, `id`, `isPinned`, `issueType`, `labels`, `milestone`, `number`, `parent`, `projectCards`, `projectItems`, `reactionGroups`, `state`, `stateReason`, `subIssues`, `subIssuesSummary`, `title`, `updatedAt`, `url`

### Examples

    $ gh issue list --label "bug" --label "help wanted"
    $ gh issue list --author monalisa
    $ gh issue list --app dependabot
    $ gh issue list --assignee "@me"
    $ gh issue list --milestone "The big 1.0"
    $ gh issue list --search "error no:assignee sort:created-asc"
    $ gh issue list --state all
    $ gh issue list --type Bug

### See also

- [gh issue](./gh_issue)

### In use

#### Default behavior

You will see the most recent 30 open items.

    # Viewing a list of open issues
    ~/Projects/my-project$ gh issue list

    Issues for owner/repo

    #14  Update the remote url if it changed  (bug)
    #14  PR commands on a detached head       (enhancement)
    #13  Support for GitHub Enterprise        (wontfix)
    #8   Add an easier upgrade command        (bug)

    ~/Projects/my-project$

#### Filtering with flags

You can use flags to filter the list for your specific use cases.

    # Viewing a list of closed issues assigned to a user
    ~/Projects/my-project$ gh issue list --state closed --assignee user

    Issues for owner/repo

    #13  Enable discarding submodule changes  (bug)
    #8   Upgrade to latest react              (upgrade)

    ~/Projects/my-project$

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
