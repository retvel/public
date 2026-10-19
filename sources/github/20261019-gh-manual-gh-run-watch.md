# Source Snapshot: gh run watch (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_run_watch
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh run watch

    gh run watch <run-id> [flags]

Watch a run until it completes, showing its progress.

By default, all steps are displayed. The `--compact` option can be used to only show the relevant/failed steps.

This command does not support authenticating via fine grained PATs as it is not currently possible to create a PAT with the `checks:read` permission.

### Options

`--compact`  
Show only relevant/failed steps

`--exit-status`  
Exit with non-zero status if run fails

`-i`, `--interval <int> (default 3)`  
Refresh interval in seconds

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### Examples

    # Watch a run until it's done
    $ gh run watch

    # Watch a run in compact mode
    $ gh run watch --compact

    # Run some other command when the run is finished
    $ gh run watch && notify-send 'run is done!'

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
