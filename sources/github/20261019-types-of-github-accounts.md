# Source Snapshot: Types of GitHub accounts

- **Accessed:** 2026-10-19
- **Type:** official documentation (GitHub Docs)
- **URL:** https://docs.github.com/en/get-started/learning-about-github/types-of-github-accounts
- **Upstream file:** [`github/docs` → `content/get-started/learning-about-github/types-of-github-accounts.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/content/get-started/learning-about-github/types-of-github-accounts.md) at commit `dae83f7` (2026-10-16)
- **Version shown:** GitHub.com "Free, Pro & Team" (`fpt`). The page source uses Liquid: `{% ifversion %}` blocks select text per product version; the site shows the `fpt` branch of each block.
- **Included files:** the published page pulls in text with `{% data reusables.* %}` tags and decides `{% ifversion %}` blocks with feature flags. These files are appended verbatim after the page, under "Included files", from the same commit: [`data/reusables/accounts/your-personal-account.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/accounts/your-personal-account.md); [`data/reusables/organizations/organization-plans.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/organizations/organization-plans.md); [`data/reusables/gated-features/more-info.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/gated-features/more-info.md); [`data/reusables/enterprise/link-to-ghec-trial.md`](https://github.com/github/docs/blob/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/reusables/enterprise/link-to-ghec-trial.md)
- **Variables:** `{% data variables.* %}` tags render short values from `data/variables/*.yml`; the values used on this page are listed under "Variable values" at the end.

---

---
title: Types of GitHub accounts
intro: 'Accounts on {% data variables.product.github %} allow you to organize and control access to code.'
redirect_from:
  - /manage-multiple-clients
  - /managing-clients
  - /articles/what-s-the-difference-between-user-and-organization-accounts
  - /articles/differences-between-user-and-organization-accounts
  - /articles/types-of-github-accounts
  - /github/getting-started-with-github/types-of-github-accounts
  - /github/getting-started-with-github/learning-about-github/types-of-github-accounts
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
category:
  - Explore GitHub plans and features
---

## About accounts

With {% data variables.product.github %}, you can store and collaborate on code. Accounts allow you to organize and control access to that code. There are three types of accounts on {% data variables.product.github %}.
* User accounts
* Organization accounts
* Enterprise accounts

Every person who uses {% data variables.product.github %} signs in to a user account. An organization account enhances collaboration between multiple users, and {% ifversion fpt or ghec %}an enterprise account{% else %}the enterprise account for {% data variables.location.product_location %}{% endif %} allows central management of multiple organizations.

## User accounts

{% data reusables.accounts.your-personal-account %}

Your user account can own resources such as repositories, packages, and projects. Any time you take any action on {% data variables.product.github %}, such as creating an issue or reviewing a pull request, the action is attributed to your user account.

User accounts are intended for humans, but you can create accounts to automate activity on {% data variables.product.github %}. This type of account is called a machine user. For example, you can create a machine user account to automate continuous integration (CI) workflows.

{% ifversion fpt or ghec %}

There are two types of user accounts:

* [Personal accounts](#personal-accounts)
* [{% data variables.enterprise.prodname_managed_users_caps %}](#managed-user-accounts)

### Personal accounts

If you signed up for your own account on {% data variables.product.prodname_dotcom_the_website %}, you are using a personal account.

Each personal account uses either {% data variables.product.prodname_free_user %} or {% data variables.product.prodname_pro %}. All personal accounts can own an unlimited number of public and private repositories, with an unlimited number of collaborators on those repositories. If you use {% data variables.product.prodname_free_user %}, private repositories owned by your personal account have a limited feature set. You can upgrade to {% data variables.product.prodname_pro %} to get a full feature set for private repositories. For more information, see [AUTOTITLE](/get-started/learning-about-github/githubs-plans).

Many people use one personal account for all their work on {% data variables.product.prodname_dotcom_the_website %}, including both open source projects and paid employment. If you're currently using more than one personal account that you created for yourself, we suggest combining the accounts. For more information, see [AUTOTITLE](/account-and-profile/how-tos/account-management/merging-multiple-personal-accounts).

Even if you're a member of an organization that uses SAML single sign-on, you will still sign in to your own personal account on {% data variables.product.prodname_dotcom_the_website %}, and that personal account will be linked to your identity in your organization's identity provider (IdP). For more information, see [AUTOTITLE](/enterprise-cloud@latest/authentication/authenticating-with-single-sign-on/about-authentication-with-single-sign-on){% ifversion fpt %}" in the {% data variables.product.prodname_ghe_cloud %} documentation.{% else %}.{% endif %}

### {% data variables.enterprise.prodname_managed_users_caps %}

If your account was created for you by an enterprise on {% data variables.product.prodname_ghe_cloud %}, you are using a {% data variables.enterprise.prodname_managed_user %}.

As a {% data variables.enterprise.prodname_managed_user %}:

* Some of your account details and settings are managed by your enterprise.
* You must sign in to your {% data variables.enterprise.prodname_managed_user %} to access organizations and repositories owned by the enterprise.
* You can create your own private repositories, but you cannot create public content or contribute to repositories outside the enterprise.

{% endif %}

## Organization accounts

Organizations are shared accounts where a large number of people can collaborate across many projects at once.

Like user accounts, organizations can own resources such as repositories, packages, and projects. However, you cannot sign in to an organization. Instead, each person signs in to their user account, and any actions the person takes on organization resources are attributed to their user account. Each user can be a member of multiple organizations.

The users within an organization can be given different roles in the organization, which grant different levels of access to the organization and its data. All members can collaborate with each other in repositories and projects, but only organization owners and security managers can manage the settings for the organization and control access to the organization's data with sophisticated security and administrative features. For more information, see [AUTOTITLE](/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization) and [AUTOTITLE](/organizations/keeping-your-organization-secure).

You can also create nested sub-groups of organization members called teams, to reflect your group's structure and simplify access management. For more information, see [AUTOTITLE](/organizations/organizing-members-into-teams/about-teams).

{% data reusables.organizations.organization-plans %}

For more information about all the features of organizations, see [AUTOTITLE](/organizations/collaborating-with-groups-in-organizations/about-organizations).

## Enterprise accounts

{% ifversion fpt %}
{% data variables.product.prodname_ghe_cloud %} and {% data variables.product.prodname_ghe_server %} include enterprise accounts, which allow administrators to centrally manage policy and billing for multiple organizations and enable innersourcing between the organizations. For more information, see [AUTOTITLE](/enterprise-cloud@latest/admin/concepts/enterprise-fundamentals/enterprise-accounts) in the {% data variables.product.prodname_ghe_cloud %} documentation.
{% elsif ghec %}
Enterprise accounts allow central policy management and billing for multiple organizations. You can use your enterprise account to centrally manage policy and billing. Unlike organizations, enterprise accounts cannot directly own resources like repositories, packages, or projects. These resources are owned by organizations within the enterprise account instead. For more information, see [AUTOTITLE](/admin/concepts/enterprise-fundamentals/enterprise-accounts).
{% elsif ghes %}
Your enterprise account is a collection of all the organizations on {% data variables.location.product_location %}. You can use your enterprise account to centrally manage policy and billing. Unlike organizations, enterprise accounts cannot directly own resources like repositories, packages, or projects. These resources are owned by organizations within the enterprise account instead. For more information, see [AUTOTITLE](/admin/concepts/enterprise-fundamentals/enterprise-accounts).
{% endif %}

## Further reading

* [AUTOTITLE](/account-and-profile/how-tos/account-management/creating-an-account-on-github)
* [AUTOTITLE](/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch)
* [Organizing people for successful collaboration](https://vimeo.com/333786093) video in {% data variables.product.company_short %} Resources

---

## Included files

### `data/reusables/accounts/your-personal-account.md`

````markdown
Every person who uses {% data variables.product.github %} signs in to a user account. Your user account is your identity on {% data variables.product.github %} and has a username and profile. For example, see [@octocat's profile](https://github.com/octocat).
````

### `data/reusables/organizations/organization-plans.md`

````markdown
{% ifversion fpt or ghec %}
You can use organizations for free, with {% data variables.product.prodname_free_team %}, which includes limited features on private repositories. To get the full feature set on private repositories and additional features at the organization level, including SAML single sign-on and improved support coverage, you can upgrade to {% data variables.product.prodname_team %} or {% data variables.product.prodname_ghe_cloud %}. {% data reusables.gated-features.more-info %}

Organizations are limited to owning 100,000 repositories, to create additional repositories you can create additional organizations.

{% ifversion fpt %}
{% data reusables.enterprise.link-to-ghec-trial %}{% endif %}
{% endif %}
````

### `data/reusables/gated-features/more-info.md`

````markdown
See [AUTOTITLE](/get-started/learning-about-github/githubs-plans).
````

### `data/reusables/enterprise/link-to-ghec-trial.md`

````markdown
For more information about how you can try {% data variables.product.prodname_ghe_cloud %} for free, see [Setting up a trial of {% data variables.product.prodname_ghe_cloud %}](/admin/overview/setting-up-a-trial-of-github-enterprise-cloud).
````

## Variable values

From `data/variables/*.yml` at the same commit ([folder](https://github.com/github/docs/tree/dae83f7d28f3b8e10015bd6b6d8b72267cedceca/data/variables)).

| Tag | Value |
|-----|-------|
| `{% data variables.product.github %}` | GitHub |
| `{% data variables.location.product_location %}` | {% ifversion ghes %}your GitHub Enterprise Server instance{% else %}GitHub.com{% endif %} |
| `{% data variables.enterprise.prodname_managed_users_caps %}` | Managed user accounts |
| `{% data variables.product.prodname_dotcom_the_website %}` | GitHub.com |
| `{% data variables.product.prodname_free_user %}` | GitHub Free |
| `{% data variables.product.prodname_pro %}` | GitHub Pro |
| `{% data variables.product.prodname_ghe_cloud %}` | GitHub Enterprise Cloud |
| `{% data variables.enterprise.prodname_managed_user %}` | managed user account |
| `{% data variables.product.prodname_ghe_server %}` | GitHub Enterprise Server |
| `{% data variables.product.company_short %}` | GitHub |
| `{% data variables.product.prodname_free_team %}` | GitHub Free |
| `{% data variables.product.prodname_team %}` | GitHub Team |
