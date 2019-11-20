# Quick start with Porter and CNAB. 


## Pre-requisites

1. Install porter from porter.sh
2. [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
3. Insta 

Update 

```sh
cd bundle
porter build
az acr login -n myregistry
porter publish
```
