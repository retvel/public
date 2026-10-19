# Source Snapshot: Dealing with non-fast-forward errors

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/get-started/using-git/dealing-with-non-fast-forward-errors
- **Upstream file:** [`github/docs` → `content/get-started/using-git/dealing-with-non-fast-forward-errors.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/get-started/using-git/dealing-with-non-fast-forward-errors.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Dealing with non-fast-forward errors
intro: 'Sometimes, Git can''t make your change to a remote repository without losing commits. When this happens, your push is refused.'
redirect_from:
  - /articles/dealing-with-non-fast-forward-errors
  - /github/using-git/dealing-with-non-fast-forward-errors
  - /github/getting-started-with-github/dealing-with-non-fast-forward-errors
  - /github/getting-started-with-github/using-git/dealing-with-non-fast-forward-errors
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Non-fast-forward error
category:
  - Work with Git
---
If another person has pushed to the same branch as you, Git won't be able to push your changes:

```shell
$ git push origin main
> To https://{% data variables.product.product_url %}/USERNAME/REPOSITORY.git
>  ! [rejected]        main -> main (non-fast-forward)
> error: failed to push some refs to 'https://{% data variables.product.product_url %}/USERNAME/REPOSITORY.git'
> To prevent you from losing history, non-fast-forward updates were rejected
> Merge the remote changes (e.g. 'git pull') before pushing again. See the
> 'Note about fast-forwards' section of 'git push --help' for details.
```

You can fix this by [fetching and merging](/get-started/using-git/getting-changes-from-a-remote-repository) the changes made on the remote branch with the changes that you have made locally:

```shell
$ git fetch origin
# Fetches updates made to an online repository
$ git merge origin YOUR_BRANCH_NAME
# Merges updates made online with your local work
```

Or, you can simply use `git pull` to perform both commands at once:

```shell
$ git pull origin YOUR_BRANCH_NAME
# Grabs online updates and merges them with your local work
```

---


## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.product_url %}` | {% ifversion fpt or ghec %}github.com{% else %}HOSTNAME{% endif %} |
