# IETF 110 hackathon demo

Docker compose based Attester / Verifier environment based on veraison components.

This demo is build using the following components:
* PSA attestation token package ([veraison/psatoken](https://github.com/veraison/psatoken))
* Challenge-response HTTP API package ([veraison/apiclient](https://github.com/veraison/apiclient))
* Various verifier related packages and HTTP API frontend ([veraison/veraison](https://github.com/veraison/veraison))

## Instructions

* To start the verifier:
```
docker-compose up -d verifier
```

* To run a [challenge-response HTTP API](https://github.com/veraison/veraison/tree/main/docs/api) transaction to request and verify Evidence in form of a [PSA attestation token](https://tools.ietf.org/html/draft-tschofenig-rats-psa-token-07) and get the Attestation Result back:
```
docker-compose run relying-party | cut -c41- | jq .
```
