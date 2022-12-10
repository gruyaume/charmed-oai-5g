# Deploy Charmed OAI 5G

## Requirements

- **Kubernetes**: A cluster with a total of a minimum of 6 vCPUs and 16 GB of RAM.
- **Juju**: A Juju controller with access to the Kubernetes cluster

## Getting Started

Install MicroK8s with the necessary add-ons:

```bash
snap install microk8s --classic
microk8s enable dns
microk8s enable storage
```

## Install the OAI 5G Core 

Install MicroK8s with the necessary add-ons:

```bash
snap install microk8s --classic
microk8s enable dns
microk8s enable storage
microk8s enable community
microk8s enable multus
```

## Deploy the 5G Core

Deploy the charms:

```bash
juju deploy mysql-k8s --channel=edge --trust
juju deploy oai-5g-nrf --channel=edge --trust
juju deploy oai-5g-udr --channel=edge --trust
juju deploy oai-5g-udm --channel=edge --trust
juju deploy oai-5g-ausf --channel=edge --trust
juju deploy oai-5g-amf --channel=edge --trust
juju deploy oai-5g-upf --channel=edge --trust
juju deploy oai-5g-smf --channel=edge --trust
```

Relate the charms:

```bash
juju relate mysql-k8s oai-5g-udr
juju relate oai-5g-nrf oai-5g-udr
juju relate oai-5g-nrf oai-5g-udm
juju relate oai-5g-udr oai-5g-udm
juju relate oai-5g-ausf oai-5g-udm
juju relate oai-5g-ausf oai-5g-nrf
juju relate oai-5g-amf mysql-k8s
juju relate oai-5g-amf oai-5g-nrf
juju relate oai-5g-amf oai-5g-udm
juju relate oai-5g-amf oai-5g-ausf
juju relate oai-5g-upf oai-5g-nrf
juju relate oai-5g-smf oai-5g-nrf
juju relate oai-5g-smf oai-5g-amf
juju relate oai-5g-smf oai-5g-udm
juju relate oai-5g-smf oai-5g-upf
```

## Reference

```mermaid
flowchart TD;
      udr((UDR))-->nrf((NRF))
      udm((UDM))-->nrf((NRF))
      ausf((AUSF))-->nrf((NRF))
      amf((AMF))-->nrf((NRF))
      udr((UDR))-->mysql((MySQL))
      udm((UDM))-->udr((UDR))
      ausf((AUSF))-->udm((UDM))
      amf((AMF))-->ausf((AUSF))
      amf((AMF))-->udm((UDM))
      amf((AMF))-->mysql((MySQL))
      upf((UPF))-->nrf((NRF))
      smf((SMF))-->nrf((NRF))
      smf((SMF))-->amf((AMF))
      smf((SMF))-->udm((UDM))
      smf((SMF))-->upf((UPF))
```

## Charmhub links

- [oai-5g-amf](https://charmhub.io/oai-5g-amf)
- [oai-5g-ausf](https://charmhub.io/oai-5g-ausf)
- [oai-5g-nrf](https://charmhub.io/oai-5g-nrf)
- [oai-5g-udm](https://charmhub.io/oai-5g-udm)
- [oai-5g-udr](https://charmhub.io/oai-5g-udr)
- [oai-5g-upf](https://charmhub.io/oai-5g-upf)
- [oai-5g-smf](https://charmhub.io/oai-5g-smf)
