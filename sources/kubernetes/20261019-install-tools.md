# Source Snapshot: Install Tools

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kubernetes Docs)
- **URL:** https://kubernetes.io/docs/tasks/tools/
- **Upstream file:** [`kubernetes/website` → `content/en/docs/tasks/tools/_index.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/tools/_index.md) at commit `1fc565c` (2026-10-19)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0) — Copyright The Kubernetes Authors ("Documentation Distributed under CC BY 4.0"). See [LICENSE-kubernetes-website](LICENSE-kubernetes-website). Reproduced verbatim and unmodified below this line.
- **Glossary:** words marked with `glossary_tooltip` / `glossary_definition` shortcodes show text from the glossary entries, which are saved in [20261019-glossary.md](20261019-glossary.md).

---

---
title: "Install Tools"
description: Set up Kubernetes tools on your computer.
weight: 10
no_list: true
card:
  name: tasks
  weight: 20
  anchors:
  - anchor: "#kubectl"
    title: Install kubectl
---

{{< note >}}
See the [Learning environment](/docs/setup/learning-environment/) page to set up a practice environment.
{{< /note >}}

## kubectl

<!-- overview -->
The Kubernetes command-line tool, [kubectl](/docs/reference/kubectl/kubectl/), allows
you to run commands against Kubernetes clusters.
You can use kubectl to deploy applications, inspect and manage cluster resources,
and view logs. For more information including a complete list of kubectl operations, see the
[`kubectl` reference documentation](/docs/reference/kubectl/).

kubectl is installable on a variety of Linux platforms, macOS and Windows.
Find your preferred operating system below.

- [Install kubectl on Linux](/docs/tasks/tools/install-kubectl-linux)
- [Install kubectl on macOS](/docs/tasks/tools/install-kubectl-macos)
- [Install kubectl on Windows](/docs/tasks/tools/install-kubectl-windows)

## kind

[`kind`](https://kind.sigs.k8s.io/) lets you run Kubernetes on
your local computer. This tool requires that you have either
[Docker](https://www.docker.com/) or [Podman](https://podman.io/) installed.

The kind [Quick Start](https://kind.sigs.k8s.io/docs/user/quick-start/) page
shows you what you need to do to get up and running with kind.

<a class="btn btn-primary" href="https://kind.sigs.k8s.io/docs/user/quick-start/" role="button" aria-label="View kind Quick Start Guide">View kind Quick Start Guide</a>

## minikube

Like `kind`, [`minikube`](https://minikube.sigs.k8s.io/) is a tool that lets you run Kubernetes
locally. `minikube` runs an all-in-one or a multi-node local Kubernetes cluster on your personal
computer (including Windows, macOS and Linux PCs) so that you can try out
Kubernetes, or for daily development work.

You can follow the official
[Get Started!](https://minikube.sigs.k8s.io/docs/start/) guide if your focus is
on getting the tool installed.

<a class="btn btn-primary" href="https://minikube.sigs.k8s.io/docs/start/" role="button" aria-label="View minikube Get Started! Guide">View minikube Get Started! Guide</a>

Once you have `minikube` working, you can use it to
[run a sample application](/docs/tutorials/hello-minikube/).

## kubeadm

You can use the {{< glossary_tooltip term_id="kubeadm" text="kubeadm" >}} tool to create and manage Kubernetes clusters.
It performs the actions necessary to get a minimum viable, secure cluster up and running in a user friendly way.

[Installing kubeadm](/docs/setup/production-environment/tools/kubeadm/install-kubeadm/) shows you how to install kubeadm.
Once installed, you can use it to [create a cluster](/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/).

<a class="btn btn-primary" href="/docs/setup/production-environment/tools/kubeadm/install-kubeadm/" role="button" aria-label="View kubeadm Install Guide">View kubeadm Install Guide</a>
