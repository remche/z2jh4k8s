# Zero to JupyterHub for Kubernetes

> :mortar_board: Turn JupyterHub in a Kubernetes learning center

This chart relies on [Zero to JupyterHub with Kubernetes](https://github.com/jupyterhub/zero-to-jupyterhub-k8s) to deploy a *Kubernetes learning center*.

## Presentation

The chart : 
* uses a `singleuser` [custom image](https://github.com/remche/k8s-notebook) image providing k8s tools like `kubectl` ;
* creates a `Namespace`, `ServiceAccount`, and some RBAC rules per user ;
* spawns the user Jupyter pod with a different service account per user.

## Installation

```bash
$ helm repo add remche https://charts.remche.org
$ helm repo update
$ helm upgrade --install remche/z2jh4k8s -f config.yaml
```

## Configuration

The chart will look `jupyterhub.auth.whitelist.users` values to create the Kubernetes RBAC machinery. You can configure JupyterHub as usual, under 'jupyterhub' value. A dummy configuation is available [here](https://gist.github.com/remche/fe98047c31adbe34d10b41c2bd20d0d0).
