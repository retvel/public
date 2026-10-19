# Source Snapshot: Determine the Reason for Pod Failure

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kubernetes Docs)
- **URL:** https://kubernetes.io/docs/tasks/debug/debug-application/determine-reason-pod-failure/
- **Upstream file:** [`kubernetes/website` → `content/en/docs/tasks/debug/debug-application/determine-reason-pod-failure.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/docs/tasks/debug/debug-application/determine-reason-pod-failure.md) at commit `1fc565c` (2026-10-19)
- **Included files:** the published page pulls these files in when the site is built (code samples, shared includes, partials). They are appended verbatim after the page, under "Included files", from the same commit: [`content/en/examples/debug/termination.yaml`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/examples/debug/termination.yaml); [`content/en/includes/task-tutorial-prereqs.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/includes/task-tutorial-prereqs.md)
- **Version values:** the `skew` and `param` shortcodes render from [`hugo.toml`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/hugo.toml) (`latest = "v1.37"`, `version = "v1.37"`). So `{{< skew currentVersion >}}` and `{{< skew latestVersion >}}` = `1.37`, `{{< param "version" >}}` = `v1.37`, `currentVersionAddMinor -1` = `1.36` (`-2` = `1.35`, `-3` = `1.34`, `+1` = `1.38`), `prevMinorVersion` = `1.36`, `nextMinorVersion` = `1.38`, `oldestMinorVersion` = `1.35`.

---

---
title: Determine the Reason for Pod Failure
content_type: task
weight: 30
---

<!-- overview -->

This page shows how to write and read a Container termination message.

Termination messages provide a way for containers to write
information about fatal events to a location where it can
be easily retrieved and surfaced by tools like dashboards
and monitoring software. In most cases, information that you
put in a termination message should also be written to
the general
[Kubernetes logs](/docs/concepts/cluster-administration/logging/).

## {{% heading "prerequisites" %}}

{{< include "task-tutorial-prereqs.md" >}}

<!-- steps -->

## Writing and reading a termination message

In this exercise, you create a Pod that runs one container.
The manifest for that Pod specifies a command that runs when the container starts:

{{% code_sample file="debug/termination.yaml" %}}

1. Create a Pod based on the YAML configuration file:

    ```shell
    kubectl apply -f https://k8s.io/examples/debug/termination.yaml
    ```
    
    In the YAML file, in the `command` and `args` fields, you can see that the
    container sleeps for 10 seconds and then writes "Sleep expired" to
    the `/dev/termination-log` file. After the container writes
    the "Sleep expired" message, it terminates.

1. Display information about the Pod:

    ```shell
    kubectl get pod termination-demo
    ```

    Repeat the preceding command until the Pod is no longer running.

1. Display detailed information about the Pod:

    ```shell
    kubectl get pod termination-demo --output=yaml
    ```

    The output includes the "Sleep expired" message:

    ```yaml
    apiVersion: v1
    kind: Pod
    ...
        lastState:
          terminated:
            containerID: ...
            exitCode: 0
            finishedAt: ...
            message: |
              Sleep expired
            ...
    ```

1. Use a Go template to filter the output so that it includes only the termination message:

    ```shell
    kubectl get pod termination-demo -o go-template="{{range .status.containerStatuses}}{{.lastState.terminated.message}}{{end}}"
    ```

If you are running a multi-container Pod, you can use a Go template to include the container's name.
By doing so, you can discover which of the containers is failing:

```shell
kubectl get pod multi-container-pod -o go-template='{{range .status.containerStatuses}}{{printf "%s:\n%s\n\n" .name .lastState.terminated.message}}{{end}}'
```

## Customizing the termination message

Kubernetes retrieves termination messages from the termination message file
specified in the `terminationMessagePath` field of a Container, which has a default
value of `/dev/termination-log`. By customizing this field, you can tell Kubernetes
to use a different file. Kubernetes use the contents from the specified file to
populate the Container's status message on both success and failure.

The termination message is intended to be brief final status, such as an assertion failure message.
The kubelet truncates messages that are longer than 4096 bytes.

The total message length across all containers is limited to 12KiB, divided equally among each container.
For example, if there are 12 containers (`initContainers` or `containers`), each has 1024 bytes of available termination message space.

The default termination message path is `/dev/termination-log`.
You cannot set the termination message path after a Pod is launched.

In the following example, the container writes termination messages to
`/tmp/my-log` for Kubernetes to retrieve:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: msg-path-demo
spec:
  containers:
  - name: msg-path-demo-container
    image: debian
    terminationMessagePath: "/tmp/my-log"
```

Moreover, users can set the `terminationMessagePolicy` field of a Container for
further customization. This field defaults to "`File`" which means the termination
messages are retrieved only from the termination message file. By setting the
`terminationMessagePolicy` to "`FallbackToLogsOnError`", you can tell Kubernetes
to use the last chunk of container log output if the termination message file
is empty and the container exited with an error. The log output is limited to
2048 bytes or 80 lines, whichever is smaller.

## {{% heading "whatsnext" %}}

* See the `terminationMessagePath` field in
  [Container](/docs/reference/generated/kubernetes-api/{{< param "version" >}}/#container-v1-core).
* See [ImagePullBackOff](/docs/concepts/containers/images/#imagepullbackoff) in [Images](/docs/concepts/containers/images/).
* Learn about [retrieving logs](/docs/concepts/cluster-administration/logging/).
* Learn about [Go templates](https://pkg.go.dev/text/template).
* Learn about [Pod status](/docs/tasks/debug/debug-application/debug-init-containers/#understanding-pod-status) and [Pod phase](/docs/concepts/workloads/pods/pod-lifecycle/#pod-phase).
* Learn about [container states](/docs/concepts/workloads/pods/pod-lifecycle/#container-states).

---

## Included files

### `content/en/examples/debug/termination.yaml`

````yaml
apiVersion: v1
kind: Pod
metadata:
  name: termination-demo
spec:
  containers:
  - name: termination-demo-container
    image: debian
    command: ["/bin/sh"]
    args: ["-c", "sleep 10 && echo Sleep expired > /dev/termination-log"]
````

### `content/en/includes/task-tutorial-prereqs.md`

````markdown
You need to have a Kubernetes cluster, and the kubectl command-line tool must
be configured to communicate with your cluster. It is recommended to run this tutorial on a cluster with at least two nodes that are not acting as control plane hosts. If you do not already have a
cluster, you can create one by using
[minikube](https://minikube.sigs.k8s.io/docs/tutorials/multi_node/)
or you can use one of these Kubernetes playgrounds:

* [iximiuz Labs](https://labs.iximiuz.com/playgrounds?category=kubernetes&filter=all)
* [Killercoda](https://killercoda.com/playgrounds/scenario/kubernetes)
* [KodeKloud](https://kodekloud.com/public-playgrounds)
````
