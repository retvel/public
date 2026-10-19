# Source Snapshot: gh repo sync (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_repo_sync
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh repo sync

    gh repo sync [<destination-repository>] [flags]

Sync destination repository from source repository. Syncing uses the default branch of the source repository to update the matching branch on the destination repository so they are equal. A fast forward update will be used except when the `--force` flag is specified, then the two branches will be synced using a hard reset.

Without an argument, the local repository is selected as the destination repository.

The source repository is the parent of the destination repository by default. This can be overridden with the `--source` flag.

### Options

`-b`, `--branch <string>`  
Branch to sync (default \[default branch\])

`--force`  
Hard reset the branch of the destination repository to match the source repository

`-s`, `--source <string>`  
Source repository

### Examples

    # Sync local repository from remote parent
    $ gh repo sync

    # Sync local repository from remote parent on specific branch
    $ gh repo sync --branch v1

    # Sync remote fork from its parent
    $ gh repo sync owner/cli-fork

    # Sync remote repository from another remote repository
    $ gh repo sync owner/repo --source owner2/repo2

### See also

- [gh repo](./gh_repo)

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
