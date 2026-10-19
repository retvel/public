# Source Snapshot: gh secret set (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_secret_set
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh secret set

    gh secret set <secret-name> [flags]

Set a value for a secret on one of the following levels:

- repository (default): available to GitHub Actions runs, Agents sessions, or Dependabot in a repository
- environment: available to GitHub Actions runs for a deployment environment in a repository
- organization: available to GitHub Actions runs, Agents sessions, Dependabot, or Codespaces within an organization
- user: available to Codespaces for your user

Organization and user secrets can optionally be restricted to only be available to specific repositories.

Secret values are locally encrypted before being sent to GitHub.

### Options

`-a`, `--app <string>`  
Set the application for a secret: {actions\|agents\|codespaces\|dependabot}

`-b`, `--body <string>`  
The value for the secret (reads from standard input if not specified)

`-e`, `--env <environment>`  
Set deployment environment secret

`-f`, `--env-file <file>`  
Load secret names and values from a dotenv-formatted file

`--no-repos-selected`  
No repositories can access the organization secret

`--no-store`  
Print the encrypted, base64-encoded value instead of storing it on GitHub

`-o`, `--org <organization>`  
Set organization secret

`-r`, `--repos <repositories>`  
List of repositories that can access an organization or user secret

`-u`, `--user`  
Set a secret for your user

`-v`, `--visibility <string> (default "private")`  
Set visibility for an organization secret: {all\|private\|selected}

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### Examples

    # Paste secret value for the current repository in an interactive prompt
    $ gh secret set MYSECRET

    # Read secret value from an environment variable
    $ gh secret set MYSECRET --body "$ENV_VALUE"

    # Set secret for a specific remote repository
    $ gh secret set MYSECRET --repo origin/repo --body "$ENV_VALUE"

    # Read secret value from a file
    $ gh secret set MYSECRET < myfile.txt

    # Set secret for a deployment environment in the current repository
    $ gh secret set MYSECRET --env myenvironment

    # Set organization-level secret visible to both public and private repositories
    $ gh secret set MYSECRET --org myOrg --visibility all

    # Set organization-level secret visible to specific repositories
    $ gh secret set MYSECRET --org myOrg --repos repo1,repo2,repo3

    # Set organization-level secret visible to no repositories
    $ gh secret set MYSECRET --org myOrg --no-repos-selected

    # Set user-level secret for Codespaces
    $ gh secret set MYSECRET --user

    # Set repository-level secret for Dependabot
    $ gh secret set MYSECRET --app dependabot

    # Set multiple secrets imported from the ".env" file
    $ gh secret set -f .env

    # Set multiple secrets from stdin
    $ gh secret set -f - < myfile.txt

### See also

- [gh secret](./gh_secret)

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
