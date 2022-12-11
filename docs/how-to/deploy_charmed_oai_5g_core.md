# Deploy the 5G Core

## Requirements

The 5G Core must be installed on a Kubernetes cluster with the following specifications:

- **:material-kubernetes: Kubernetes**: A cluster with a total of a minimum of 6 vCPUs and 16 GB of RAM.
- **:material-ubuntu: Juju**: A Juju controller with access to the Kubernetes cluster

## Getting Started

Install MicroK8s with the necessary add-ons:

```bash
snap install microk8s --classic
microk8s enable dns
microk8s enable storage
microk8s enable metallb:10.0.1.1-10.0.1.10
```

## Deploy the 5G Core

```bash
juju deploy oai-5g-core --channel=edge --trust
```
