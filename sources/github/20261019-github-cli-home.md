# Source Snapshot: GitHub CLI | Take GitHub to the command line

- **Accessed:** 2026-10-19
- **Type:** official website (GitHub CLI home page)
- **URL:** https://cli.github.com/
- **Published / updated:** not stated; the download links on the page point to release v2.102.0
- **Capture:** Fetched with curl on 2026-10-19. The element with `id="main"` (the page's main content) was converted to GitHub-flavored Markdown with pandoc, after removing scripts, styles, navigation, forms, buttons, empty heading anchors, and syntax-highlighting markup inside code blocks. The text is otherwise verbatim. Images shown on the page were copied into `assets/` (prefixed `cli-`) and their paths changed to point to the copies.

---

# Take GitHub to the command line

GitHub CLI brings GitHub to your terminal. Free and open source.

Install with Homebrew

- 
- 
- 
- <a href="https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian" class="install-option" target="_blank" data-label="Install on Debian/Ubuntu">Linux — apt (Debian, Ubuntu)</a>
- <a href="https://github.com/cli/cli/blob/trunk/docs/install_linux.md#dnf4" class="install-option" target="_blank" data-label="Install on Fedora/RHEL">Linux — dnf (Fedora, RHEL)</a>
- <a href="https://github.com/cli/cli/blob/trunk/docs/install_linux.md#opensusesuse-linux-zypper" class="install-option" target="_blank" data-label="Install on openSUSE/SUSE">Linux — zypper (openSUSE, SUSE)</a>
- 
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_macOS_amd64.zip" class="install-option" data-label="Download for macOS">macOS — Download binary</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_windows_amd64.msi" class="install-option" data-label="Download for Windows">Windows — Download MSI</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.deb" class="install-option" data-label="Download .deb">Linux — Download .deb</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.rpm" class="install-option" data-label="Download .rpm">Linux — Download .rpm</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.tar.gz" class="install-option" data-label="Download .tar.gz">Linux — Download .tar.gz</a>

`brew install gh` <a href="#" class="install-cta install-cta-download d-none" aria-label="Download installer">Install</a>

## \$ gh copilot gh issue list gh pr status gh pr checkout gh pr create gh pr checks gh release create gh repo view gh alias set

Run GitHub Copilot CLI.

View and filter a repository's open issues.

Check on the status of your pull requests.

Check out pull requests locally.

Create a new pull request.

View your pull requests' checks.

Create a new release.

View repository READMEs.

Create a shortcut for a gh command.

\$

gh copilot

  

``` copilot-init-mascot
╭────────────────────────────────────────────────────────────────────────╮
│ ╭─╮╭─╮  GitHub Copilot v1.0.39                                         │
│ ╰─╯╰─╯  Describe a task to get started.                                │
│ █ ▘▝ █                                                                 │
│  ▔▔▔▔                                                                  │
│                                                                        │
│ Tip: /init Initialize Copilot instructions for this repository.        │
│ Copilot uses AI. Check for mistakes.                                   │
╰────────────────────────────────────────────────────────────────────────╯
```

  
● Environment loaded: 2 custom instructions, 19 skills, 6 MCP servers, 4 plugins, 3 agents  
  
● GitHub MCP Server: Connected

gh issue list

  
**Showing 4 of 4 issues in cli/cli**  
  
\#16 Improving interactions with protected branches  
\#14 PR commands on a detached head  
\#13 Support for GitHub Enterprise (enhancement)  
\#8 Add an easier upgrade command (bug)

gh pr status

  
Relevant pull requests in cli/cli  
  
**Current branch**  
There is no pull request associated with \[fix-homepage-bug\]  
  
**Created by you**  
You have no open pull requests  
  
**Requesting a code review from you**  
\#100 Fix footer on homepage \[fix-homepage-footer\]  
✓ Checks passing - Review pending

gh pr checkout 12

remote: Enumerating objects: 66, done.  
remote: Counting objects: 100% (66/66), done.  
remote: Total 83 (delta 66), reused 66 (delta 66), pack-reused 17  
Unpacking objects: 100% (83/83), done.  
From https://github.com/owner/repo  
\* \[new ref\] refs/pull/8896/head -\> patch-2  
M README.md  
Switched to branch 'patch-2'

gh pr create

  
Creating pull request for feature-branch into main in ampinsk/test  
  
**? Title** My new pull request  
**? Body** \[(e) to launch vim, enter to skip\]  
**? What's next?** Submit  
https://github.com/owner/repo/pull/1

gh pr checks

**All checks were successful**  
1 failing, 3 successful, and 1 pending checks  
  
- CodeQL 3m43s https://github.com/cli/cli/runs/123  
✓ build (macos-latest) 4m18s https://github.com/cli/cli/runs/123  
✓ build (ubuntu-latest) 1m23s https://github.com/cli/cli/runs/123  
✓ build (windows-latest) 4m43s https://github.com/cli/cli/runs/123  
× lint 47s https://github.com/cli/cli/runs/123  

gh release create 1.0

**? Title** GitHub CLI 1.0  
**? Release notes** Write my own  
**? Is this a prerelease?** No  
**? Submit?** Publish release  
https://github.com/octocat/.github/releases/tag/1.0

gh repo view

**cli/cli**  
GitHub’s official command line tool  
  
**GitHub CLI**  
  

gh is GitHub on the command line. It brings pull requests, issues, and other GitHub concepts to the terminal next to where you are already working with git and your code.

  
  

Image: screenshot of gh pr status → https://user-images.githubusercontent.com/98482/84171218-327e7a80-aa40-11ea-8cd1-5177fc2d0e72.png

  
  
View this repository on GitHub: https://github.com/cli/cli

gh alias set bugs 'issue list --label="bugs"'

\- Adding alias for bugs: issue list --label="bugs"  
✓ Added alias.  
  
\$ gh bugs  
  
**Showing 2 of 7 issues in cli/cli that match your search**  
  
\#19 Pagination request returns empty JSON (bug)  
\#21 Error raised when passing valid parameters (bug)  

<a href="/manual/gh" class="h5-mktg color-fg-default Bump-link mx-auto mx-lg-0 no-underline mb-5">View all GitHub CLI commands →</a>

## Goodbye, context switching. Hello, terminal.

### Your entire GitHub workflow

Work with issues, pull requests, checks, releases and more.

<a href="/manual/gh" class="f6-mktg Bump-link no-underline">View all GitHub CLI commands →</a>

### Script and customize

Call the GitHub API to script almost any action, and set a custom alias for any command.

<a href="/manual" class="f6-mktg Bump-link no-underline">Learn about aliases and API →</a>

### Enterprise-ready

Connect to GitHub Enterprise Server in addition to GitHub.com.

<a href="/manual#github-enterprise" class="f6-mktg Bump-link no-underline">Get set up with Enterprise →</a>

### We \<3 community

GitHub CLI is open source and ready for your contributions.

<a href="https://github.com/cli/cli" class="f6-mktg Bump-link no-underline">Contribute to CLI →</a>

## Try GitHub on the command line

GitHub CLI brings GitHub to your terminal. Free and open source.

Install with Homebrew

- 
- 
- 
- <a href="https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian" class="install-option" target="_blank" data-label="Install on Debian/Ubuntu">Linux — apt (Debian, Ubuntu)</a>
- <a href="https://github.com/cli/cli/blob/trunk/docs/install_linux.md#dnf4" class="install-option" target="_blank" data-label="Install on Fedora/RHEL">Linux — dnf (Fedora, RHEL)</a>
- <a href="https://github.com/cli/cli/blob/trunk/docs/install_linux.md#opensusesuse-linux-zypper" class="install-option" target="_blank" data-label="Install on openSUSE/SUSE">Linux — zypper (openSUSE, SUSE)</a>
- 
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_macOS_amd64.zip" class="install-option" data-label="Download for macOS">macOS — Download binary</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_windows_amd64.msi" class="install-option" data-label="Download for Windows">Windows — Download MSI</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.deb" class="install-option" data-label="Download .deb">Linux — Download .deb</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.rpm" class="install-option" data-label="Download .rpm">Linux — Download .rpm</a>
- <a href="https://github.com/cli/cli/releases/download/v2.102.0/gh_2.102.0_linux_amd64.tar.gz" class="install-option" data-label="Download .tar.gz">Linux — Download .tar.gz</a>

`brew install gh` <a href="#" class="install-cta install-cta-download d-none" aria-label="Download installer">Install</a>

<a href="https://github.com/cli/cli#installation" class="mt-4 d-block f5-mktg Bump-link mx-auto mx-lg-0 no-underline" target="_blank">View installation instructions →</a>

<img src="assets/cli-icon-windows.svg" class="mr-4" style="width: 24px;" alt="Windows" /> <img src="assets/cli-icon-mac.svg" class="mr-4" style="width: 24px;" alt="Mac" /> <img src="assets/cli-icon-linux.svg" style="width: 24px;" alt="Linux" />

<img src="assets/cli-square-pattern.png" class="bottom-0 position-absolute" width="1680" height="450" />
