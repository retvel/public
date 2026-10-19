# Source Snapshot: LoadBalancer

- **Accessed:** 2026-10-19
- **Type:** official documentation (kind)
- **URL:** https://kind.sigs.k8s.io/docs/user/loadbalancer/
- **Upstream file:** [`kubernetes-sigs/kind` → `site/content/docs/user/loadbalancer.md`](https://github.com/kubernetes-sigs/kind/blob/214d9fd1426470dcfa0d8aa1c5dda03bfea835cb/site/content/docs/user/loadbalancer.md) at commit `214d9fd` (2026-10-13)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0) — the license of the kind website content (`site/LICENSE`), Copyright The Kubernetes Authors. See [LICENSE-kind-site](LICENSE-kind-site). Reproduced verbatim and unmodified below this line.
- **Included files:** the published page pulls these files in when the site is built (code samples, shared includes, partials). They are appended verbatim after the page, under "Included files", from the same commit: [`site/static/examples/loadbalancer/usage.yaml`](https://github.com/kubernetes-sigs/kind/blob/214d9fd1426470dcfa0d8aa1c5dda03bfea835cb/site/static/examples/loadbalancer/usage.yaml)

---

---
title: "LoadBalancer"
menu:
  main:
    parent: "user"
    identifier: "user-loadbalancer"
    weight: 3
description: |-
    This guide covers how to get service of type LoadBalancer working in a kind cluster using [Cloud Provider KIND].

    This guide complements Cloud Provider KIND [installation docs].

    [Cloud Provider KIND]: https://github.com/kubernetes-sigs/cloud-provider-kind
    [installation docs]: https://github.com/kubernetes-sigs/cloud-provider-kind?tab=readme-ov-file#install

    [Ingress Guide]: /docs/user/ingress
    [Configuration Guide]: /docs/user/configuration#extra-port-mappings

---

## Installing Cloud Provider KIND

Cloud Provider KIND can be installed using golang

{{< codeFromInline lang="bash" >}}
go install sigs.k8s.io/cloud-provider-kind@latest
{{< /codeFromInline >}}

or downloading one of the [released binaries](https://github.com/kubernetes-sigs/cloud-provider-kind/releases).

Cloud Provider KIND runs as a standalone binary in your host and connects to your KIND cluster and provisions new Load Balancer containers for your Services. It requires privileges to open ports on the system and to connect to the container runtime.

## Using LoadBalancer

The following example creates a loadbalancer service that routes to two http-echo pods, one that outputs foo and the other outputs bar.

```yaml
{{% readFile "static/examples/loadbalancer/usage.yaml" %}}
```

Apply the contents

{{< codeFromInline lang="yaml" >}}
kubectl apply -f https://kind.sigs.k8s.io/examples/loadbalancer/usage.yaml
{{< /codeFromInline>}}

Now verify that the loadbalancer works by sending traffic to it's external IP and port.

{{< codeFromInline lang="bash" >}}
LB_IP=$(kubectl get svc/foo-service -o=jsonpath='{.status.loadBalancer.ingress[0].ip}')
{{< /codeFromInline >}}

```bash
# should output foo and bar on separate lines 
for _ in {1..10}; do
  curl ${LB_IP}:5678
done
```

---

## Included files

### `site/static/examples/loadbalancer/usage.yaml`

````yaml
kind: Pod
apiVersion: v1
metadata:
  name: foo-app
  labels:
    app: http-echo
spec:
  containers:
  - command:
    - /agnhost
    - serve-hostname
    - --http=true
    - --port=8080
    image: registry.k8s.io/e2e-test-images/agnhost:2.39
    name: foo-app
---
kind: Pod
apiVersion: v1
metadata:
  name: bar-app
  labels:
    app: http-echo
spec:
  containers:
  - command:
    - /agnhost
    - serve-hostname
    - --http=true
    - --port=8080
    image: registry.k8s.io/e2e-test-images/agnhost:2.39
    name: bar-app
---
kind: Service
apiVersion: v1
metadata:
  name: foo-service
spec:
  type: LoadBalancer
  selector:
    app: http-echo
  ports:
  - port: 5678
    targetPort: 8080
````
