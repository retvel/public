# Source Snapshot: Kali's Default Credentials | Kali Linux Documentation

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kali Linux Documentation)
- **URL:** https://www.kali.org/docs/introduction/default-credentials/
- **Upstream file:** [`kalilinux/documentation/kali-docs (GitLab)` → `introduction/default-credentials/index.md`](https://gitlab.com/kalilinux/documentation/kali-docs/-/blob/d5aef7dd93fb7b533fb6992f1817f8f6cd9e73c0/introduction/default-credentials/index.md) at commit `d5aef7d` (2026-10-08)
- **License:** Kali Linux documentation — © OffSec / Kali Linux team; GNU General Public License v3. See [LICENSE-kali-docs](LICENSE-kali-docs). Reproduced verbatim and unmodified below this line.

---

---
title: Kali's Default Credentials
description: What is Kali's password
icon:
weight: 60
author: ["g0tmi1k",]
---

Kali changed to a [non-root user policy](/docs/policy/kali-linux-user-policy/) by default [since the release of **2020.1**](/blog/kali-default-non-root-user/).

This means:

- During the installation of [**amd64** images](/docs/installation/), it will prompt you for a standard user account to be created.

- Any default operating system credentials used during **Live Boot**, or **pre-created image** (like **[Virtual Machines](/docs/virtualization/)** & **[ARM](/docs/arm/)**) will be:
    - User: `kali`
    - Password: `kali`

- **Vagrant** image _(based on their [policy](https://www.vagrantup.com/docs/boxes/base.html))_:
    - Username: `vagrant`
    - Password: `vagrant`

- [Amazon **EC2**](/docs/cloud/aws/):
    - User: `kali`
    - Password: `<ssh key>`

## Default Tool Credentials

Some tools shipped with Kali, will use their own default hardcoded credentials (others will generate a new password the first time its used). The following tools have the default values:

- [BeEF-XSS](/tools/beef-xss/)
    - Username: `beef`
    - Password: `beef`
    - Configuration File: `/etc/beef-xss/config.yaml`

- MySQL
    - User: `root`
    - Password: ` ` _(blank)_
    - Setup Program: `mysql_secure_installation`

- [OpenVAS](/tools/gvm/)
    - Username: `admin`
    - Password: `<Generated during setup>`
    - Setup Program: `openvas-setup`

- [Metasploit-Framework](/tools/metasploit-framework/)
    - Username: `postgres`
    - Password: `postgres`
    - Configuration File: `/usr/share/metasploit-framework/config/database.yml`

- [PowerShell-Empire/Starkiller](/tools/powershell-empire/)
    - Username: `empireadmin`
    - Password: `password123`

- [Bloodhound](/tools/bloodhound/)
    - Username: `admin`
    - Password: `admin`

- - -

For versions of Kali Linux older than [2020.1](/blog/kali-linux-2020-1-release/), here is our [previous credential information](/docs/introduction/kali-linux-default-passwords/) and [root policy](/docs/policy/kali-linux-root-user-policy/) information.
