# Model

```mermaid
flowchart TD;
      udr((UDR))-->mysql((MySQL))
      udr((UDR))-->nrf((NRF))
      udm((UDM))-->nrf((NRF))
      udm((UDM))-->nrf((NRF))
      ausf((AUSF))-->nrf((NRF))
      ausf((AUSF))-->udm((UDM))
      amf((AMF))-->mysql((MySQL))
      amf((AMF))-->nrf((NRF))
      amf((AMF))-->udm((UDM))
      amf((AMF))-->ausf((AUSF))
      upf((UPF))-->nrf((NRF))
```

## Charmhub links

- [oai-5g-amf](https://charmhub.io/oai-5g-amf)
- [oai-5g-ausf](https://charmhub.io/oai-5g-ausf)
- [oai-5g-nrf](https://charmhub.io/oai-5g-nrf)
- [oai-5g-udm](https://charmhub.io/oai-5g-udm)
- [oai-5g-udr](https://charmhub.io/oai-5g-udr)
- [oai-5g-upf](https://charmhub.io/oai-5g-upf)
