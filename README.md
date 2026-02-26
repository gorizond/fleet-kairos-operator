# fleet-kairos-operator

Fleet wrapper repository for deploying [`kairos-io/kairos-operator`](https://github.com/kairos-io/kairos-operator)
using Kustomize in Rancher Fleet.

## Layout

- `kustomize/kustomization.yaml` — remote Kustomize source pinned to upstream tag `v0.0.7`.

## Fleet usage

Use GitRepo with:

- `repo: https://github.com/gorizond/fleet-kairos-operator`
- `paths: [kustomize]`

This keeps `fleet-gitops` small and avoids vendoring large generated manifests.
