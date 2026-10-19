# Source Snapshot: Adding a new SSH key to your GitHub account

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
- **Upstream file:** [`github/docs` → `content/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/ssh/about-ssh.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/ssh/about-ssh.md); [`data/reusables/ssh/key-type-support.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/ssh/key-type-support.md); [`data/reusables/gpg/copy-ssh-public-key.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gpg/copy-ssh-public-key.md); [`data/reusables/user-settings/access_settings.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/user-settings/access_settings.md); [`data/reusables/user-settings/ssh.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/user-settings/ssh.md); [`data/reusables/user-settings/sudo-mode-popup.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/user-settings/sudo-mode-popup.md); [`data/reusables/cli/cli-learn-more.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/cli/cli-learn-more.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Adding a new SSH key to your GitHub account
intro: 'To configure your account on {% data variables.location.product_location %} to use your new (or existing) SSH key, you''ll also need to add the key to your account.'
redirect_from:
  - /articles/adding-a-new-ssh-key-to-your-github-account
  - /github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account
  - /github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Add a new SSH key
category:
  - Connect with SSH
---

## About addition of SSH keys to your account

{% data reusables.ssh.about-ssh %} For more information, see [AUTOTITLE](/authentication/connecting-to-github-with-ssh/about-ssh).

You can also use SSH to sign commits and tags. For more information about commit signing, see [AUTOTITLE](/authentication/managing-commit-signature-verification/about-commit-signature-verification).

After you generate an SSH key pair, you must add the public key to {% data variables.location.product_location %} to enable SSH access for your account.

## Prerequisites

Before adding a new SSH key to your account on {% data variables.location.product_location %}, complete the following steps.

1. Check for existing SSH keys. For more information, see [AUTOTITLE](/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys).
1. Generate a new SSH key and add it to your machine's SSH agent. For more information, see [AUTOTITLE](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

## Adding a new SSH key to your account

You can add an SSH key and use it for authentication, or commit signing, or both. If you want to use the same SSH key for both authentication and signing, you need to upload it twice.

After adding a new SSH authentication key to your account on {% data variables.location.product_location %}, you can reconfigure any local repositories to use SSH. For more information, see [AUTOTITLE](/get-started/git-basics/managing-remote-repositories#switching-remote-urls-from-https-to-ssh).

{% data reusables.ssh.key-type-support %}

{% webui %}

{% data reusables.gpg.copy-ssh-public-key %}

{% data reusables.user-settings.access_settings %}

{% data reusables.user-settings.ssh %}

1. Click **New SSH key** or **Add SSH key**.
1. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".
1. Select the type of key, either authentication or signing. For more information about commit signing, see [AUTOTITLE](/authentication/managing-commit-signature-verification/about-commit-signature-verification).
1. In the "Key" field, paste your public key.
1. Click **Add SSH key**.
{% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

Before you can use the {% data variables.product.prodname_cli %} to add an SSH key to your account, you must authenticate to the {% data variables.product.prodname_cli %}. For more information, see [`gh auth login`](https://cli.github.com/manual/gh_auth_login) in the {% data variables.product.prodname_cli %} documentation.

To add an SSH key to your GitHub account, use the `ssh-key add` subcommand, specifying your public key. For authentication keys, if you're prompted to request additional scopes, follow the instructions in the command line.

```shell
gh ssh-key add KEY-FILE --type {authentication|signing}
```

To include a title for the new key, use the `-t` or `--title` flag.

```shell
gh ssh-key add KEY-FILE --title "personal laptop"
```

If you generated your SSH key by following the instructions in [AUTOTITLE](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), you can add the key to your account with this command.

```shell
gh ssh-key add ~/.ssh/id_ed25519.pub --type signing
```

{% endcli %}

{% ifversion fpt or ghec %}

## Further reading

* [AUTOTITLE](/authentication/authenticating-with-single-sign-on/authorizing-an-ssh-key-for-use-with-single-sign-on)
{% endif %}

---

## Included files

### `data/reusables/ssh/about-ssh.md`

````markdown
You can access and write data in repositories on {% data variables.product.prodname_dotcom %} using SSH (Secure Shell Protocol). When you connect via SSH, you authenticate using a private key file on your local machine.
````

### `data/reusables/ssh/key-type-support.md`

````markdown
{% ifversion fpt or ghec %}

> [!NOTE]
> {% data variables.product.company_short %} improved security by dropping older, insecure key types on March 15, 2022.
>
> As of that date, DSA keys (`ssh-dss`) are no longer supported. You cannot add new DSA keys to your personal account on {% data variables.product.prodname_dotcom %}.
>
> RSA keys (`ssh-rsa`) with a `valid_after` before November 2, 2021 may continue to use any signature algorithm. RSA keys generated after that date must use a SHA-2 signature algorithm. Some older clients may need to be upgraded in order to use SHA-2 signatures.

{% endif %}
````

### `data/reusables/gpg/copy-ssh-public-key.md`

````markdown
1. Copy the SSH public key to your clipboard.

   If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.
   {% mac %}

   ```shell
   $ pbcopy < ~/.ssh/id_ed25519.pub
   # Copies the contents of the id_ed25519.pub file to your clipboard
   ```

   > [!TIP]
   > If `pbcopy` isn't working, you can locate the hidden `.ssh` folder, open the file in your favorite text editor, and copy it to your clipboard.

   {% endmac %}
   {% windows %}

   ```shell
   $ clip < ~/.ssh/id_ed25519.pub
   # Copies the contents of the id_ed25519.pub file to your clipboard
   ```

   > [!NOTE]
   > * With Windows Subsystem for Linux (WSL), you can use `clip.exe`. Otherwise if `clip` isn't working, you can locate the hidden `.ssh` folder, open the file in your favorite text editor, and copy it to your clipboard.
   > * On newer versions of Windows that use the {% data variables.product.prodname_windows_terminal %}, or anywhere else that uses the PowerShell command line, you may receive a `ParseError` stating that `The '&lt;' operator is reserved for future use.` In this case, the following alternative `clip` command should be used:
   >
   > ```shell
   > $ cat ~/.ssh/id_ed25519.pub | clip
   > # Copies the contents of the id_ed25519.pub file to your clipboard
   > ```

   {% endwindows %}
   {% linux %}

   ```shell
   $ cat ~/.ssh/id_ed25519.pub
   # Then select and copy the contents of the id_ed25519.pub file
   # displayed in the terminal to your clipboard
   ```

   > [!TIP]
   > Alternatively, you can locate the hidden `.ssh` folder, open the file in your favorite text editor, and copy it to your clipboard.

   {% endlinux %}
````

### `data/reusables/user-settings/access_settings.md`

````markdown
1. In the upper-right corner of any page on {% data variables.product.prodname_dotcom %}, click your profile picture, then click **{% octicon "gear" aria-hidden="true" aria-label="gear" %} Settings**.
````

### `data/reusables/user-settings/ssh.md`

````markdown
1. In the "Access" section of the sidebar, click **{% octicon "key" aria-hidden="true" aria-label="key" %} SSH and GPG keys**.
````

### `data/reusables/user-settings/sudo-mode-popup.md`

````markdown
1. If prompted, confirm access to your account on {% data variables.product.github %}. For more information, see [AUTOTITLE](/authentication/keeping-your-account-and-data-secure/sudo-mode).
````

### `data/reusables/cli/cli-learn-more.md`

````markdown
> [!NOTE]
> To learn more about {% data variables.product.prodname_cli %}, see [AUTOTITLE](/github-cli/github-cli/about-github-cli).
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.product.prodname_cli %}` | GitHub CLI |
| `{% data variables.product.prodname_dotcom %}` | GitHub |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.prodname_windows_terminal %}` | Windows Terminal |
| `{% data variables.product.github %}` | GitHub |
