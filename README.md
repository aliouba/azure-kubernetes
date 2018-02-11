# azure-kubernetes

az group create --name myResourceGroup --location eastus


az acr create --resource-group myResourceGroup --name mydockerregistry123 --sku Basic


az ad sp create-for-rbac --scopes /subscriptions/<>/resourceGroups/myResourceGroup/providers/Microsoft.ContainerRegistry/registries/ --role Owner --password 


docker login mydockerregistry123.azurecr.io -u <> -p <>

or 

az acr login --name mydockerregistry123

docker tag azure-vote-front:latest mydockerregistry123.azurecr.io/azure-vote-front:v1

az acr repository list --name mydockerregistry123 --output table

az acr repository show-tags --name mydockerregistry123 --repository azure-vote-front --output table

az provider register -n Microsoft.ContainerService

az provider register -n Microsoft.Compute

az provider register -n Microsoft.Storage

az provider register -n Microsoft.Network

az aks create --resource-group myResourceGroup --name myAKSCluster --node-count 1 --generate-ssh-keys

az aks install-cli

az aks get-credentials --resource-group=myResourceGroup --name=myAKSCluster

kubectl create -f azure-vote-all-in-one-redis.yaml 

kubectl create -f oms-daemonset.yam



