# Zero to JupyterHub with for Kubernetes

> :mortar_board: Turn JupyterHub in a Kubernetes learning center

This chart relies on [Zero to JupyterHub with Kubernetes](https://github.com/jupyterhub/zero-to-jupyterhub-k8s) to deploy a *Kubernetes learning center*.

## Presentation

The chart : 
* uses a `singleuser` [custom image](https://github.com/jupyterhub/zero-to-jupyterhub-k8s) image providing k8s tools like `kubectl` ;
* create a `Namespace`, `ServiceAccount`, and some RBAC rules per user ;
* spawn the user Jupyter pod with a different service account per user.

## Installation

```bash
$ helm repo add remche https://charts.remche.org
$ helm repo update
$ helm upgrade --install remche/z2jh4k8s -f config.yaml
```

## Configuration

The chart will look `jupyterhub.auth.whitelist.users` values to create the Kubernetes RBAC machinery. You can configure JupyterHub as usual, under 'jupyterhub' value.