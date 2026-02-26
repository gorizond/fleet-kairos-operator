# fleet-kairos-operator

Fleet deployment wrapper for `kairos-operator` using Kustomize.

## Why this repo exists

Fleet scans and builds each `GitRepo.spec.paths` entry independently.
Upstream `kairos-operator/config/default` references sibling dirs (`../crd`, `../rbac`, `../manager`),
so we keep a Fleet-friendly local copy of the required `config/*` subtree here.

This avoids:

- giant vendored single-file manifests in `fleet-gitops`
- direct fork maintenance of the full upstream repository
- runtime dependency on `git` inside Fleet kustomize post-render for remote bases

## Structure

- `kustomize/default`
- `kustomize/crd`
- `kustomize/rbac`
- `kustomize/manager`
- `kustomize/kustomization.yaml`

Synced from upstream tag: **v0.0.7**.

## Fleet GitRepo example

- `repo: https://github.com/gorizond/fleet-kairos-operator`
- `paths: [kustomize]`
