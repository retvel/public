# Source Snapshot: Testing your SSH connection

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection
- **Upstream file:** [`github/docs` → `content/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/enterprise-data-residency/access-domain.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/enterprise-data-residency/access-domain.md); [`data/reusables/command_line/open_the_multi_os_terminal.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/command_line/open_the_multi_os_terminal.md); [`data/reusables/enterprise-data-residency/ssh-user.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/enterprise-data-residency/ssh-user.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Testing your SSH connection
intro: "After you've set up your SSH key and added it to {% data variables.product.prodname_dotcom %}, you can test your connection."
redirect_from:
  - /articles/testing-your-ssh-connection
  - /github/authenticating-to-github/testing-your-ssh-connection
  - /github/authenticating-to-github/connecting-to-github-with-ssh/testing-your-ssh-connection
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Test your SSH connection
category:
  - Connect with SSH
---

Before testing your SSH connection, you should have already:
* [Checked for existing SSH keys](/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)
* [Generated a new SSH key](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
* [Added a new SSH key to your GitHub account](/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

You'll need to authenticate this action using your password, which is the SSH key passphrase you created earlier. See [AUTOTITLE](/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases).

{% ifversion ghec %}

> [!NOTE] {% data reusables.enterprise-data-residency.access-domain %}

{% endif %}

{% data reusables.command_line.open_the_multi_os_terminal %}
1. Enter the following:

   ```shell copy
   ssh -T git@{% data variables.product.product_url %}
   # Attempts to ssh to {% data variables.product.github %}
   ```

   You may see a warning like this:

   ```shell
   > The authenticity of host '{% data variables.product.product_url %} (IP ADDRESS)' can't be established.
   > ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
   > Are you sure you want to continue connecting (yes/no)?
   ```

1. Verify that the fingerprint in the message you see matches {% ifversion fpt or ghec %}[{% data variables.product.prodname_dotcom %}'s public key fingerprint](/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints){% else %} your enterprise's public key fingerprint{% endif %}. If it does, then type `yes`:

   ```shell
   > Hi USERNAME! You've successfully authenticated, but GitHub does not
   > provide shell access.
   ```

   {% linux %}

   You may see this error message:

   ```shell
   ...
   Agent admitted failure to sign using the key.
   debug1: No more authentication methods to try.
   Permission denied (publickey).
   ```

   This is a known problem with certain Linux distributions. For more information, see [AUTOTITLE](/authentication/troubleshooting-ssh/error-agent-admitted-failure-to-sign).

   {% endlinux %}

   > [!NOTE]
   > The remote command should exit with code 1.

1. Verify that the resulting message contains your username. If you receive a "permission denied" message, see [AUTOTITLE](/authentication/troubleshooting-ssh/error-permission-denied-publickey).

{% ifversion ghec or fpt %}

> [!TIP] {% data reusables.enterprise-data-residency.ssh-user %}
>
> ```shell
> ssh -T {% data variables.enterprise.data_residency_example_git_ssh %}
> # Attempts to ssh to {% data variables.enterprise.data_residency_example_domain %}
> ```

{% endif %}

---

## Included files

### `data/reusables/enterprise-data-residency/access-domain.md`

````markdown
This article contains commands or examples that use the `{% data variables.product.product_url %}` domain. You might access {% data variables.product.github %} at a different domain, such as `{% data variables.enterprise.data_residency_example_domain %}`.
````

### `data/reusables/command_line/open_the_multi_os_terminal.md`

````markdown
1. Open <span class="platform-mac">Terminal</span><span class="platform-linux">Terminal</span><span class="platform-windows">Git Bash</span>.
````

### `data/reusables/enterprise-data-residency/ssh-user.md`

````markdown
If you are accessing {% data variables.product.github %} at a different domain such as `{% data variables.enterprise.data_residency_example_domain %}`, then you need to replace `git@{% data variables.product.product_url %}` with `{% data variables.enterprise.data_residency_example_git_ssh %}`.
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.product_url %}` | {% ifversion fpt or ghec %}github.com{% else %}HOSTNAME{% endif %} |
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.enterprise.data_residency_example_git_ssh %}` | octocorp@octocorp.ghe.com |
| `{% data variables.enterprise.data_residency_example_domain %}` | octocorp.ghe.com |
