
## Install ArgoCD

```bash
helm upgrade --install argocd argo/argo-cd \
    --version v7.8.4 \
    --namespace argocd  \
    --values values.yaml \
    --create-namespace
```

<br/>

## ArgoCD admin password

```bash
kubectl --namespace argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```


<br/>

## Uninstall

```bash
helm uninstall argocd
```


```bash
kubectl delete ns argocd --force
```