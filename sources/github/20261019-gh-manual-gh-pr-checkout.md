# Source Snapshot: gh pr checkout (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_pr_checkout
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh pr checkout

Check out a pull request in git

    gh pr checkout [<number> | <url> | <branch>] [flags]

### Options

`-b`, `--branch <string>`  
Local branch name to use (default \[the name of the head branch\])

`--detach`  
Checkout PR with a detached HEAD

`-f`, `--force`  
Reset the existing local branch to the latest state of the pull request

`--recurse-submodules`  
Update all submodules after checkout

`--worktree <path>`  
Check out the pull request into a worktree at the given path

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### ALIASES

gh pr co

### Examples

    # Interactively select a PR from the 10 most recent to check out
    $ gh pr checkout

    # Checkout a specific PR
    $ gh pr checkout 32
    $ gh pr checkout https://github.com/OWNER/REPO/pull/32
    $ gh pr checkout feature
    $ gh pr checkout 32 --branch feature --worktree /path/to/wt-feature

### See also

- [gh pr](./gh_pr)

### In use

#### Using pull request number

You can check out any pull request, including from forks, in a repository using its pull request number

    // Checking out a pull request locally
    ~/Projects/my-project$ gh pr checkout 12
    remote: Enumerating objects: 66, done.
    remote: Counting objects: 100% (66/66), done.
    remote: Total 83 (delta 66), reused 66 (delta 66), pack-reused 17
    Unpacking objects: 100% (83/83), done.
    From https://github.com/owner/repo
     * [new ref]             refs/pull/8896/head -> patch-2
    M       README.md
    Switched to branch 'patch-2'

    ~/Projects/my-project$

#### Using other selectors

You can also use URLs and branch names to checkout pull requests.

    // Checking out a pull request locally
    ~/Projects/my-project$ gh pr checkout branch-name
    Switched to branch 'branch-name'
    Your branch is up to date with 'origin/branch-name'.
    Already up to date.

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
