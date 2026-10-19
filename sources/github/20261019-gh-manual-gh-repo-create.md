# Source Snapshot: gh repo create (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_repo_create
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh repo create

    gh repo create [<name>] [flags]

Create a new GitHub repository.

To create a repository interactively, use `gh repo create` with no arguments.

To create a remote repository non-interactively, supply the repository name and one of `--public`, `--private`, or `--internal`. Pass `--clone` to clone the new repository locally.

If the `OWNER/` portion of the `OWNER/REPO` name argument is omitted, it defaults to the name of the authenticating user.

To create a remote repository from an existing local repository, specify the source directory with `--source`. By default, the remote repository name will be the name of the source directory.

Pass `--push` to push any local commits to the new repository. If the repo is bare, this will mirror all refs.

For language or platform .gitignore templates to use with `--gitignore`, <https://github.com/github/gitignore>.

For license keywords to use with `--license`, run `gh repo license list` or visit <https://choosealicense.com>.

The repo is created with the configured repository default branch, see <https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-user-account-settings/managing-the-default-branch-name-for-your-repositories>.

### Options

`--add-readme`  
Add a README file to the new repository

`-c`, `--clone`  
Clone the new repository to the current directory

`-d`, `--description <string>`  
Description of the repository

`--disable-issues`  
Disable issues in the new repository

`--disable-wiki`  
Disable wiki in the new repository

`-g`, `--gitignore <string>`  
Specify a gitignore template for the repository

`-h`, `--homepage <URL>`  
Repository home page URL

`--include-all-branches`  
Include all branches from template repository

`--internal`  
Make the new repository internal

`-l`, `--license <string>`  
Specify an Open Source License for the repository

`--private`  
Make the new repository private

`--public`  
Make the new repository public

`--push`  
Push local commits to the new repository

`-r`, `--remote <string>`  
Specify remote name for the new repository

`-s`, `--source <string>`  
Specify path to local repository to use as source

`-t`, `--team <name>`  
The name of the organization team to be granted access

`-p`, `--template <repository>`  
Make the new repository based on a template repository

### ALIASES

gh repo new

### Examples

    # Create a repository interactively
    $ gh repo create

    # Create a new remote repository and clone it locally
    $ gh repo create my-project --public --clone

    # Create a new remote repository in a different organization
    $ gh repo create my-org/my-project --public

    # Create a remote repository from the current directory
    $ gh repo create my-project --private --source=. --remote=upstream

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
