# Kubernetes sources

Snapshots of the official documentation used by the Kubernetes reference.

| Origin | Repository and commit | Published at | License |
|--------|-----------------------|--------------|---------|
| Kubernetes Docs (describes Kubernetes **v1.37**) | [`kubernetes/website`](https://github.com/kubernetes/website) @ [`1fc565c`](https://github.com/kubernetes/website/commit/1fc565c2f557823a911f073dc577945230f27dd7) (2026-10-19) | https://kubernetes.io/ | CC BY 4.0 — [LICENSE-kubernetes-website](LICENSE-kubernetes-website) |
| Helm Docs (Helm 4 docs set, labelled 4.3.1) | [`helm/helm-www`](https://github.com/helm/helm-www) @ [`dc74ea9`](https://github.com/helm/helm-www/commit/dc74ea9bf052d34f94004b30407cded73ca838f4) (2026-10-17) | https://helm.sh/docs/ | Docs CC BY 4.0 (site footer); repo MIT — [LICENSE-helm-www](LICENSE-helm-www) |
| kind | [`kubernetes-sigs/kind`](https://github.com/kubernetes-sigs/kind) @ [`214d9fd`](https://github.com/kubernetes-sigs/kind/commit/214d9fd1426470dcfa0d8aa1c5dda03bfea835cb) (2026-10-13), `site/` | https://kind.sigs.k8s.io/ | CC BY 4.0 (`site/LICENSE`) — [LICENSE-kind-site](LICENSE-kind-site) |
| minikube | [`kubernetes/minikube`](https://github.com/kubernetes/minikube) @ [`d43dd07`](https://github.com/kubernetes/minikube/commit/d43dd0782a483778ff6296462a6a3d5a7ebfc44f) (2026-10-18), `site/` | https://minikube.sigs.k8s.io/ | Apache-2.0 — [LICENSE-minikube](LICENSE-minikube) |

- Each snapshot reproduces the original file verbatim below its header. Files that the
  published page pulls in at build time (code samples, shared includes, release data) are
  appended under "Included files". Images are copied into [`assets/`](assets/); only their
  paths are changed, and each header lists the copies.
- **Snapshots are immutable.** When a page changes, a new dated snapshot is added.

| Snapshot | Title | Original URL |
|----------|-------|--------------|
| [20261019-overview.md](20261019-overview.md) | Overview | https://kubernetes.io/docs/concepts/overview/ |
| [20261019-components.md](20261019-components.md) | Kubernetes Components | https://kubernetes.io/docs/concepts/overview/components/ |
| [20261019-cluster-architecture.md](20261019-cluster-architecture.md) | Cluster Architecture | https://kubernetes.io/docs/concepts/architecture/ |
| [20261019-nodes.md](20261019-nodes.md) | Nodes | https://kubernetes.io/docs/concepts/architecture/nodes/ |
| [20261019-controllers.md](20261019-controllers.md) | Controllers | https://kubernetes.io/docs/concepts/architecture/controller/ |
| [20261019-self-healing.md](20261019-self-healing.md) | Kubernetes Self-Healing | https://kubernetes.io/docs/concepts/architecture/self-healing/ |
| [20261019-containers.md](20261019-containers.md) | Containers | https://kubernetes.io/docs/concepts/containers/ |
| [20261019-images.md](20261019-images.md) | Images | https://kubernetes.io/docs/concepts/containers/images/ |
| [20261019-cri.md](20261019-cri.md) | Container Runtime Interface (CRI) | https://kubernetes.io/docs/concepts/containers/cri/ |
| [20261019-kubernetes-api.md](20261019-kubernetes-api.md) | The Kubernetes API | https://kubernetes.io/docs/concepts/overview/kubernetes-api/ |
| [20261019-objects.md](20261019-objects.md) | Objects In Kubernetes | https://kubernetes.io/docs/concepts/overview/working-with-objects/ |
| [20261019-names.md](20261019-names.md) | Object Names and IDs | https://kubernetes.io/docs/concepts/overview/working-with-objects/names/ |
| [20261019-namespaces.md](20261019-namespaces.md) | Namespaces | https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/ |
| [20261019-labels.md](20261019-labels.md) | Labels and Selectors | https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/ |
| [20261019-annotations.md](20261019-annotations.md) | Annotations | https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/ |
| [20261019-object-management.md](20261019-object-management.md) | Kubernetes Object Management | https://kubernetes.io/docs/concepts/overview/working-with-objects/object-management/ |
| [20261019-owners-dependents.md](20261019-owners-dependents.md) | Owners and Dependents | https://kubernetes.io/docs/concepts/overview/working-with-objects/owners-dependents/ |
| [20261019-kubectl-concept.md](20261019-kubectl-concept.md) | The kubectl command-line tool | https://kubernetes.io/docs/concepts/overview/kubectl/ |
| [20261019-kubectl-overview.md](20261019-kubectl-overview.md) | Command line tool (kubectl) | https://kubernetes.io/docs/reference/kubectl/ |
| [20261019-kubectl-quick-reference.md](20261019-kubectl-quick-reference.md) | kubectl Quick Reference | https://kubernetes.io/docs/reference/kubectl/quick-reference/ |
| [20261019-kubeconfig.md](20261019-kubeconfig.md) | Organizing Cluster Access Using kubeconfig Files | https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/ |
| [20261019-declarative-config.md](20261019-declarative-config.md) | Declarative Management of Kubernetes Objects Using Configuration Files | https://kubernetes.io/docs/tasks/manage-kubernetes-objects/declarative-config/ |
| [20261019-kustomization.md](20261019-kustomization.md) | Declarative Management of Kubernetes Objects Using Kustomize | https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/ |
| [20261019-workloads.md](20261019-workloads.md) | Workloads | https://kubernetes.io/docs/concepts/workloads/ |
| [20261019-pods.md](20261019-pods.md) | Pods | https://kubernetes.io/docs/concepts/workloads/pods/ |
| [20261019-pod-lifecycle.md](20261019-pod-lifecycle.md) | Pod Lifecycle | https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/ |
| [20261019-init-containers.md](20261019-init-containers.md) | Init Containers | https://kubernetes.io/docs/concepts/workloads/pods/init-containers/ |
| [20261019-sidecar-containers.md](20261019-sidecar-containers.md) | Sidecar Containers | https://kubernetes.io/docs/concepts/workloads/pods/sidecar-containers/ |
| [20261019-probes.md](20261019-probes.md) | Liveness, Readiness, and Startup Probes | https://kubernetes.io/docs/concepts/workloads/pods/probes/ |
| [20261019-pod-qos.md](20261019-pod-qos.md) | Pod Quality of Service Classes | https://kubernetes.io/docs/concepts/workloads/pods/pod-qos/ |
| [20261019-disruptions.md](20261019-disruptions.md) | Disruptions | https://kubernetes.io/docs/concepts/workloads/pods/disruptions/ |
| [20261019-workload-management.md](20261019-workload-management.md) | Workload Management | https://kubernetes.io/docs/concepts/workloads/controllers/ |
| [20261019-deployment.md](20261019-deployment.md) | Deployments | https://kubernetes.io/docs/concepts/workloads/controllers/deployment/ |
| [20261019-replicaset.md](20261019-replicaset.md) | ReplicaSet | https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/ |
| [20261019-statefulset.md](20261019-statefulset.md) | StatefulSets | https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/ |
| [20261019-daemonset.md](20261019-daemonset.md) | DaemonSet | https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/ |
| [20261019-job.md](20261019-job.md) | Jobs | https://kubernetes.io/docs/concepts/workloads/controllers/job/ |
| [20261019-cronjob.md](20261019-cronjob.md) | CronJob | https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/ |
| [20261019-services-networking.md](20261019-services-networking.md) | Services, Load Balancing, and Networking | https://kubernetes.io/docs/concepts/services-networking/ |
| [20261019-service.md](20261019-service.md) | Service | https://kubernetes.io/docs/concepts/services-networking/service/ |
| [20261019-dns.md](20261019-dns.md) | DNS for Services and Pods | https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/ |
| [20261019-endpointslices.md](20261019-endpointslices.md) | EndpointSlices | https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/ |
| [20261019-ingress.md](20261019-ingress.md) | Ingress | https://kubernetes.io/docs/concepts/services-networking/ingress/ |
| [20261019-ingress-controllers.md](20261019-ingress-controllers.md) | Ingress Controllers | https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/ |
| [20261019-gateway-api.md](20261019-gateway-api.md) | Gateway API | https://kubernetes.io/docs/concepts/services-networking/gateway/ |
| [20261019-network-policies.md](20261019-network-policies.md) | Network Policies | https://kubernetes.io/docs/concepts/services-networking/network-policies/ |
| [20261019-cluster-networking.md](20261019-cluster-networking.md) | Cluster Networking | https://kubernetes.io/docs/concepts/cluster-administration/networking/ |
| [20261019-volumes.md](20261019-volumes.md) | Volumes | https://kubernetes.io/docs/concepts/storage/volumes/ |
| [20261019-persistent-volumes.md](20261019-persistent-volumes.md) | Persistent Volumes | https://kubernetes.io/docs/concepts/storage/persistent-volumes/ |
| [20261019-storage-classes.md](20261019-storage-classes.md) | Storage Classes | https://kubernetes.io/docs/concepts/storage/storage-classes/ |
| [20261019-dynamic-provisioning.md](20261019-dynamic-provisioning.md) | Dynamic Volume Provisioning | https://kubernetes.io/docs/concepts/storage/dynamic-provisioning/ |
| [20261019-ephemeral-volumes.md](20261019-ephemeral-volumes.md) | Ephemeral Volumes | https://kubernetes.io/docs/concepts/storage/ephemeral-volumes/ |
| [20261019-configmaps.md](20261019-configmaps.md) | ConfigMaps | https://kubernetes.io/docs/concepts/configuration/configmap/ |
| [20261019-secrets.md](20261019-secrets.md) | Secrets | https://kubernetes.io/docs/concepts/configuration/secret/ |
| [20261019-secrets-good-practices.md](20261019-secrets-good-practices.md) | Good practices for Kubernetes Secrets | https://kubernetes.io/docs/concepts/security/secrets-good-practices/ |
| [20261019-resource-management.md](20261019-resource-management.md) | Resource Management for Pods and Containers | https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/ |
| [20261019-kube-scheduler.md](20261019-kube-scheduler.md) | Kubernetes Scheduler | https://kubernetes.io/docs/concepts/scheduling-eviction/kube-scheduler/ |
| [20261019-assign-pod-node.md](20261019-assign-pod-node.md) | Assigning Pods to Nodes | https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/ |
| [20261019-taints-tolerations.md](20261019-taints-tolerations.md) | Taints and Tolerations | https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/ |
| [20261019-topology-spread.md](20261019-topology-spread.md) | Pod Topology Spread Constraints | https://kubernetes.io/docs/concepts/scheduling-eviction/topology-spread-constraints/ |
| [20261019-node-pressure-eviction.md](20261019-node-pressure-eviction.md) | Node-pressure Eviction | https://kubernetes.io/docs/concepts/scheduling-eviction/node-pressure-eviction/ |
| [20261019-limit-ranges.md](20261019-limit-ranges.md) | Limit Ranges | https://kubernetes.io/docs/concepts/policy/limit-range/ |
| [20261019-resource-quotas.md](20261019-resource-quotas.md) | Resource Quotas | https://kubernetes.io/docs/concepts/policy/resource-quotas/ |
| [20261019-configure-probes.md](20261019-configure-probes.md) | Configure Liveness, Readiness and Startup Probes | https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/ |
| [20261019-autoscaling.md](20261019-autoscaling.md) | Autoscaling Workloads | https://kubernetes.io/docs/concepts/workloads/autoscaling/ |
| [20261019-hpa.md](20261019-hpa.md) | Horizontal Pod Autoscaling | https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/ |
| [20261019-vpa.md](20261019-vpa.md) | Vertical Pod Autoscaling | https://kubernetes.io/docs/concepts/workloads/autoscaling/vertical-pod-autoscale/ |
| [20261019-hpa-walkthrough.md](20261019-hpa-walkthrough.md) | HorizontalPodAutoscaler Walkthrough | https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/ |
| [20261019-node-autoscaling.md](20261019-node-autoscaling.md) | Node Autoscaling | https://kubernetes.io/docs/concepts/cluster-administration/node-autoscaling/ |
| [20261019-resource-metrics-pipeline.md](20261019-resource-metrics-pipeline.md) | Resource metrics pipeline | https://kubernetes.io/docs/tasks/debug/debug-cluster/resource-metrics-pipeline/ |
| [20261019-security.md](20261019-security.md) | Security | https://kubernetes.io/docs/concepts/security/ |
| [20261019-controlling-access.md](20261019-controlling-access.md) | Controlling Access to the Kubernetes API | https://kubernetes.io/docs/concepts/security/controlling-access/ |
| [20261019-rbac.md](20261019-rbac.md) | Using RBAC Authorization | https://kubernetes.io/docs/reference/access-authn-authz/rbac/ |
| [20261019-rbac-good-practices.md](20261019-rbac-good-practices.md) | Role Based Access Control Good Practices | https://kubernetes.io/docs/concepts/security/rbac-good-practices/ |
| [20261019-service-accounts.md](20261019-service-accounts.md) | Service Accounts | https://kubernetes.io/docs/concepts/security/service-accounts/ |
| [20261019-pod-security-standards.md](20261019-pod-security-standards.md) | Pod Security Standards | https://kubernetes.io/docs/concepts/security/pod-security-standards/ |
| [20261019-pod-security-admission.md](20261019-pod-security-admission.md) | Pod Security Admission | https://kubernetes.io/docs/concepts/security/pod-security-admission/ |
| [20261019-enforce-pss-namespace-labels.md](20261019-enforce-pss-namespace-labels.md) | Enforce Pod Security Standards with Namespace Labels | https://kubernetes.io/docs/tasks/configure-pod-container/enforce-standards-namespace-labels/ |
| [20261019-security-context.md](20261019-security-context.md) | Configure a Security Context for a Pod or Container | https://kubernetes.io/docs/tasks/configure-pod-container/security-context/ |
| [20261019-security-checklist.md](20261019-security-checklist.md) | Security Checklist | https://kubernetes.io/docs/concepts/security/security-checklist/ |
| [20261019-private-registry.md](20261019-private-registry.md) | Pull an Image from a Private Registry | https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/ |
| [20261019-getting-started.md](20261019-getting-started.md) | Getting started | https://kubernetes.io/docs/setup/ |
| [20261019-install-tools.md](20261019-install-tools.md) | Install Tools | https://kubernetes.io/docs/tasks/tools/ |
| [20261019-install-kubectl-linux.md](20261019-install-kubectl-linux.md) | Install and Set Up kubectl on Linux | https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/ |
| [20261019-container-runtimes.md](20261019-container-runtimes.md) | Container Runtimes | https://kubernetes.io/docs/setup/production-environment/container-runtimes/ |
| [20261019-install-kubeadm.md](20261019-install-kubeadm.md) | Installing kubeadm | https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/ |
| [20261019-create-cluster-kubeadm.md](20261019-create-cluster-kubeadm.md) | Creating a cluster with kubeadm | https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/ |
| [20261019-kubeadm-upgrade.md](20261019-kubeadm-upgrade.md) | Upgrading kubeadm clusters | https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/ |
| [20261019-migrating-from-dockershim.md](20261019-migrating-from-dockershim.md) | Migrating from dockershim | https://kubernetes.io/docs/tasks/administer-cluster/migrating-from-dockershim/ |
| [20261019-troubleshooting.md](20261019-troubleshooting.md) | Monitoring, Logging, and Debugging | https://kubernetes.io/docs/tasks/debug/ |
| [20261019-debug-pods.md](20261019-debug-pods.md) | Debug Pods | https://kubernetes.io/docs/tasks/debug/debug-application/debug-pods/ |
| [20261019-debug-running-pod.md](20261019-debug-running-pod.md) | Debug Running Pods | https://kubernetes.io/docs/tasks/debug/debug-application/debug-running-pod/ |
| [20261019-debug-service.md](20261019-debug-service.md) | Debug Services | https://kubernetes.io/docs/tasks/debug/debug-application/debug-service/ |
| [20261019-pod-failure-reason.md](20261019-pod-failure-reason.md) | Determine the Reason for Pod Failure | https://kubernetes.io/docs/tasks/debug/debug-application/determine-reason-pod-failure/ |
| [20261019-debug-cluster.md](20261019-debug-cluster.md) | Troubleshooting Clusters | https://kubernetes.io/docs/tasks/debug/debug-cluster/ |
| [20261019-port-forward.md](20261019-port-forward.md) | Use Port Forwarding to Access Applications in a Cluster | https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/ |
| [20261019-kubernetes-basics.md](20261019-kubernetes-basics.md) | Learn Kubernetes Basics | https://kubernetes.io/docs/tutorials/kubernetes-basics/ |
| [20261019-hello-minikube.md](20261019-hello-minikube.md) | Hello Minikube | https://kubernetes.io/docs/tutorials/hello-minikube/ |
| [20261019-releases.md](20261019-releases.md) | Releases | https://kubernetes.io/releases/ |
| [20261019-release-cycle.md](20261019-release-cycle.md) | Kubernetes Release Cycle | https://kubernetes.io/releases/release/ |
| [20261019-patch-releases.md](20261019-patch-releases.md) | Patch Releases | https://kubernetes.io/releases/patch-releases/ |
| [20261019-version-skew-policy.md](20261019-version-skew-policy.md) | Version Skew Policy | https://kubernetes.io/releases/version-skew-policy/ |
| [20261019-helm-introduction.md](20261019-helm-introduction.md) | Introduction to Helm | https://helm.sh/docs/intro/introduction/ |
| [20261019-helm-quickstart.md](20261019-helm-quickstart.md) | Quickstart Guide | https://helm.sh/docs/intro/quickstart/ |
| [20261019-helm-install.md](20261019-helm-install.md) | Installing Helm | https://helm.sh/docs/intro/install/ |
| [20261019-helm-using-helm.md](20261019-helm-using-helm.md) | Using Helm | https://helm.sh/docs/intro/using_helm/ |
| [20261019-helm-cheat-sheet.md](20261019-helm-cheat-sheet.md) | Cheat Sheet | https://helm.sh/docs/intro/CheatSheet/ |
| [20261019-helm-4-overview.md](20261019-helm-4-overview.md) | Helm 4 Overview | https://helm.sh/docs/overview/ |
| [20261019-helm-charts.md](20261019-helm-charts.md) | Charts | https://helm.sh/docs/topics/charts/ |
| [20261019-helm-chart-template-getting-started.md](20261019-helm-chart-template-getting-started.md) | Getting Started | https://helm.sh/docs/chart_template_guide/getting_started/ |
| [20261019-helm-oci-registries.md](20261019-helm-oci-registries.md) | Use OCI-based registries | https://helm.sh/docs/topics/registries/ |
| [20261019-helm-glossary.md](20261019-helm-glossary.md) | Glossary | https://helm.sh/docs/glossary/ |
| [20261019-kind-home.md](20261019-kind-home.md) | kind | https://kind.sigs.k8s.io/ |
| [20261019-kind-quick-start.md](20261019-kind-quick-start.md) | Quick Start | https://kind.sigs.k8s.io/docs/user/quick-start/ |
| [20261019-kind-ingress.md](20261019-kind-ingress.md) | Ingress | https://kind.sigs.k8s.io/docs/user/ingress/ |
| [20261019-kind-loadbalancer.md](20261019-kind-loadbalancer.md) | LoadBalancer | https://kind.sigs.k8s.io/docs/user/loadbalancer/ |
| [20261019-minikube-start.md](20261019-minikube-start.md) | minikube start | https://minikube.sigs.k8s.io/docs/start/ |
| [20261019-minikube-accessing-apps.md](20261019-minikube-accessing-apps.md) | Accessing apps | https://minikube.sigs.k8s.io/docs/handbook/accessing/ |
| [20261019-minikube-pushing-images.md](20261019-minikube-pushing-images.md) | Pushing images | https://minikube.sigs.k8s.io/docs/handbook/pushing/ |
| [20261019-minikube-dashboard.md](20261019-minikube-dashboard.md) | Dashboard | https://minikube.sigs.k8s.io/docs/handbook/dashboard/ |
| [20261019-minikube-basic-controls.md](20261019-minikube-basic-controls.md) | Basic controls | https://minikube.sigs.k8s.io/docs/handbook/controls/ |
| [20261019-check-dockershim-removal.md](20261019-check-dockershim-removal.md) | Check whether dockershim removal affects you | https://kubernetes.io/docs/tasks/administer-cluster/migrating-from-dockershim/check-if-dockershim-removal-affects-you/ |
| [20261019-ingress-nginx-retirement.md](20261019-ingress-nginx-retirement.md) | Ingress NGINX Retirement: What You Need to Know | https://kubernetes.io/blog/2025/11/11/ingress-nginx-retirement/ |
| [20261019-ingress-nginx-statement.md](20261019-ingress-nginx-statement.md) | Ingress NGINX: Statement from the Kubernetes Steering and Security Response Committees | https://kubernetes.io/blog/2026/01/29/ingress-nginx-statement/ |
| [20261019-ingress2gateway-1-0.md](20261019-ingress2gateway-1-0.md) | Announcing Ingress2Gateway 1.0: Your Path to Gateway API | https://kubernetes.io/blog/2026/03/20/ingress2gateway-1-0-release/ |
| [20261019-configure-pod-configmap.md](20261019-configure-pod-configmap.md) | Configure a Pod to Use a ConfigMap | https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/ |
| [20261019-managing-secret-kubectl.md](20261019-managing-secret-kubectl.md) | Managing Secrets using kubectl | https://kubernetes.io/docs/tasks/configmap-secret/managing-secret-using-kubectl/ |
| [20261019-configure-pdb.md](20261019-configure-pdb.md) | Specifying a Disruption Budget for your Application | https://kubernetes.io/docs/tasks/run-application/configure-pdb/ |
| [20261019-authorization.md](20261019-authorization.md) | Authorization | https://kubernetes.io/docs/reference/access-authn-authz/authorization/ |
| [20261019-helm-version-skew.md](20261019-helm-version-skew.md) | Helm Version Support Policy | https://helm.sh/docs/topics/version_skew/ |
| [20261019-glossary.md](20261019-glossary.md) | Glossary | https://kubernetes.io/docs/reference/glossary/?all=true |
| [20261019-docs-site-config.md](20261019-docs-site-config.md) | kubernetes/website site configuration (hugo.toml) | https://github.com/kubernetes/website/blob/main/hugo.toml |
