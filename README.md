# argocd-apps

This is an EXAMPLE(!) ArgoCD Applications (kind: AppProject) repository.\
The ArgoCD application named "__apps__" (kind: Application) __AUTO sync's__ these files!

This repository uses __plain manifest files__ (no kustomize/helm) !

> NB! __The ability to create Applications in arbitrary Projects is an admin-level capability__!

> NB! Projects __default__ & __argocd__ are only for root apps - do not create new Applications under them!

## Linked repositories

- https://github.com/villisco/argocd-setup - creates the __apps__ application that auto syncs this repository.
- https://github.com/villisco/argocd-projects - sync source for __projects__ (kind: Application)

## Repository structure

```
├── README.md
├── dev                       <!--- kubernetes cluster
│   ├── namespace1            <!--- kubernetes namespace
│   │   └── zipkin.yaml       <!--- ArgoCD "Application" definition (kind: Application)
│   └── namespace2
│       └── zipkin.yaml
├── live
│   └── ...
└── test
    └── ...
```

## Applications

Application (__kind: Application__) provides the info for ArgoCD where to __track & sync__ the user app manifests.\
All Applications (__kind: Application__) must belong to an Project (__kind: AppProject__).

Please define all new user __Projects__ in __argocd-projects__ repository.

## ArgoCD docs

- https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#applications