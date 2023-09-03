# Helm Kustomized

This is a simple example which uses what-the-helm chart to hihglight how helm can be used along with kustomized to make
changes to resources that do not have template logic.

In this example for my overlay/env2 I have decided to add an additional port mapping to my pod container. This can be
helpful when using third party helm charts which you need to flexibility to change configurations that can't be
configured through a values.yaml

Additionally this supports adding additional values.yaml files within overlay directories that can be used during Helm
template generate phase.

# How to use

## Requirements

First you must have the following binaries installed:

- [kubectl](https://kubectl.docs.kubernetes.io/installation/kubectl/)
- [kustomize](https://kubectl.docs.kubernetes.io/installation/kustomize/)
- [helm](https://helm.sh/docs/intro/install/)

Second you must be connected to a kubernetes cluster 1.18+, which contains a `default` namespace which you context has
access to.

## Examples
The examples below will deploy `env1` and then delete the deployment. The overlay for `env1` includes an additional `values.yaml`.

Using `env2` shows an overlay that overrides the `Deployment` resources named `foo-what-the-helm`

### Deployment Overlay Env1

Deployment for `env1`
```bash
./kustomize apply overlay/env1
```

### Delete an Overlay Deployment

Delete a current deployed environment `evn1`
```bash
./kustomize delete overlay/env1
```
