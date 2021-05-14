# Helm Kustomized

This is a simple example which uses what-the-helm chart to hihglight how helm can be used along with kustomized to make
changes to resources that do not have template logic.

In this example for my overlay/env2 I have decided to add an additional port mapping to my pod container. This can be
helpful when using third party helm charts which you need to flexibility to change configurations that can't be
configured through a values.yaml

## How to use

### Requirements

First you must have the following binaries installed:

- [kubectl](https://kubectl.docs.kubernetes.io/installation/kubectl/)
- [kustomize](https://kubectl.docs.kubernetes.io/installation/kustomize/)
- [helm](https://helm.sh/docs/intro/install/)

Second you must be connected to a kubernetes cluster 1.18+, which contains a `default` namespace which you context has
access to.

### Deployment Overlay Env1

```bash
./kustomize apply overlay/env1
```

### Deployment Overlay Env2

```bash
./kustomize apply overlay/env2
```

### Delete an Overlay Deployment

```bash
./kustomize delete overlay/env1
or
./kustomize delete overlay/env2
```