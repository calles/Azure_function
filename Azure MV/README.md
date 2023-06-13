# Azure MV

## CLI de Azure

Listar MV
```
az vm list
```
o
```
az vm list -o table
```
o
```
Get-AzVM
```
Crear un grupo de recursos
```
az group create \
    --name VirtualMachineDemo \
    --location eastus2
```
Crear una dirección IP pública

```
az network public-ip create \
    --resource-group VirtualMachineDemo \
    --name PublicIP2 \
    --version IPv4 \
    --sku Standard \
    --zone 1 2 3
```
Crear una máquina virtual
```
az vm create \
    --name VMWindowsDemo \
    --resource-group VirtualMachineDemo \
    --public-ip-address PublicIP2 \
    --size Standard_B1s \
    --image MicrosoftWindowsServer:WindowsServer:2019-Datacenter:latest \
    --admin-username rodrigo.zaldana
```
Limpieza de recursos
```
az group delete --name VirtualMachineDemo --yes
```
