# Azure MV

## CLI de Azure

Listar MV

az vm list

Crear un grupo de recursos

az group create \
    --name [nombredelgrupo] \
    --location eastus2

Crear una dirección IP pública

az network public-ip create \
    --resource-group [nombredelgrupo] \
    --name [nombredelaIP] \
    --version IPv4 \
    --sku Standard \
    --zone 1 2 3

Crear una máquina virtual

az vm create \
    --name [nombredelamaquina] \
    --resource-group [nombredelgrupo] \
    --public-ip-address [nombredelaIP] \
    --size [DS1_v2] \
    --image [MicrosoftWindowsServer:WindowsServer:2019-Datacenter:latest] \
    --admin-username [rodrigo.zaldana]


