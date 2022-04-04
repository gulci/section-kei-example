# Photo Stream deployment with Section KEI

[Read more about Section's Kubernetes Edge Interface (KEI)](https://www.section.io/docs/get-started/create-environment/)

[Photo Stream image fork that syncs with a Google Cloud Storage bucket](https://github.com/gulci/photo-stream)

## Pre-requisites
- Have an account with Section.io
- Install Kubernetes
- Have a Google Cloud Storage bucket configured with a service account. Create `gsa-creds.yaml` in the `secrets` directory and create a secret with your `gsa.json` data. Refer to `gsa-creds.examples.yaml` for an example.

## Photo Stream-specific setup

The following Section.io documentation are very helpful and mostly applicable when deploying this application to their KEI service:
- https://www.section.io/docs/get-started/create-environment/
- https://www.section.io/docs/get-started/deploy-container/
- https://www.section.io/docs/get-started/setup-ingress/

For this specific application, the following `kubectl` commands cover the deployment of the photo-stream container:
- `kubectl apply -f configs/photo-stream-config.yaml`
- `kubectl apply -f secrets/gsa-creds.haml`
- `kubectl apply -f photo-stream.yaml`
