# Bootstrap

## Flux

### Install Flux

```sh
kubectl apply --server-side --kustomize flux
```

### Apply Cluster Configuration

_These cannot be applied with `kubectl` in the regular fashion due to be encrypted with sops_

```sh
kubectl apply -f flux/github-deploy-key.sops.yaml
```

### Kick off Flux applying this repository

```sh
kubectl apply --server-side --kustomize ./clusters/capstone-demo/flux/config
```