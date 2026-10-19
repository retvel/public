# Source Snapshot: Install and Set Up kubectl on Linux

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kubernetes Docs)
- **URL:** https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
- **Upstream file:** [`kubernetes/website` → `content/en/docs/tasks/tools/install-kubectl-linux.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/install-kubectl-linux.md) at commit `1fc565c` (2026-10-19)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0) — Copyright The Kubernetes Authors ("Documentation Distributed under CC BY 4.0"). See [LICENSE-kubernetes-website](LICENSE-kubernetes-website). Reproduced verbatim and unmodified below this line.
- **Included files:** the published page pulls these files in when the site is built (code samples, shared includes, partials). They are appended verbatim after the page, under "Included files", from the same commit: [`content/en/docs/tasks/tools/included/verify-kubectl.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/included/verify-kubectl.md); [`content/en/docs/tasks/tools/included/kubectl-convert-overview.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/included/kubectl-convert-overview.md); [`content/en/docs/tasks/tools/included/kubectl-whats-next.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/included/kubectl-whats-next.md); [`content/en/docs/tasks/tools/included/optional-kubectl-configs-bash-linux.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/included/optional-kubectl-configs-bash-linux.md); [`content/en/docs/tasks/tools/included/optional-kubectl-configs-fish.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/included/optional-kubectl-configs-fish.md); [`content/en/docs/tasks/tools/included/optional-kubectl-configs-zsh.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/included/optional-kubectl-configs-zsh.md); [`data/releases/schedule.yaml`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/data/releases/schedule.yaml)
- **Release data:** the release tables on this page are rendered by shortcodes (`release-data`, `upcoming-releases`, `eol-releases`, `release-branches`, `skew currentPatchVersion`) from the `data/releases/*.yaml` files listed under Included files.
- **Version values:** the `skew` and `param` shortcodes render from [`hugo.toml`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/hugo.toml) (`latest = "v1.37"`, `version = "v1.37"`). So `{{< skew currentVersion >}}` and `{{< skew latestVersion >}}` = `1.37`, `{{< param "version" >}}` = `v1.37`, `currentVersionAddMinor -1` = `1.36` (`-2` = `1.35`, `-3` = `1.34`, `+1` = `1.38`), `prevMinorVersion` = `1.36`, `nextMinorVersion` = `1.38`, `oldestMinorVersion` = `1.35`. `{{< skew currentPatchVersion >}}` renders the newest released patch of 1.37 listed in `data/releases/schedule.yaml` at this commit: `1.37.1`.

---

---
reviewers:
- mikedanese
title: Install and Set Up kubectl on Linux
content_type: task
weight: 10
---

## {{% heading "prerequisites" %}}

You must use a kubectl version that is within one minor version difference of
your cluster. For example, a v{{< skew currentVersion >}} client can communicate
with v{{< skew currentVersionAddMinor -1 >}}, v{{< skew currentVersionAddMinor 0 >}},
and v{{< skew currentVersionAddMinor 1 >}} control planes.
Using the latest compatible version of kubectl helps avoid unforeseen issues.

## Install kubectl on Linux

The following methods exist for installing kubectl on Linux:

- [Install kubectl binary with curl on Linux](#install-kubectl-binary-with-curl-on-linux)
- [Install using native package management](#install-using-native-package-management)
- [Install using other package management](#install-using-other-package-management)

### Install kubectl binary with curl on Linux

1. Download the latest release with the command:

   {{< tabs name="download_binary_linux" >}}
   {{< tab name="x86-64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
   {{< /tab >}}
   {{< tab name="ARM64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl"
   {{< /tab >}}
   {{< /tabs >}}

   {{< note >}}
   To download a specific version, replace the `$(curl -L -s https://dl.k8s.io/release/stable.txt)`
   portion of the command with the specific version.

   For example, to download version {{< skew currentPatchVersion >}} on Linux x86-64, type:

   ```bash
   curl -LO https://dl.k8s.io/release/v{{< skew currentPatchVersion >}}/bin/linux/amd64/kubectl
   ```

   And for Linux ARM64, type:

   ```bash
   curl -LO https://dl.k8s.io/release/v{{< skew currentPatchVersion >}}/bin/linux/arm64/kubectl
   ```

   {{< /note >}}

1. Validate the binary (optional)

   Download the kubectl checksum file:

   {{< tabs name="download_checksum_linux" >}}
   {{< tab name="x86-64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
   {{< /tab >}}
   {{< tab name="ARM64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl.sha256"
   {{< /tab >}}
   {{< /tabs >}}

   Validate the kubectl binary against the checksum file:

   ```bash
   echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
   ```

   If valid, the output is:

   ```console
   kubectl: OK
   ```

   If the check fails, `sha256` exits with nonzero status and prints output similar to:

   ```console
   kubectl: FAILED
   sha256sum: WARNING: 1 computed checksum did NOT match
   ```

   {{< note >}}
   Download the same version of the binary and checksum.
   {{< /note >}}

1. Install kubectl

   ```bash
   sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   ```

   {{< note >}}
   If you do not have root access on the target system, you can still install
   kubectl to the `~/.local/bin` directory:

   ```bash
   chmod +x kubectl
   mkdir -p ~/.local/bin
   mv ./kubectl ~/.local/bin/kubectl
   # and then append (or prepend) ~/.local/bin to $PATH
   ```

   {{< /note >}}

1. Test to ensure the version you installed is up-to-date:

   ```bash
   kubectl version --client
   ```

   Or use this for detailed view of version:

   ```cmd
   kubectl version --client --output=yaml
   ```

### Install using native package management

{{< tabs name="kubectl_install" >}}
{{% tab name="Debian-based distributions" %}}

1. Update the `apt` package index and install packages needed to use the Kubernetes `apt` repository:

   ```shell
   sudo apt-get update
   # apt-transport-https may be a dummy package; if so, you can skip that package
   sudo apt-get install -y apt-transport-https ca-certificates curl gnupg
   ```

2. Download the public signing key for the Kubernetes package repositories. The same signing key is used for all repositories so you can disregard the version in the URL:

   ```shell
   # If the folder `/etc/apt/keyrings` does not exist, it should be created before the curl command, read the note below.
   # sudo mkdir -p -m 755 /etc/apt/keyrings
   curl -fsSL https://pkgs.k8s.io/core:/stable:/{{< param "version" >}}/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
   sudo chmod 644 /etc/apt/keyrings/kubernetes-apt-keyring.gpg # allow unprivileged APT programs to read this keyring
   ```
   
{{< note >}}
In releases older than Debian 12 and Ubuntu 22.04, folder `/etc/apt/keyrings` does not exist by default, and it should be created before the curl command.
{{< /note >}}

3. Add the appropriate Kubernetes `apt` repository. If you want to use Kubernetes version different than {{< param "version" >}},
   replace {{< param "version" >}} with the desired minor version in the command below:

   ```shell
   # This overwrites any existing configuration in /etc/apt/sources.list.d/kubernetes.list
   echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/{{< param "version" >}}/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
   sudo chmod 644 /etc/apt/sources.list.d/kubernetes.list   # helps tools such as command-not-found to work correctly
   ```

{{< note >}}
To upgrade kubectl to another minor release, you'll need to bump the version in `/etc/apt/sources.list.d/kubernetes.list` before running `apt-get update` and `apt-get upgrade`. This procedure is described in more detail in [Changing The Kubernetes Package Repository](/docs/tasks/administer-cluster/kubeadm/change-package-repository/).
{{< /note >}}

4. Update `apt` package index, then install kubectl:

   ```shell
   sudo apt-get update
   sudo apt-get install -y kubectl
   ```

{{% /tab %}}

{{% tab name="Red Hat-based distributions" %}}

1. Add the Kubernetes `yum` repository. If you want to use Kubernetes version
   different than {{< param "version" >}}, replace {{< param "version" >}} with
   the desired minor version in the command below.

   ```bash
   # This overwrites any existing configuration in /etc/yum.repos.d/kubernetes.repo
   cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo
   [kubernetes]
   name=Kubernetes
   baseurl=https://pkgs.k8s.io/core:/stable:/{{< param "version" >}}/rpm/
   enabled=1
   gpgcheck=1
   gpgkey=https://pkgs.k8s.io/core:/stable:/{{< param "version" >}}/rpm/repodata/repomd.xml.key
   EOF
   ```

{{< note >}}
To upgrade kubectl to another minor release, you'll need to bump the version in `/etc/yum.repos.d/kubernetes.repo` before running `dnf update`. This procedure is described in more detail in [Changing The Kubernetes Package Repository](/docs/tasks/administer-cluster/kubeadm/change-package-repository/).
{{< /note >}}

2. Install kubectl using `dnf`:

   ```bash
   sudo dnf install -y kubectl
   ```

{{% /tab %}}

{{% tab name="SUSE-based distributions" %}}

1. Add the Kubernetes `zypper` repository. If you want to use Kubernetes version
   different than {{< param "version" >}}, replace {{< param "version" >}} with
   the desired minor version in the command below.

   ```bash
   # This overwrites any existing configuration in /etc/zypp/repos.d/kubernetes.repo
   cat <<EOF | sudo tee /etc/zypp/repos.d/kubernetes.repo
   [kubernetes]
   name=Kubernetes
   baseurl=https://pkgs.k8s.io/core:/stable:/{{< param "version" >}}/rpm/
   enabled=1
   gpgcheck=1
   gpgkey=https://pkgs.k8s.io/core:/stable:/{{< param "version" >}}/rpm/repodata/repomd.xml.key
   EOF
   ```

{{< note >}}
To upgrade kubectl to another minor release, you'll need to bump the version in `/etc/zypp/repos.d/kubernetes.repo`
before running `zypper update`. This procedure is described in more detail in
[Changing The Kubernetes Package Repository](/docs/tasks/administer-cluster/kubeadm/change-package-repository/).
{{< /note >}}

2. Update `zypper` and confirm the new repo addition:
   
   ```bash
   sudo zypper update
   ```

   When this message appears, press 't' or 'a':

   ```
   New repository or package signing key received:

   Repository:       Kubernetes
   Key Fingerprint:  1111 2222 3333 4444 5555 6666 7777 8888 9999 AAAA
   Key Name:         isv:kubernetes OBS Project <isv:kubernetes@build.opensuse.org>
   Key Algorithm:    RSA 2048
   Key Created:      Thu 25 Aug 2022 01:21:11 PM -03
   Key Expires:      Sat 02 Nov 2024 01:21:11 PM -03 (expires in 85 days)
   Rpm Name:         gpg-pubkey-9a296436-6307a177

   Note: Signing data enables the recipient to verify that no modifications occurred after the data
   were signed. Accepting data with no, wrong or unknown signature can lead to a corrupted system
   and in extreme cases even to a system compromise.

   Note: A GPG pubkey is clearly identified by its fingerprint. Do not rely on the key's name. If
   you are not sure whether the presented key is authentic, ask the repository provider or check
   their web site. Many providers maintain a web page showing the fingerprints of the GPG keys they
   are using.

   Do you want to reject the key, trust temporarily, or trust always? [r/t/a/?] (r): a
   ```
   
3. Install kubectl using `zypper`:

   ```bash
   sudo zypper install -y kubectl
   ```

{{% /tab %}}
{{< /tabs >}}

### Install using other package management

{{< tabs name="other_kubectl_install" >}}
{{% tab name="Snap" %}}
If you are on Ubuntu or another Linux distribution that supports the
[snap](https://snapcraft.io/docs/core/install) package manager, kubectl
is available as a [snap](https://snapcraft.io/) application.

```shell
snap install kubectl --classic
kubectl version --client
```

{{% /tab %}}

{{% tab name="Homebrew" %}}
If you are on Linux and using [Homebrew](https://docs.brew.sh/Homebrew-on-Linux)
package manager, kubectl is available for [installation](https://docs.brew.sh/Homebrew-on-Linux#install).

```shell
brew install kubectl
kubectl version --client
```

{{% /tab %}}

{{< /tabs >}}

## Verify kubectl configuration

{{< include "included/verify-kubectl.md" >}}

## Optional kubectl configurations and plugins

### Enable shell autocompletion

kubectl provides autocompletion support for Bash, Zsh, Fish, and PowerShell,
which can save you a lot of typing.

Below are the procedures to set up autocompletion for Bash, Fish, and Zsh.

{{< tabs name="kubectl_autocompletion" >}}
{{< tab name="Bash" include="included/optional-kubectl-configs-bash-linux.md" />}}
{{< tab name="Fish" include="included/optional-kubectl-configs-fish.md" />}}
{{< tab name="Zsh" include="included/optional-kubectl-configs-zsh.md" />}}
{{< /tabs >}}

### Configure kuberc

See [kuberc](/docs/reference/kubectl/kuberc) for more information.

### Install `kubectl convert` plugin

{{< include "included/kubectl-convert-overview.md" >}}

1. Download the latest release with the command:

   {{< tabs name="download_convert_binary_linux" >}}
   {{< tab name="x86-64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl-convert"
   {{< /tab >}}
   {{< tab name="ARM64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl-convert"
   {{< /tab >}}
   {{< /tabs >}}

1. Validate the binary (optional)

   Download the kubectl-convert checksum file:

   {{< tabs name="download_convert_checksum_linux" >}}
   {{< tab name="x86-64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl-convert.sha256"
   {{< /tab >}}
   {{< tab name="ARM64" codelang="bash" >}}
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl-convert.sha256"
   {{< /tab >}}
   {{< /tabs >}}

   Validate the kubectl-convert binary against the checksum file:

   ```bash
   echo "$(cat kubectl-convert.sha256) kubectl-convert" | sha256sum --check
   ```

   If valid, the output is:

   ```console
   kubectl-convert: OK
   ```

   If the check fails, `sha256` exits with nonzero status and prints output similar to:

   ```console
   kubectl-convert: FAILED
   sha256sum: WARNING: 1 computed checksum did NOT match
   ```

   {{< note >}}
   Download the same version of the binary and checksum.
   {{< /note >}}

1. Install kubectl-convert

   ```bash
   sudo install -o root -g root -m 0755 kubectl-convert /usr/local/bin/kubectl-convert
   ```

1. Verify plugin is successfully installed

   ```shell
   kubectl convert --help
   ```

   If you do not see an error, it means the plugin is successfully installed.

1. After installing the plugin, clean up the installation files:

   ```bash
   rm kubectl-convert kubectl-convert.sha256
   ```

## {{% heading "whatsnext" %}}

{{< include "included/kubectl-whats-next.md" >}}

---

## Included files

### `content/en/docs/tasks/tools/included/verify-kubectl.md`

````markdown
---
title: "verify kubectl install"
description: "How to verify kubectl."
headless: true
_build:
  list: never
  render: never
  publishResources: false
---

In order for kubectl to find and access a Kubernetes cluster, it needs a
[kubeconfig file](/docs/concepts/configuration/organize-cluster-access-kubeconfig/),
which is created automatically when you create a cluster using
[kube-up.sh](https://github.com/kubernetes/kubernetes/blob/master/cluster/kube-up.sh)
or successfully deploy a Minikube cluster.
By default, kubectl configuration is located at `~/.kube/config`.

Check that kubectl is properly configured by getting the cluster state:

```shell
kubectl cluster-info
```

If you see a URL response, kubectl is correctly configured to access your cluster.

If you see a message similar to the following, kubectl is not configured correctly
or is not able to connect to a Kubernetes cluster.

```
The connection to the server <server-name:port> was refused - did you specify the right host or port?
```

For example, if you are intending to run a Kubernetes cluster on your laptop (locally),
you will need a tool like [Minikube](https://minikube.sigs.k8s.io/docs/start/) to be
installed first and then re-run the commands stated above.

If `kubectl cluster-info` returns the url response, but you can't access your cluster,
check whether it is configured properly using the following command:

```shell
kubectl cluster-info dump
```

### Troubleshooting the 'No Auth Provider Found' error message {#no-auth-provider-found}

In Kubernetes 1.26, kubectl removed the built-in authentication for the following cloud
providers' managed Kubernetes offerings. These providers have released kubectl plugins
to provide the cloud-specific authentication. For instructions, refer to the following provider documentation:

* Azure AKS: [kubelogin plugin](https://azure.github.io/kubelogin/)
* Google Kubernetes Engine: [gke-gcloud-auth-plugin](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl#install_plugin)

There could also be other causes for the same error message that are unrelated
to that change.
````

### `content/en/docs/tasks/tools/included/kubectl-convert-overview.md`

````markdown
---
title: "kubectl-convert overview"
description: >-
  A kubectl plugin that allows you to convert manifests from one version
  of a Kubernetes API to a different version.
headless: true
_build:
  list: never
  render: never
  publishResources: false
---

A plugin for Kubernetes command-line tool `kubectl`, which allows you to convert manifests between different API 
versions. This can be particularly helpful to migrate manifests to a non-deprecated api version with newer Kubernetes release.
For more info, visit [migrate to non deprecated apis](/docs/reference/using-api/deprecation-guide/#migrate-to-non-deprecated-apis)
````

### `content/en/docs/tasks/tools/included/kubectl-whats-next.md`

````markdown
---
title: "What's next?"
description: "What's next after installing kubectl."
headless: true
_build:
  list: never
  render: never
  publishResources: false
---

* Learn about [kubectl](/docs/concepts/overview/kubectl/) and its role in the Kubernetes ecosystem.
* [Install Minikube](https://minikube.sigs.k8s.io/docs/start/)
* See the [getting started guides](/docs/setup/) for more about creating clusters.
* [Learn how to launch and expose your application.](/docs/tasks/access-application-cluster/service-access-application-cluster/)
* If you need access to a cluster you didn't create, see the
  [Sharing Cluster Access document](/docs/tasks/access-application-cluster/configure-access-multiple-clusters/).
* Read the [kubectl reference docs](/docs/reference/kubectl/kubectl/)
````

### `content/en/docs/tasks/tools/included/optional-kubectl-configs-bash-linux.md`

````markdown
---
title: "bash auto-completion on Linux"
description: "Some optional configuration for bash auto-completion on Linux."
headless: true
_build:
  list: never
  render: never
  publishResources: false
---

### Introduction

The kubectl completion script for Bash can be generated with the command `kubectl completion bash`.
Sourcing the completion script in your shell enables kubectl autocompletion.

However, the completion script depends on
[**bash-completion**](https://github.com/scop/bash-completion),
which means that you have to install this software first
(you can test if you have bash-completion already installed by running `type _init_completion`).

### Install bash-completion

bash-completion is provided by many package managers
(see [here](https://github.com/scop/bash-completion#installation)).
You can install it with `apt-get install bash-completion` or `dnf install bash-completion`, etc.

The above commands create `/usr/share/bash-completion/bash_completion`,
which is the main script of bash-completion. Depending on your package manager,
you have to manually source this file in your `~/.bashrc` file.

To find out, reload your shell and run `type _init_completion`.
If the command succeeds, you're already set, otherwise add the following to your `~/.bashrc` file:

```bash
source /usr/share/bash-completion/bash_completion
```

Reload your shell and verify that bash-completion is correctly installed by typing `type _init_completion`.

### Enable kubectl autocompletion

#### Bash

You now need to ensure that the kubectl completion script gets sourced in all
your shell sessions. There are two ways in which you can do this:

{{< tabs name="kubectl_bash_autocompletion" >}}
{{< tab name="User" codelang="bash" >}}
echo 'source <(kubectl completion bash)' >>~/.bashrc
{{< /tab >}}
{{< tab name="System" codelang="bash" >}}
kubectl completion bash | sudo tee /etc/bash_completion.d/kubectl > /dev/null
sudo chmod a+r /etc/bash_completion.d/kubectl
{{< /tab >}}
{{< /tabs >}}

If you have an alias for kubectl, you can extend shell completion to work with that alias:

```bash
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -o default -F __start_kubectl k' >>~/.bashrc
```

{{< note >}}
bash-completion sources all completion scripts in `/etc/bash_completion.d`.
{{< /note >}}

Both approaches are equivalent. After reloading your shell, kubectl autocompletion should be working.
To enable bash autocompletion in current session of shell, source the ~/.bashrc file:

```bash
source ~/.bashrc
```
````

### `content/en/docs/tasks/tools/included/optional-kubectl-configs-fish.md`

````markdown
---
title: "fish auto-completion"
description: "Optional configuration to enable fish shell auto-completion."
headless: true
_build:
  list: never
  render: never
  publishResources: false
---

{{< note >}}
Autocomplete for Fish requires kubectl 1.23 or later.
{{< /note >}}

The kubectl completion script for Fish can be generated with the command `kubectl completion fish`. Sourcing the completion script in your shell enables kubectl autocompletion.

To do so in all your shell sessions, add the following line to your `~/.config/fish/config.fish` file:

```shell
kubectl completion fish | source
```

After reloading your shell, kubectl autocompletion should be working.
````

### `content/en/docs/tasks/tools/included/optional-kubectl-configs-zsh.md`

````markdown
---
title: "zsh auto-completion"
description: "Some optional configuration for zsh auto-completion."
headless: true
_build:
  list: never
  render: never
  publishResources: false
---

The kubectl completion script for Zsh can be generated with the command `kubectl completion zsh`. Sourcing the completion script in your shell enables kubectl autocompletion.

To do so in all your shell sessions, add the following to your `~/.zshrc` file:

```zsh
source <(kubectl completion zsh)
```

If you have an alias for kubectl, kubectl autocompletion will automatically work with it.

After reloading your shell, kubectl autocompletion should be working.

If you get an error like `2: command not found: compdef`, then add the following to the beginning of your `~/.zshrc` file:

```zsh
autoload -Uz compinit
compinit
```
````

### `data/releases/schedule.yaml`

````yaml
# Use "schedule-builder" to maintain this file:
# https://github.com/kubernetes/release/tree/master/cmd/schedule-builder
# For example by running:
# schedule-builder -uc data/releases/schedule.yaml -e data/releases/eol.yaml
---
schedules:
- endOfLifeDate: "2027-10-28"
  maintenanceModeStartDate: "2027-08-28"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.37.2
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.37.1
    targetDate: "2026-09-15"
  release: "1.37"
  releaseDate: "2026-08-26"
- endOfLifeDate: "2027-06-28"
  maintenanceModeStartDate: "2027-04-28"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.36.6
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.36.5
    targetDate: "2026-09-15"
  - cherryPickDeadline: "2026-08-07"
    release: 1.36.4
    targetDate: "2026-08-11"
  - cherryPickDeadline: "2026-07-10"
    release: 1.36.3
    targetDate: "2026-07-14"
  - cherryPickDeadline: "2026-06-05"
    release: 1.36.2
    targetDate: "2026-06-09"
  - cherryPickDeadline: "2026-05-08"
    release: 1.36.1
    targetDate: "2026-05-13"
  release: "1.36"
  releaseDate: "2026-04-22"
- endOfLifeDate: "2027-02-28"
  maintenanceModeStartDate: "2026-12-28"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.35.10
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.35.9
    targetDate: "2026-09-15"
  - cherryPickDeadline: "2026-08-07"
    release: 1.35.8
    targetDate: "2026-08-11"
  - cherryPickDeadline: "2026-07-10"
    release: 1.35.7
    targetDate: "2026-07-14"
  - cherryPickDeadline: "2026-06-05"
    release: 1.35.6
    targetDate: "2026-06-09"
  - cherryPickDeadline: "2026-05-08"
    release: 1.35.5
    targetDate: "2026-05-12"
  - cherryPickDeadline: "2026-04-10"
    release: 1.35.4
    targetDate: "2026-04-14"
  - cherryPickDeadline: "2026-03-13"
    release: 1.35.3
    targetDate: "2026-03-19"
  - cherryPickDeadline: "2026-02-26"
    note: Out of band patch release to pick up a new version of Go to [address several
      Go CVEs](https://groups.google.com/g/golang-dev/c/ytMTMwK7QBk/m/hpcstrxADwAJ).
      No other changes.
    release: 1.35.2
    targetDate: "2026-02-26"
  - cherryPickDeadline: "2026-02-06"
    note: January 2026 patches consolidated with February
    release: 1.35.1
    targetDate: "2026-02-10"
  release: "1.35"
  releaseDate: "2025-12-17"
- endOfLifeDate: "2026-10-27"
  maintenanceModeStartDate: "2026-08-27"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.34.13
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.34.12
    targetDate: "2026-09-15"
  - cherryPickDeadline: "2026-08-07"
    release: 1.34.11
    targetDate: "2026-08-11"
  - cherryPickDeadline: "2026-07-10"
    release: 1.34.10
    targetDate: "2026-07-14"
  - cherryPickDeadline: "2026-06-05"
    release: 1.34.9
    targetDate: "2026-06-09"
  - cherryPickDeadline: "2026-05-08"
    release: 1.34.8
    targetDate: "2026-05-12"
  - cherryPickDeadline: "2026-04-10"
    release: 1.34.7
    targetDate: "2026-04-14"
  - cherryPickDeadline: "2026-03-13"
    release: 1.34.6
    targetDate: "2026-03-19"
  - cherryPickDeadline: "2026-02-26"
    note: Out of band patch release to pick up a new version of Go to [address several
      Go CVEs](https://groups.google.com/g/golang-dev/c/ytMTMwK7QBk/m/hpcstrxADwAJ).
      No other changes.
    release: 1.34.5
    targetDate: "2026-02-26"
  - cherryPickDeadline: "2026-02-06"
    note: January 2026 patches consolidated with February
    release: 1.34.4
    targetDate: "2026-02-10"
  - cherryPickDeadline: "2025-12-05"
    release: 1.34.3
    targetDate: "2025-12-09"
  - cherryPickDeadline: "2025-11-07"
    note: October 2025 patches consolidated with November
    release: 1.34.2
    targetDate: "2025-11-11"
  - cherryPickDeadline: "2025-09-05"
    release: 1.34.1
    targetDate: "2025-09-09"
  release: "1.34"
  releaseDate: "2025-08-27"
upcoming_releases:
- cherryPickDeadline: "2026-10-09"
  targetDate: "2026-10-13"
- cherryPickDeadline: "2026-11-06"
  targetDate: "2026-11-10"
- cherryPickDeadline: "2026-12-11"
  targetDate: "2026-12-15"
- cherryPickDeadline: "2027-01-08"
  targetDate: "2027-01-12"
````
