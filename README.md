# Quick start with Porter and CNAB


## Pre-requisites

1. Install porter from porter.sh
2. [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
3. Insta 

## Publish artifacts to ACR

Ensure you have have updated `porter.yaml` to point to your registry 

```yaml
invocationImage: myregistry.azurecr.io/porter-hello:latest
tag: myregistry.azurecr.io/porter-hello-bundle:latest
```

### Login to the Registry and publish you bundle

```sh
cd bundle
porter build
az acr login -n myregistry
porter publish
```

## Executing CNAB bundles

ACR Tasks supports executing CNAB bundles. You can use porter as a driver to kick off your bundle execution with just [Azure Cloud Shell](shell.azure.com)

> Currently using a porter bootstrap image until the official image is published.

```sh
az acr run -r myregistry --cmd 'sajay/porter install demo --tag myregistry.azurecr.io/porter-hello-bundle:latest' /dev/null
```