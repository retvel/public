# Source Snapshot: Learn Kubernetes Basics

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kubernetes Docs)
- **URL:** https://kubernetes.io/docs/tutorials/kubernetes-basics/
- **Upstream file:** [`kubernetes/website` → `content/en/docs/tutorials/kubernetes-basics/_index.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tutorials/kubernetes-basics/_index.md) at commit `1fc565c` (2026-10-19)

---

---
title: Learn Kubernetes Basics
main_menu: true
no_list: true
weight: 20
content_type: concept
card:
  name: tutorials
  weight: 20
  title: Walkthrough the basics
---

## {{% heading "objectives" %}}

This tutorial provides a walkthrough of the basics of the Kubernetes cluster orchestration
system. Each module contains some background information on major Kubernetes features
and concepts, and a tutorial for you to follow along.

Using the tutorials, you can learn to:

* Deploy a containerized application on a cluster.
* Scale the deployment.
* Update the containerized application with a new software version.
* Debug the containerized application.

## What can Kubernetes do for you?

With modern web services, users expect applications to be available 24/7, and developers
expect to deploy new versions of those applications several times a day. Containerization
helps package software to serve these goals, enabling applications to be released and updated
without downtime. Kubernetes helps you make sure those containerized applications run where
and when you want, and helps them find the resources and tools they need to work. Kubernetes
is a production-ready, open source platform designed with Google's accumulated experience in
container orchestration, combined with best-of-breed ideas from the community.

## Kubernetes Basics Modules

<!-- For translators, translate only the values of the ‘alt’ and ‘title’ keys -->
{{< tutorials/modules >}}
  {{< tutorials/module
      path="/docs/tutorials/kubernetes-basics/create-cluster/cluster-intro/"
      image="assets/module_01.svg"
      alt="Module 1"
      title="1. Create a Kubernetes cluster" >}}

  {{< tutorials/module
      path="/docs/tutorials/kubernetes-basics/deploy-app/deploy-intro/"
      image="assets/module_02.svg"
      alt="Module 2"
      title="2. Deploy an app" >}}

  {{< tutorials/module
      path="/docs/tutorials/kubernetes-basics/explore/explore-intro/"
      image="assets/module_03.svg"
      alt="Module 3"
      title="3. Explore your app" >}}

  {{< tutorials/module
      path="/docs/tutorials/kubernetes-basics/expose/expose-intro/"
      image="assets/module_04.svg"
      alt="Module 4"
      title="4. Expose your app publicly" >}}

  {{< tutorials/module
      path="/docs/tutorials/kubernetes-basics/scale/scale-intro/"
      image="assets/module_05.svg"
      alt="Module 5"
      title="5. Scale up your app" >}}

  {{< tutorials/module
      path="/docs/tutorials/kubernetes-basics/update/update-intro/"
      image="assets/module_06.svg"
      alt="Module 6"
      title="6. Update your app" >}}
{{< /tutorials/modules >}}

## {{% heading "whatsnext" %}}

* See the [Learning environment](/docs/setup/learning-environment/) page to learn more about practice clusters and how you can run your own one.
* Tutorial [Using Minikube to Create a Cluster](/docs/tutorials/kubernetes-basics/create-cluster/)
