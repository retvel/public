# GitHub sources

Snapshots of the sources used by the `github` reference. All sources were accessed on
2026-10-19 and are publicly accessible without a login or payment.

| Origin | Repository / site and version | Published at | Copyright and license |
|--------|-------------------------------|--------------|-----------------------|
| GitHub Docs | [`github/docs`](https://github.com/github/docs) @ [`dae83f7`](https://github.com/github/docs/commit/dae83f7d28f3b8e10015bd6b6d8b72267cedceca) (2026-10-16), `content/` and `data/` | https://docs.github.com/ | © GitHub, Inc. Documentation in `content/` and `data/` is licensed under Creative Commons Attribution 4.0 (CC BY 4.0) per the repository README — [LICENSE-github-docs](LICENSE-github-docs) |
| Pro Git, 2nd edition (Scott Chacon, Ben Straub) | [`progit/progit2`](https://github.com/progit/progit2) @ [`a013e32`](https://github.com/progit/progit2/commit/a013e3230a1207cfa5ae94d28ba7d2021063c337) (2026-05-25), `book/` | https://git-scm.com/book/en/v2 | CC BY-NC-SA 3.0 Unported — [LICENSE-progit2](LICENSE-progit2) |
| Git reference manual | git-scm.com pages `git-revert`, `git-reset` (Git 2.54.0), `git-push` (Git 2.55.0), fetched 2026-10-19 | https://git-scm.com/docs | Part of the Git project's documentation; no license is stated on the page. Copied for non-commercial reference with attribution |
| GitHub CLI manual and home page | cli.github.com, fetched 2026-10-19 (download links point to gh v2.102.0) | https://cli.github.com/manual/ | "© 2026 GitHub, Inc." (page footer); no license is stated on the page. Copied for non-commercial reference with attribution |

- **GitHub Docs snapshots** reproduce the page file verbatim below the header. GitHub Docs pages
  use Liquid: `{% data reusables.* %}` tags insert shared text, `{% data variables.* %}` tags
  insert short values, and `{% ifversion %}` blocks choose text per product version. Each
  snapshot therefore appends, under "Included files", every reusable file it pulls in
  (recursively) and every feature-flag file its `ifversion` blocks use, and lists the variable
  values under "Variable values", all from the same commit. The glossary snapshot also includes
  `data/glossaries/external.yml`, which the page lists in full. Readers see the "Free, Pro &
  Team" (`fpt`) version of each page unless the header says otherwise.
- **Pro Git snapshots** reproduce the AsciiDoc section file verbatim.
- **Web captures** (git-scm.com reference, GitHub CLI) were converted from HTML to Markdown; see
  each header's **Capture** line.
- **Images** shown by the pages are copied into [`assets/`](assets/); only image paths were
  changed to point to these copies.
- **Snapshots are immutable.** When a source changes, a new dated snapshot is added.

| Snapshot | Title | Original URL |
|----------|-------|--------------|
| [20261019-about-2fa.md](20261019-about-2fa.md) | About two-factor authentication | https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/about-two-factor-authentication |
| [20261019-about-authentication.md](20261019-about-authentication.md) | About authentication to GitHub | https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github |
| [20261019-about-forks.md](20261019-about-forks.md) | About forks | https://docs.github.com/en/pull-requests/get-started/about-forks |
| [20261019-about-git-rebase.md](20261019-about-git-rebase.md) | About Git rebase | https://docs.github.com/en/get-started/using-git/about-git-rebase |
| [20261019-about-git.md](20261019-about-git.md) | About Git | https://docs.github.com/en/get-started/using-git/about-git |
| [20261019-about-github-advanced-security.md](20261019-about-github-advanced-security.md) | About GitHub Advanced Security | https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security |
| [20261019-about-github-cli.md](20261019-about-github-cli.md) | About GitHub CLI | https://docs.github.com/en/github-cli/github-cli/about-github-cli |
| [20261019-about-issues.md](20261019-about-issues.md) | About issues | https://docs.github.com/en/issues/tracking-your-work-with-issues/learning-about-issues/about-issues |
| [20261019-about-milestones.md](20261019-about-milestones.md) | About milestones | https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/about-milestones |
| [20261019-about-projects.md](20261019-about-projects.md) | About Projects | https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects |
| [20261019-about-pull-requests.md](20261019-about-pull-requests.md) | About pull requests | https://docs.github.com/en/pull-requests/get-started/about-pull-requests |
| [20261019-about-readmes.md](20261019-about-readmes.md) | About the repository README file | https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes |
| [20261019-about-remote-repositories.md](20261019-about-remote-repositories.md) | About remote repositories | https://docs.github.com/en/get-started/git-basics/about-remote-repositories |
| [20261019-about-repositories.md](20261019-about-repositories.md) | About repositories | https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories |
| [20261019-about-rulesets.md](20261019-about-rulesets.md) | About rulesets | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets |
| [20261019-about-templates.md](20261019-about-templates.md) | About issue and pull request templates | https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates |
| [20261019-actions-billing-and-usage.md](20261019-actions-billing-and-usage.md) | Billing and usage | https://docs.github.com/en/actions/concepts/billing-and-usage |
| [20261019-actions-limits.md](20261019-actions-limits.md) | Actions limits | https://docs.github.com/en/actions/reference/limits |
| [20261019-actions-quickstart.md](20261019-actions-quickstart.md) | Quickstart for GitHub Actions | https://docs.github.com/en/actions/get-started/quickstart |
| [20261019-actions-settings-repo.md](20261019-actions-settings-repo.md) | Managing GitHub Actions settings for a repository | https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository |
| [20261019-adding-ssh-key.md](20261019-adding-ssh-key.md) | Adding a new SSH key to your GitHub account | https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account |
| [20261019-authenticate-with-github-token.md](20261019-authenticate-with-github-token.md) | Use GITHUB_TOKEN for authentication in workflows | https://docs.github.com/en/actions/tutorials/authenticate-with-github_token |
| [20261019-auto-merge.md](20261019-auto-merge.md) | Automatically merging a pull request | https://docs.github.com/en/pull-requests/how-tos/merge-and-close-pull-requests/automatically-merging-a-pull-request |
| [20261019-available-rules.md](20261019-available-rules.md) | Available rules for rulesets | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets |
| [20261019-billing-advanced-security.md](20261019-billing-advanced-security.md) | GitHub Advanced Security license billing | https://docs.github.com/en/billing/concepts/product-billing/github-advanced-security |
| [20261019-billing-git-lfs.md](20261019-billing-git-lfs.md) | Git Large File Storage billing | https://docs.github.com/en/billing/concepts/product-billing/git-lfs |
| [20261019-billing-github-actions.md](20261019-billing-github-actions.md) | GitHub Actions billing | https://docs.github.com/en/billing/concepts/product-billing/github-actions |
| [20261019-billing-github-packages.md](20261019-billing-github-packages.md) | GitHub Packages billing | https://docs.github.com/en/billing/concepts/product-billing/github-packages |
| [20261019-checking-out-prs-locally.md](20261019-checking-out-prs-locally.md) | Checking out pull requests locally | https://docs.github.com/en/pull-requests/how-tos/review-pull-requests/checking-out-pull-requests-locally |
| [20261019-closing-an-issue.md](20261019-closing-an-issue.md) | Closing an issue | https://docs.github.com/en/issues/tracking-your-work-with-issues/administering-issues/closing-an-issue |
| [20261019-code-owners.md](20261019-code-owners.md) | About code owners | https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners |
| [20261019-code-scanning-setup-types.md](20261019-code-scanning-setup-types.md) | About setup types for code scanning | https://docs.github.com/en/code-security/concepts/code-scanning/setup-types |
| [20261019-code-scanning.md](20261019-code-scanning.md) | Code scanning | https://docs.github.com/en/code-security/concepts/code-scanning/code-scanning |
| [20261019-configure-version-updates.md](20261019-configure-version-updates.md) | Configuring Dependabot version updates | https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-version-updates |
| [20261019-configuring-issue-templates.md](20261019-configuring-issue-templates.md) | Configuring issue templates for your repository | https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository |
| [20261019-conflicts-after-rebase.md](20261019-conflicts-after-rebase.md) | Resolving merge conflicts after a Git rebase | https://docs.github.com/en/get-started/using-git/resolving-merge-conflicts-after-a-git-rebase |
| [20261019-creating-a-pull-request.md](20261019-creating-a-pull-request.md) | Creating a pull request | https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/creating-a-pull-request |
| [20261019-creating-a-repository.md](20261019-creating-a-repository.md) | Creating a new repository | https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository |
| [20261019-dependabot-alerts.md](20261019-dependabot-alerts.md) | Dependabot alerts | https://docs.github.com/en/code-security/concepts/supply-chain-security/dependabot-alerts |
| [20261019-dependabot-security-updates.md](20261019-dependabot-security-updates.md) | Dependabot security updates | https://docs.github.com/en/code-security/concepts/supply-chain-security/dependabot-security-updates |
| [20261019-dependabot-version-updates.md](20261019-dependabot-version-updates.md) | Dependabot version updates | https://docs.github.com/en/code-security/concepts/supply-chain-security/dependabot-version-updates |
| [20261019-events-that-trigger-workflows.md](20261019-events-that-trigger-workflows.md) | Events that trigger workflows | https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows |
| [20261019-faq-changes-to-plans.md](20261019-faq-changes-to-plans.md) | FAQ about changes to GitHub's plans | https://docs.github.com/en/get-started/learning-about-github/faq-about-changes-to-githubs-plans |
| [20261019-fork-a-repo.md](20261019-fork-a-repo.md) | Fork a repository | https://docs.github.com/en/pull-requests/how-tos/work-with-forks/fork-a-repo |
| [20261019-forks-reference.md](20261019-forks-reference.md) | Forks | https://docs.github.com/en/pull-requests/reference/forks |
| [20261019-generating-ssh-key.md](20261019-generating-ssh-key.md) | Generating a new SSH key and adding it to the ssh-agent | https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent |
| [20261019-gh-manual-gh-auth-login.md](20261019-gh-manual-gh-auth-login.md) | gh auth login (GitHub CLI manual) | https://cli.github.com/manual/gh_auth_login |
| [20261019-gh-manual-gh-browse.md](20261019-gh-manual-gh-browse.md) | gh browse (GitHub CLI manual) | https://cli.github.com/manual/gh_browse |
| [20261019-gh-manual-gh-issue-create.md](20261019-gh-manual-gh-issue-create.md) | gh issue create (GitHub CLI manual) | https://cli.github.com/manual/gh_issue_create |
| [20261019-gh-manual-gh-issue-list.md](20261019-gh-manual-gh-issue-list.md) | gh issue list (GitHub CLI manual) | https://cli.github.com/manual/gh_issue_list |
| [20261019-gh-manual-gh-pr-checkout.md](20261019-gh-manual-gh-pr-checkout.md) | gh pr checkout (GitHub CLI manual) | https://cli.github.com/manual/gh_pr_checkout |
| [20261019-gh-manual-gh-pr-checks.md](20261019-gh-manual-gh-pr-checks.md) | gh pr checks (GitHub CLI manual) | https://cli.github.com/manual/gh_pr_checks |
| [20261019-gh-manual-gh-pr-create.md](20261019-gh-manual-gh-pr-create.md) | gh pr create (GitHub CLI manual) | https://cli.github.com/manual/gh_pr_create |
| [20261019-gh-manual-gh-pr-merge.md](20261019-gh-manual-gh-pr-merge.md) | gh pr merge (GitHub CLI manual) | https://cli.github.com/manual/gh_pr_merge |
| [20261019-gh-manual-gh-pr-review.md](20261019-gh-manual-gh-pr-review.md) | gh pr review (GitHub CLI manual) | https://cli.github.com/manual/gh_pr_review |
| [20261019-gh-manual-gh-repo-clone.md](20261019-gh-manual-gh-repo-clone.md) | gh repo clone (GitHub CLI manual) | https://cli.github.com/manual/gh_repo_clone |
| [20261019-gh-manual-gh-repo-create.md](20261019-gh-manual-gh-repo-create.md) | gh repo create (GitHub CLI manual) | https://cli.github.com/manual/gh_repo_create |
| [20261019-gh-manual-gh-repo-fork.md](20261019-gh-manual-gh-repo-fork.md) | gh repo fork (GitHub CLI manual) | https://cli.github.com/manual/gh_repo_fork |
| [20261019-gh-manual-gh-repo-sync.md](20261019-gh-manual-gh-repo-sync.md) | gh repo sync (GitHub CLI manual) | https://cli.github.com/manual/gh_repo_sync |
| [20261019-gh-manual-gh-run-list.md](20261019-gh-manual-gh-run-list.md) | gh run list (GitHub CLI manual) | https://cli.github.com/manual/gh_run_list |
| [20261019-gh-manual-gh-run-watch.md](20261019-gh-manual-gh-run-watch.md) | gh run watch (GitHub CLI manual) | https://cli.github.com/manual/gh_run_watch |
| [20261019-gh-manual-gh-secret-set.md](20261019-gh-manual-gh-secret-set.md) | gh secret set (GitHub CLI manual) | https://cli.github.com/manual/gh_secret_set |
| [20261019-gh-manual-gh-workflow-run.md](20261019-gh-manual-gh-workflow-run.md) | gh workflow run (GitHub CLI manual) | https://cli.github.com/manual/gh_workflow_run |
| [20261019-git-scm-git-push.md](20261019-git-scm-git-push.md) | Git - git-push Documentation | https://git-scm.com/docs/git-push |
| [20261019-git-scm-git-reset.md](20261019-git-scm-git-reset.md) | Git - git-reset Documentation | https://git-scm.com/docs/git-reset |
| [20261019-git-scm-git-revert.md](20261019-git-scm-git-revert.md) | Git - git-revert Documentation | https://git-scm.com/docs/git-revert |
| [20261019-github-cli-home.md](20261019-github-cli-home.md) | GitHub CLI \| Take GitHub to the command line | https://cli.github.com/ |
| [20261019-github-cli-quickstart.md](20261019-github-cli-quickstart.md) | GitHub CLI quickstart | https://docs.github.com/en/github-cli/github-cli/quickstart |
| [20261019-github-flow.md](20261019-github-flow.md) | GitHub flow | https://docs.github.com/en/get-started/using-github/github-flow |
| [20261019-github-glossary.md](20261019-github-glossary.md) | GitHub glossary | https://docs.github.com/en/get-started/learning-about-github/github-glossary |
| [20261019-github-token.md](20261019-github-token.md) | GITHUB_TOKEN | https://docs.github.com/en/actions/concepts/security/github_token |
| [20261019-githubs-plans.md](20261019-githubs-plans.md) | GitHub's plans | https://docs.github.com/en/get-started/learning-about-github/githubs-plans |
| [20261019-giving-reviews.md](20261019-giving-reviews.md) | Giving reviews | https://docs.github.com/en/pull-requests/concepts/giving-reviews |
| [20261019-hello-world.md](20261019-hello-world.md) | Hello World | https://docs.github.com/en/get-started/using-github/hello-world |
| [20261019-helping-others-review.md](20261019-helping-others-review.md) | Helping others review your changes | https://docs.github.com/en/pull-requests/concepts/helping-others-review-your-changes |
| [20261019-ignoring-files.md](20261019-ignoring-files.md) | Ignoring files | https://docs.github.com/en/get-started/git-basics/ignoring-files |
| [20261019-incorporating-feedback.md](20261019-incorporating-feedback.md) | Incorporating feedback in your pull request | https://docs.github.com/en/pull-requests/how-tos/review-pull-requests/incorporating-feedback-in-your-pull-request |
| [20261019-issue-forms-syntax.md](20261019-issue-forms-syntax.md) | Syntax for issue forms | https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms |
| [20261019-issue-types.md](20261019-issue-types.md) | Managing issue types in an organization | https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/managing-issue-types-in-an-organization |
| [20261019-large-files.md](20261019-large-files.md) | About large files on GitHub | https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github |
| [20261019-learning-resources.md](20261019-learning-resources.md) | Git and GitHub learning resources | https://docs.github.com/en/get-started/start-your-journey/git-and-github-learning-resources |
| [20261019-linking-pr-to-issue.md](20261019-linking-pr-to-issue.md) | Linking a pull request to an issue | https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue |
| [20261019-managing-labels.md](20261019-managing-labels.md) | Managing labels | https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels |
| [20261019-mandatory-2fa.md](20261019-mandatory-2fa.md) | About mandatory two-factor authentication | https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/about-mandatory-two-factor-authentication |
| [20261019-merge-conflicts.md](20261019-merge-conflicts.md) | Merge conflicts | https://docs.github.com/en/pull-requests/reference/merge-conflicts |
| [20261019-merge-methods.md](20261019-merge-methods.md) | About merge methods on GitHub | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/about-merge-methods-on-github |
| [20261019-merge-queue.md](20261019-merge-queue.md) | Managing a merge queue | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue |
| [20261019-merging-a-pull-request.md](20261019-merging-a-pull-request.md) | Merging a pull request | https://docs.github.com/en/pull-requests/how-tos/merge-and-close-pull-requests/merging-a-pull-request |
| [20261019-non-fast-forward-errors.md](20261019-non-fast-forward-errors.md) | Dealing with non-fast-forward errors | https://docs.github.com/en/get-started/using-git/dealing-with-non-fast-forward-errors |
| [20261019-pages-limits.md](20261019-pages-limits.md) | GitHub Pages limits | https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits |
| [20261019-pages-publishing-source.md](20261019-pages-publishing-source.md) | Configuring a publishing source for your GitHub Pages site | https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site |
| [20261019-pages-quickstart.md](20261019-pages-quickstart.md) | Quickstart for GitHub Pages | https://docs.github.com/en/pages/quickstart |
| [20261019-pages-visibility.md](20261019-pages-visibility.md) | Changing the visibility of your GitHub Pages site | https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site |
| [20261019-personal-access-tokens.md](20261019-personal-access-tokens.md) | Managing your personal access tokens | https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens |
| [20261019-pr-stage-draft.md](20261019-pr-stage-draft.md) | Changing the stage of a pull request | https://docs.github.com/en/pull-requests/how-tos/create-pull-requests/changing-the-stage-of-a-pull-request |
| [20261019-pr-template.md](20261019-pr-template.md) | Creating a pull request template for your repository | https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository |
| [20261019-progit-basic-branching-and-merging.md](20261019-progit-basic-branching-and-merging.md) | Pro Git — Basic Branching and Merging | https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging |
| [20261019-progit-branches-in-a-nutshell.md](20261019-progit-branches-in-a-nutshell.md) | Pro Git — Branches in a Nutshell | https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell |
| [20261019-progit-first-time-setup.md](20261019-progit-first-time-setup.md) | Pro Git — First-Time Git Setup | https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup |
| [20261019-progit-getting-a-repository.md](20261019-progit-getting-a-repository.md) | Pro Git — Getting a Git Repository | https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository |
| [20261019-progit-rebasing.md](20261019-progit-rebasing.md) | Pro Git — Rebasing | https://git-scm.com/book/en/v2/Git-Branching-Rebasing |
| [20261019-progit-recording-changes.md](20261019-progit-recording-changes.md) | Pro Git — Recording Changes to the Repository | https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository |
| [20261019-progit-remote-branches.md](20261019-progit-remote-branches.md) | Pro Git — Remote Branches | https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches |
| [20261019-progit-stashing-and-cleaning.md](20261019-progit-stashing-and-cleaning.md) | Pro Git — Stashing and Cleaning | https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning |
| [20261019-progit-undoing-things.md](20261019-progit-undoing-things.md) | Pro Git — Undoing Things | https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things |
| [20261019-progit-what-is-git.md](20261019-progit-what-is-git.md) | Pro Git — What is Git? | https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F |
| [20261019-progit-working-with-remotes.md](20261019-progit-working-with-remotes.md) | Pro Git — Working with Remotes | https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes |
| [20261019-protected-branches.md](20261019-protected-branches.md) | About protected branches | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches |
| [20261019-pull-request-merges.md](20261019-pull-request-merges.md) | Pull request merges | https://docs.github.com/en/pull-requests/reference/pull-request-merges |
| [20261019-pull-request-reviews.md](20261019-pull-request-reviews.md) | Pull request reviews | https://docs.github.com/en/pull-requests/reference/pull-request-reviews |
| [20261019-pull-requests-reference.md](20261019-pull-requests-reference.md) | Pull requests | https://docs.github.com/en/pull-requests/reference/pull-requests |
| [20261019-push-protection.md](20261019-push-protection.md) | Push protection | https://docs.github.com/en/code-security/concepts/secret-security/push-protection |
| [20261019-pushing-commits.md](20261019-pushing-commits.md) | Pushing commits to a remote repository | https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository |
| [20261019-removing-sensitive-data.md](20261019-removing-sensitive-data.md) | Removing sensitive data from a repository | https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository |
| [20261019-repository-best-practices.md](20261019-repository-best-practices.md) | Best practices for repositories | https://docs.github.com/en/repositories/creating-and-managing-repositories/best-practices-for-repositories |
| [20261019-repository-limits.md](20261019-repository-limits.md) | Repository limits | https://docs.github.com/en/repositories/creating-and-managing-repositories/repository-limits |
| [20261019-repository-visibility.md](20261019-repository-visibility.md) | Setting repository visibility | https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility |
| [20261019-resolve-conflict-command-line.md](20261019-resolve-conflict-command-line.md) | Resolving a merge conflict using the command line | https://docs.github.com/en/pull-requests/how-tos/merge-and-close-pull-requests/resolving-a-merge-conflict-using-the-command-line |
| [20261019-reverting-a-pull-request.md](20261019-reverting-a-pull-request.md) | Reverting a pull request | https://docs.github.com/en/pull-requests/how-tos/merge-and-close-pull-requests/reverting-a-pull-request |
| [20261019-reviewing-proposed-changes.md](20261019-reviewing-proposed-changes.md) | Reviewing proposed changes in a pull request | https://docs.github.com/en/pull-requests/how-tos/review-pull-requests/reviewing-proposed-changes-in-a-pull-request |
| [20261019-secret-scanning.md](20261019-secret-scanning.md) | Secret scanning | https://docs.github.com/en/code-security/concepts/secret-security/secret-scanning |
| [20261019-secrets-concept.md](20261019-secrets-concept.md) | Secrets | https://docs.github.com/en/actions/concepts/security/secrets |
| [20261019-secrets-reference.md](20261019-secrets-reference.md) | Secrets reference | https://docs.github.com/en/actions/reference/security/secrets |
| [20261019-secure-use.md](20261019-secure-use.md) | Secure use reference | https://docs.github.com/en/actions/reference/security/secure-use |
| [20261019-security-features.md](20261019-security-features.md) | GitHub security features | https://docs.github.com/en/code-security/getting-started/github-security-features |
| [20261019-status-checks.md](20261019-status-checks.md) | Status checks | https://docs.github.com/en/pull-requests/reference/status-checks |
| [20261019-sub-issues.md](20261019-sub-issues.md) | Adding sub-issues | https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/adding-sub-issues |
| [20261019-syncing-a-fork.md](20261019-syncing-a-fork.md) | Syncing a fork | https://docs.github.com/en/pull-requests/how-tos/work-with-forks/syncing-a-fork |
| [20261019-testing-ssh-connection.md](20261019-testing-ssh-connection.md) | Testing your SSH connection | https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection |
| [20261019-types-of-github-accounts.md](20261019-types-of-github-accounts.md) | Types of GitHub accounts | https://docs.github.com/en/get-started/learning-about-github/types-of-github-accounts |
| [20261019-understand-github-actions.md](20261019-understand-github-actions.md) | Understanding GitHub Actions | https://docs.github.com/en/actions/get-started/understand-github-actions |
| [20261019-what-is-github-pages.md](20261019-what-is-github-pages.md) | What is GitHub Pages? | https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages |
| [20261019-workflow-syntax.md](20261019-workflow-syntax.md) | Workflow syntax for GitHub Actions | https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax |
