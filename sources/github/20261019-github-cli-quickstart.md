# Source Snapshot: GitHub CLI quickstart

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/github-cli/github-cli/quickstart
- **Upstream file:** [`github/docs` → `content/github-cli/github-cli/quickstart.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/github-cli/github-cli/quickstart.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/cli/about-cli.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/about-cli.md); [`data/reusables/rest-api/github-cli-install-and-auth.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/rest-api/github-cli-install-and-auth.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: GitHub CLI quickstart
intro: Start using {% data variables.product.prodname_cli %} to work with {% data variables.product.company_short %} in the command line.
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
allowTitleToDifferFromFilename: true
shortTitle: Quickstart
contentType: concepts
category:
  - Learn the basics
---

## About {% data variables.product.prodname_cli %}

{% data reusables.cli.about-cli %}

## Prerequisites

{% data reusables.rest-api.github-cli-install-and-auth %}

## Some useful commands

> [!NOTE]
> When you use some commands for the first time - for example, `gh codespace SUBCOMMAND` - you'll be prompted to add extra scopes to your authentication token. Follow the onscreen instructions.

### Viewing your status

Enter `gh status` to see details of your current work on {% data variables.product.prodname_dotcom %} across all the repositories you're subscribed to.

### Viewing a repository

Enter `gh repo view OWNER/REPO` to see the repository description and `README.md` for the repository. Enter `gh repo view OWNER/REPO --web` to view the repository in your default browser.

If you run the `repo` subcommand from within the directory of a local Git repository that has a remote on {% data variables.product.prodname_dotcom %} you can omit `OWNER/REPO`.

### Cloning a repository

Enter `gh repo clone OWNER/REPO`. For example, `gh repo clone octo-org/octo-repo` clones the `octo-org/octo-repo` repository to the directory from which you ran this command on your local computer.

### Creating a repository

Enter `gh repo create` and follow the on-screen instructions. You can create a new, empty repository on {% data variables.product.prodname_dotcom %} and then, optionally, clone it locally. Alternatively, you can push an existing local repository to {% data variables.product.prodname_dotcom %}, and optionally set it as the remote for your local repository. For information on setting a local directory as a Git repository, see [AUTOTITLE](/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github#initializing-a-git-repository).

### Working with issues

Enter `gh issue list --repo OWNER/REPO` to list the most recently created issues that are currently open for the specified repository. If you run the `issue` subcommand from within the directory of a local Git repository that has a remote on {% data variables.product.prodname_dotcom %} you can omit `--repo OWNER/REPO`. For example, enter `gh issue list --assignee "@me"` to list issues assigned to you in this repository, or `gh issue list --author monalisa` to list issues created by the user "monalisa."

You can also create a new issue, see [AUTOTITLE](/issues/tracking-your-work-with-issues/using-issues/creating-an-issue#creating-an-issue-with-github-cli), or search for an issue, see [AUTOTITLE](/issues/tracking-your-work-with-issues/using-issues/filtering-and-searching-issues-and-pull-requests?tool=cli#searching-for-issues-and-pull-requests).

### Working with pull requests

Enter `gh pr list --repo OWNER/REPO` to list the most recently created pull requests that are currently open for the specified repository. If you run the `pr` subcommand from within the directory of a local Git repository that has a remote on {% data variables.product.prodname_dotcom %} you can omit `--repo OWNER/REPO`. For example, enter `gh pr list --author "@me"` to list open pull requests that you created in this repository.

Enter `gh pr list --label LABEL-NAME` to list open pull requests with a specific label. Enter `gh search prs --review-requested=@me --state=open` to list pull requests that you've been asked to review.

To create a pull request, enter `gh pr create` and follow the on-screen instructions. For more information, see [AUTOTITLE](/pull-requests/how-tos/create-pull-requests/creating-a-pull-request?tool=cli#creating-the-pull-request).

### Working with codespaces

To create a new codespace, enter `gh codespace create` and follow the on-screen instructions.

To display your existing codespaces, enter `gh codespace list`. To open a codespace in the web version of {% data variables.product.prodname_vscode_shortname %} enter `gh codespace code -w` and choose a codespace.

In all of these commands you can substitute `cs` for `codespace`.

## Getting help

Enter `gh` for a reminder of the top-level {% data variables.product.prodname_cli %} commands that you can use. For example, `issue`, `pr`, `repo`, and so on.

For each command, and each subsidiary subcommand, you can append the `--help` flag to find out how it's used. For example, `gh issue --help` or `gh issue create --help`.

## Customizing {% data variables.product.prodname_cli %}

You can change configuration settings and add aliases or extensions, to make {% data variables.product.prodname_cli %} work the way that suits you best.

* Enter `gh config set SUBCOMMANDS` to configure {% data variables.product.prodname_cli %}'s settings, replacing `SUBCOMMANDS` with the setting you want to adjust.

  For example, you can specify the text editor that's used when a {% data variables.product.prodname_cli %} command requires you to edit text - such as when you add the body text for a new issue you're creating. To set your preferred text editor to {% data variables.product.prodname_vscode %} enter `gh config set editor "code -w"`. The `-w` (or `--wait`) flag in this example causes the command to wait for the file to be closed in {% data variables.product.prodname_vscode %} before proceeding with the next step in your terminal.

  For more information, see [`gh config set`](https://cli.github.com/manual/gh_config_set).

* Define aliases for commands that you commonly run. For example, if you run `gh alias set prd "pr create --draft"`, you will then be able to run `gh prd` to quickly open a draft pull request. For more information, see [`gh alias`](https://cli.github.com/manual/gh_alias).

* Create or add custom commands with {% data variables.product.prodname_cli %} extensions. For more information, see [AUTOTITLE](/github-cli/github-cli/using-github-cli-extensions) and [AUTOTITLE](/github-cli/github-cli/creating-github-cli-extensions).

## Using {% data variables.product.prodname_cli %} with multiple accounts

If you have multiple accounts on the same {% data variables.product.github %} platform, such as {% data variables.location.product_location %}, you can authenticate to each one and switch between them using the `gh auth switch` command. See [gh auth switch](https://cli.github.com/manual/gh_auth_switch) in the {% data variables.product.prodname_cli %} manual.

If you need to use the {% data variables.product.prodname_cli %} across multiple {% data variables.product.github %} platforms, such as a personal account on {% data variables.product.prodname_dotcom_the_website %} and a {% data variables.enterprise.prodname_managed_user %} on {% data variables.enterprise.data_residency_site %}, see [AUTOTITLE](/github-cli/github-cli/using-multiple-accounts).

## Further reading

* [AUTOTITLE](/github-cli/github-cli/github-cli-reference)
* [{% data variables.product.prodname_cli %} online manual](https://cli.github.com/manual/gh)

---

## Included files

### `data/reusables/cli/about-cli.md`

````markdown
{% data variables.product.prodname_cli %} is an open source tool for using {% data variables.product.prodname_dotcom %} from your computer's command line. When you're working from the command line, you can use the {% data variables.product.prodname_cli %} to save time and avoid switching context.
````

### `data/reusables/rest-api/github-cli-install-and-auth.md`

````markdown
1. Install {% data variables.product.prodname_cli %} on macOS, Windows, or Linux. For more information, see [Installation](https://github.com/cli/cli?ref_product=cli&ref_type=engagement&ref_style=text#installation) in the {% data variables.product.prodname_cli %} repository.
1. To authenticate to {% data variables.product.github %}, run the following command from your terminal.

   ```shell
   gh auth login
   ```

1. Select where you want to authenticate to:

   * If you access {% data variables.product.github %} at {% data variables.product.prodname_dotcom_the_website %}, select **{% data variables.product.prodname_dotcom_the_website %}**.
   * If you access {% data variables.product.github %} at a different domain, select **Other**, then enter your hostname (for example: `octocorp.ghe.com`).
1. Follow the rest of the on-screen prompts.

   {% data variables.product.prodname_cli %} automatically stores your Git credentials for you when you choose HTTPS as your preferred protocol for Git operations and answer "yes" to the prompt asking if you would like to authenticate to Git with your {% data variables.product.prodname_dotcom %} credentials. This can be useful as it allows you to use Git commands like `git push` and `git pull` without needing to set up a separate credential manager or use SSH.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_cli %}` | GitHub CLI |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.prodname_vscode_shortname %}` | VS Code |
| `{% data variables.product.prodname_vscode %}` | Visual Studio Code |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.product.prodname_dotcom_the_website %}` | GitHub.com |
| `{% data variables.enterprise.prodname_managed_user %}` | managed user account |
| `{% data variables.enterprise.data_residency_site %}` | GHE.com |
