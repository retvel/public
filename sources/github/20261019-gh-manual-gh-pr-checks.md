# Source Snapshot: gh pr checks (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_pr_checks
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh pr checks

    gh pr checks [<number> | <url> | <branch>] [flags]

Show CI status for a single pull request.

Without an argument, the pull request that belongs to the current branch is selected.

When the `--json` flag is used, it includes a `bucket` field, which categorizes the `state` field into `pass`, `fail`, `pending`, `skipping`, or `cancel`.

Additional exit codes: 8: Checks pending

### Options

`--fail-fast`  
Exit watch mode on first check failure

`-i`, `--interval <int> (default 10)`  
Refresh interval in seconds in watch mode

`-q`, `--jq <expression>`  
Filter JSON output using a jq expression

`--json <fields>`  
Output JSON with the specified fields

`--required`  
Only show checks that are required

`-t`, `--template <string>`  
Format JSON output using a Go template; see "gh help formatting"

`--watch`  
Watch checks until they finish

`-w`, `--web`  
Open the web browser to show details about checks

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### JSON Fields

`bucket`, `completedAt`, `description`, `event`, `link`, `name`, `startedAt`, `state`, `workflow`

### See also

- [gh pr](./gh_pr)

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
