# 01-kubectl-and-cluster-access

- Share kubeconfig with everyone
- Access the cluster with kubectl and explore around?

```bash
kubectl get pods
```

## Kubectl context

Cluster access (user, kube-api endpoint, certificates)

```bash
# Install
kubectl krew install ctx

kubectx <namespace>
```

> [!TIP]
> Update your terminal prompt to inform you of your current context (so you do not delete production when you wanted to work with test cluster).

## Kubens

Easy namespace switching so you do not have to type the `-n <namespace>`.

```bash
# Install
kubectl krew install ns

kubens <namespace>
```
