# Source Snapshot: gh pr merge (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_pr_merge
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh pr merge

    gh pr merge [<number> | <url> | <branch>] [flags]

Merge a pull request on GitHub.

Without an argument, the pull request that belongs to the current branch is selected.

When targeting a branch that requires a merge queue, no merge strategy is required. If required checks have not yet passed, auto-merge will be enabled. If required checks have passed, the pull request will be added to the merge queue. To bypass a merge queue and merge directly, pass the `--admin` flag.

### Options

`--admin`  
Use administrator privileges to merge a pull request that does not meet requirements

`-A`, `--author-email <text>`  
Email text for merge commit author

`--auto`  
Automatically merge only after necessary requirements are met

`-b`, `--body <text>`  
Body text for the merge commit

`-F`, `--body-file <file>`  
Read body text from file (use "-" to read from standard input)

`-d`, `--delete-branch`  
Delete the local and remote branch after merge

`--disable-auto`  
Disable auto-merge for this pull request

`--match-head-commit <SHA>`  
Commit SHA that the pull request head must match to allow merge

`-m`, `--merge`  
Merge the commits with the base branch

`-r`, `--rebase`  
Rebase the commits onto the base branch

`-s`, `--squash`  
Squash the commits into one commit and merge it into the base branch

`-t`, `--subject <text>`  
Subject text for the merge commit

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

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
