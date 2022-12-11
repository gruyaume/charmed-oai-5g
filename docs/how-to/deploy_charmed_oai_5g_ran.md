# Deploy the 5G RAN

## Requirements

The 5G RAN must be installed on a Kubernetes cluster with the following specifications:

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

## Deploy the 5G RAN

Deploy the charms:

```bash
juju deploy oai-5g-cu --channel=edge --trust
juju deploy oai-5g-du --channel=edge --trust
```

Relate the charms:

```bash
juju relate oai-5g-cu oai-5g-amf
juju relate oai-5g-cu oai-5g-du
```
