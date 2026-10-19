# Source Snapshot: gh auth login (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_auth_login
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh auth login

    gh auth login [flags]

Authenticate with a GitHub host.

The default hostname is `github.com`. This can be overridden using the `--hostname` flag.

The default authentication mode is a web-based browser flow. After completion, an authentication token will be stored securely in the system credential store. If a credential store is not found or there is an issue using it gh will fallback to writing the token to a plain text file. See `gh auth status` for its stored location.

Alternatively, use `--with-token` to pass in a personal access token (classic) on standard input. The minimum required scopes for the token are: `repo`, `read:org`, and `gist`. Take care when passing a fine-grained personal access token to `--with-token` as the inherent scoping to certain resources may cause confusing behaviour when interacting with other resources. Favour setting `GH_TOKEN` for fine-grained personal access token usage.

Alternatively, gh will use the authentication token found in environment variables. This method is most suitable for "headless" use of gh such as in automation. See `gh help environment` for more info.

To use gh in GitHub Actions, add `GH_TOKEN: ${{ github.token }}` to `env`.

The git protocol to use for git operations on this host can be set with `--git-protocol`, or during the interactive prompting. Although login is for a single account on a host, setting the git protocol will take effect for all users on the host.

Specifying `ssh` for the git protocol will detect existing SSH keys to upload, prompting to create and upload a new key if one is not found. This can be skipped with `--skip-ssh-key` flag.

For more information on OAuth scopes, see <https://docs.github.com/en/developers/apps/building-oauth-apps/scopes-for-oauth-apps/>.

### Options

`-c`, `--clipboard`  
Copy one-time OAuth device code to clipboard

`-p`, `--git-protocol <string>`  
The protocol to use for git operations on this host: {ssh\|https}

`-h`, `--hostname <string>`  
The hostname of the GitHub instance to authenticate with

`--insecure-storage`  
Save authentication credentials in plain text instead of credential store

`-s`, `--scopes <strings>`  
Additional authentication scopes to request

`--skip-ssh-key`  
Skip generate/upload SSH key prompt

`-w`, `--web`  
Open a browser to authenticate

`--with-token`  
Read token from standard input

### Examples

    # Start interactive setup
    $ gh auth login

    # Open a browser to authenticate and copy one-time OAuth code to clipboard
    $ gh auth login --web --clipboard

    # Authenticate against github.com by reading the token from a file
    $ gh auth login --with-token < mytoken.txt

    # Authenticate with specific host
    $ gh auth login --hostname enterprise.internal

### See also

- [gh auth](./gh_auth)

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
