# Source Snapshot: gh repo clone (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_repo_clone
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh repo clone

    gh repo clone <repository> [<directory>] [-- <gitflags>...]

Clone a GitHub repository locally. Pass additional `git clone` flags by listing them after `--`.

If the `OWNER/` portion of the `OWNER/REPO` repository argument is omitted, it defaults to the name of the authenticating user.

When a protocol scheme is not provided in the repository argument, the `git_protocol` will be chosen from your configuration, which can be checked via `gh config get git_protocol`. If the protocol scheme is provided, the repository will be cloned using the specified protocol.

If the repository is a fork, its parent repository will be added as an additional git remote called `upstream`. The remote name can be configured using `--upstream-remote-name`. The `--upstream-remote-name` option supports an `@owner` value which will name the remote after the owner of the parent repository.

If the repository is a fork, its parent repository will be set as the default remote repository. To skip this behavior, use `--no-upstream`.

### Options

`--no-upstream`  
Do not add an upstream remote when cloning a fork

`-u`, `--upstream-remote-name <string> (default "upstream")`  
Upstream remote name when cloning a fork

### Examples

    # Clone a repository from a specific org
    $ gh repo clone cli/cli

    # Clone a repository from your own account
    $ gh repo clone myrepo

    # Clone a repo, overriding git protocol configuration
    $ gh repo clone https://github.com/cli/cli
    $ gh repo clone git@github.com:cli/cli.git

    # Clone a repository to a custom directory
    $ gh repo clone cli/cli workspace/cli

    # Clone a repository with additional git clone flags
    $ gh repo clone cli/cli -- --depth=1

    # Clone a fork without adding an upstream remote
    $ gh repo clone myfork --no-upstream

### See also

- [gh repo](./gh_repo)

### In use

#### Using OWNER/REPO syntax

You can clone any repository using OWNER/REPO syntax.

    # Cloning a repository
    ~/Projects$ gh repo clone cli/cli
    Cloning into 'cli'...
    ~/Projects$ cd cli
    ~/Projects/cli$

#### Using other selectors

You can also use GitHub URLs to clone repositories.

    # Cloning a repository
    ~/Projects/my-project$ gh repo clone https://github.com/cli/cli
    Cloning into 'cli'...
    remote: Enumerating objects: 99, done.
    remote: Counting objects: 100% (99/99), done.
    remote: Compressing objects: 100% (76/76), done.
    remote: Total 21160 (delta 49), reused 35 (delta 18), pack-reused 21061
    Receiving objects: 100% (21160/21160), 57.93 MiB | 10.82 MiB/s, done.
    Resolving deltas: 100% (16051/16051), done.

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
