# Source Snapshot: Containers

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kubernetes Docs)
- **URL:** https://kubernetes.io/docs/concepts/containers/
- **Upstream file:** [`kubernetes/website` → `content/en/docs/concepts/containers/_index.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/concepts/containers/_index.md) at commit `1fc565c` (2026-10-19)
- **Glossary:** words marked with `glossary_tooltip` / `glossary_definition` shortcodes show text from the glossary entries, which are saved in [20261019-glossary.md](20261019-glossary.md).

---

---
title: Containers
weight: 40
description: Technology for packaging an application along with its runtime dependencies.
reviewers:
- erictune
- thockin
content_type: concept
card:
  name: concepts
  weight: 50
---

<!-- overview -->

This page will discuss containers and container images, as well as their use in operations and solution development.

The word _container_ is an overloaded term. Whenever you use the word, check whether your audience uses the same definition.

Each container that you run is repeatable; the standardization from having
dependencies included means that you get the same behavior wherever you
run it.

Containers decouple applications from the underlying host infrastructure.
This makes deployment easier in different cloud or OS environments.

Each {{< glossary_tooltip text="node" term_id="node" >}} in a Kubernetes
cluster runs the containers that form the
[Pods](/docs/concepts/workloads/pods/) assigned to that node.
Containers in a Pod are co-located and co-scheduled to run on the same node.


<!-- body -->

## Container images
A [container image](/docs/concepts/containers/images/) is a ready-to-run
software package containing everything needed to run an application:
the code and any runtime it requires, application and system libraries,
and default values for any essential settings.

Containers are intended to be stateless and
[immutable](https://glossary.cncf.io/immutable-infrastructure/):
you should not change
the code of a container that is already running. If you have a containerized
application and want to make changes, the correct process is to build a new
image that includes the change, then recreate the container to start from the
updated image.

## Container runtimes

{{< glossary_definition term_id="container-runtime" length="all" >}}

Usually, you can allow your cluster to pick the default container runtime
for a Pod. If you need to use more than one container runtime in your cluster,
you can specify the [RuntimeClass](/docs/concepts/containers/runtime-class/)
for a Pod to make sure that Kubernetes runs those containers using a
particular container runtime.

You can also use RuntimeClass to run different Pods with the same container
runtime but with different settings.
