# Source Snapshot: gh browse (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_browse
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh browse

    gh browse [<number> | <path> | <commit-sha>] [flags]

Transition from the terminal to the web browser to view and interact with:

- Issues
- Pull requests
- Repository content
- Repository home page
- Repository settings

### Options

`-a`, `--actions`  
Open repository actions

`--blame`  
Open blame view for a file

`-b`, `--branch <string>`  
Select another branch by passing in the branch name

`-c`, `--commit <string>`  
Select another commit by passing in the commit SHA, default is the last commit

`-n`, `--no-browser`  
Print destination URL instead of opening the browser

`-p`, `--projects`  
Open repository projects

`-r`, `--releases`  
Open repository releases

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

`-s`, `--settings`  
Open repository settings

`-w`, `--wiki`  
Open repository wiki

### Examples

    # Open the home page of the current repository
    $ gh browse

    # Open the script directory of the current repository
    $ gh browse script/

    # Open issue or pull request 217
    $ gh browse 217

    # Open commit page
    $ gh browse 77507cd94ccafcf568f8560cfecde965fcfa63

    # Open repository settings
    $ gh browse --settings

    # Open main.go at line 312
    $ gh browse main.go:312

    # Open blame view for main.go at line 312
    $ gh browse main.go:312 --blame

    # Open main.go with the repository at head of bug-fix branch
    $ gh browse main.go --branch bug-fix

    # Open main.go with the repository at commit 775007cd
    $ gh browse main.go --commit=77507cd94ccafcf568f8560cfecde965fcfa63

### See also

- [gh](./gh)

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
