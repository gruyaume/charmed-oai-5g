# Model

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
