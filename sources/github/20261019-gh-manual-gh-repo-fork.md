# Source Snapshot: gh repo fork (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_repo_fork
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh repo fork

    gh repo fork [<repository>] [-- <gitflags>...] [flags]

Create a fork of a repository.

With no argument, creates a fork of the current repository. Otherwise, forks the specified repository.

By default, the new fork is set to be your `origin` remote and any existing origin remote is renamed to `upstream`. To alter this behavior, you can set a name for the new fork's remote with `--remote-name`.

The `upstream` remote will be set as the default remote repository.

Additional `git clone` flags can be passed after `--`.

### Options

`--clone`  
Clone the fork

`--default-branch-only`  
Only include the default branch in the fork

`--fork-name <string>`  
Rename the forked repository

`--org <string>`  
Create the fork in an organization

`--remote`  
Add a git remote for the fork

`--remote-name <string> (default "origin")`  
Specify the name for the new remote

### Examples

    # Fork a repository
    $ gh repo fork owner/repo

    # Fork a repository and clone it locally
    $ gh repo fork owner/repo --clone

    # Fork a repository without cloning it, skip the prompt
    $ gh repo fork owner/repo --clone=false

### See also

- [gh repo](./gh_repo)

### In use

#### With no arguments

Inside a git repository, and without any arguments, we will automatically create a fork on GitHub on your account for your current directory. It will then prompt if you want to set an upstream remote.

    # Create a fork for the current repository.
    ~/Projects/cli$ gh repo fork
    - Forking cli/cli...
    ✓ Created fork user/cli
    ? Would you like to add a remote for the fork? Yes
    ✓ Renamed origin remote to upstream
    ✓ Added remote origin
    ~/Projects/cli$

#### With arguments

If you pass a repository in OWNER/REPO format, \`gh\` will automatically create a fork on GitHub on your account and ask if you want to clone it. This works inside or outside of a git repository.

    # Create a fork for another repository.
    ~/Projects$ gh repo fork cli/cli
    - Forking cli/cli...
    ✓ Created fork cli/cli
    ? Would you like to clone the fork? Yes
    Cloning into 'cli'...
    ✓ Cloned fork
    ~/Projects$ cd cli
    ~/Projects/cli$

#### Using flags

Use flags to skip prompts about adding a git remote for the fork, or about cloning the forked repository locally.

    # Skipping remote prompts using flags
    ~/Projects/cli$ gh repo fork --remote=false
    - Forking cli/cli...
    ✓ Created fork user/cli
    ~/Projects/cli$

    # Skipping clone prompts using flags
    ~/Projects$ gh repo fork cli/cli --clone=false
    - Forking cli/cli...
    ✓ Created fork user/cli
    ~/Projects$

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
