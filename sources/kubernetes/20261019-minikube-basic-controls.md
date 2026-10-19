# Source Snapshot: Basic controls

- **Accessed:** 2026-10-19
- **Type:** official documentation (minikube)
- **URL:** https://minikube.sigs.k8s.io/docs/handbook/controls/
- **Upstream file:** [`kubernetes/minikube` → `site/content/en/docs/handbook/controls.md`](https://github.com/kubernetes/minikube/blob/d43dd0782a483778ff6296462a6a3d5a7ebfc44f/site/content/en/docs/handbook/controls.md) at commit `d43dd07` (2026-10-18)

---


---
title: "Basic controls"
weight: 2
description: >
  See minikube in action!
aliases:

- /docs/examples/

---

Start a cluster by running:

```shell
minikube start
```

Access the Kubernetes dashboard running within the minikube cluster:

```shell
minikube dashboard
```

Once started, you can interact with your cluster using `kubectl`, just like any other Kubernetes cluster. For instance, starting a server:

```shell
kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
```

Exposing a service as a NodePort

```shell
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```

minikube makes it easy to open this exposed endpoint in your browser:

```shell
minikube service hello-minikube
```

Upgrade your cluster:

```shell
minikube start --kubernetes-version=latest
```

Start a second local cluster (_note: This will not work if minikube is using the bare-metal/none driver_):

```shell
minikube start -p cluster2
```

Stop your local cluster:

```shell
minikube stop
```

Delete your local cluster:

```shell
minikube delete
```

Delete all local clusters and profiles

```shell
minikube delete --all
```
