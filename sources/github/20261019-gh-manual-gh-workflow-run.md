# Source Snapshot: gh workflow run (GitHub CLI manual)

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub CLI manual)
- **URL:** https://cli.github.com/manual/gh_workflow_run
- **Published / updated:** not stated on the page; the GitHub CLI home page offered release v2.102.0 for download on the same day (see 20261019-github-cli-home.md)
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images are not copied; links are kept as on the page.

---

## gh workflow run

    gh workflow run [<workflow-id> | <workflow-name>] [flags]

Create a `workflow_dispatch` event for a given workflow.

This command will trigger GitHub Actions to run a given workflow file. The given workflow file must support an `on.workflow_dispatch` trigger in order to be run in this way.

If the workflow file supports inputs, they can be specified in a few ways:

- Interactively
- Via `-f/--raw-field` or `-F/--field` flags
- As JSON, via standard input

The created workflow run URL will be returned if available.

### Options

`-F`, `--field <key=value>`  
Add a string parameter in key=value format, respecting @ syntax (see "gh help api").

`--json`  
Read workflow inputs as JSON via STDIN

`-f`, `--raw-field <key=value>`  
Add a string parameter in key=value format

`-r`, `--ref <string>`  
Branch or tag name which contains the version of the workflow file you'd like to run

### Options inherited from parent commands

`-R`, `--repo <[HOST/]OWNER/REPO>`  
Select another repository using the \[HOST/\]OWNER/REPO format

### Examples

    # Have gh prompt you for what workflow you'd like to run and interactively collect inputs
    $ gh workflow run

    # Run the workflow file 'triage.yml' at the remote's default branch
    $ gh workflow run triage.yml

    # Run the workflow file 'triage.yml' at a specified ref
    $ gh workflow run triage.yml --ref my-branch

    # Run the workflow file 'triage.yml' with command line inputs
    $ gh workflow run triage.yml -f name=scully -f greeting=hello

    # Run the workflow file 'triage.yml' with JSON via standard input
    $ echo '{"name":"scully", "greeting":"hello"}' | gh workflow run triage.yml --json

### See also

- [gh workflow](./gh_workflow)

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
