# Source Snapshot: gh pr review (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_pr_review
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh pr review

    gh pr review [<number> | <url> | <branch>] [flags]

Add a review to a pull request.

Without an argument, the pull request that belongs to the current branch is reviewed.

### Options

`-a`, `--approve`  
Approve pull request

`-b`, `--body <string>`  
Specify the body of a review

`-F`, `--body-file <file>`  
Read body text from file (use "-" to read from standard input)

`-c`, `--comment`  
Comment on a pull request

`-r`, `--request-changes`  
Request changes on a pull request

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### Examples

    # Approve the pull request of the current branch
    $ gh pr review --approve

    # Leave a review comment for the current branch
    $ gh pr review --comment -b "interesting"

    # Add a review for a specific pull request
    $ gh pr review 123

    # Request changes on a specific pull request
    $ gh pr review 123 -r -b "needs more ASCII art"

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
