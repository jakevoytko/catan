# Kubernetes namespaces

[API documentation](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/#namespace-v1-core)

## Listing

```bash
kubectl get namespaces
```

## Executing commands within a namespace

```bash
kubectl --namespace=my-namespace get pods # or whatever other command
```

## Default namespaces

- `default`: Namespace if none is specified
- `kube-system`: Namespace for objects created by the Kubernetes system
- `kube-node-lease`: ?
- `kube-public`: ?
