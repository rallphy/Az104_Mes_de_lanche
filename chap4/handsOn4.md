# listar VM's disponíveis (mudar região):
az vm list-skus --location eastus --output table

# Criar VM com disco:
_Adaptar. Este passo não é aplicável se estiver utilizando uma sandbox, pois a sandbox já tem um rg._
- resource group:
az group create --name azuremolchapter4 --location eastus

## - Linux VM:
az vm create \
--resource-group azuremolchapter4 \
--name storagevm \
--image UbuntuLTS \
--size Standard_B1ms \
--admin-username azuremol \
--generate-ssh-keys \
--data-disk-sizes-gb 64

ou

## - Windows VM:
az vm create \
--resource-group azuremolchapter4 \
--name storagevm \
--image Win2019Datacenter \
--size Standard_B1ms \
--admin-username azuremol \
--admin-password P@ssw0rd! \
--data-disk-sizes-gb 64

## - Adicionar um disco a uma VM:
az vm disk attach \
--resource-group azuremolchapter4 \
--vm-name storagevm \
--name datadisk \
--size-gb 64 \
--sku Premium_LRS \
--new
_(apesar de anexado, o disco ainda não pode ser utilizado até que seja inicializado_
_No Linux, o fluxo é __fdisk, mkfs, and then mount__._
_No Windows, seria: __Disk Management > Initialize > Create Volume > Format__.)_

# Testando Table Storage...
## Obs.: 
_antes, editei o arquivo storage_table_demo.py para receber o valor de resource group gerando pelo sandbox_
_funcionou, mas ao tentar o storage_queue_demo.py, não funcionou. Depois nem o storage_table_demo_
_não sei se deveria ter editado..._

No shell:
git clone https://github.com/fouldsy/azure-mol-samples-2nd-ed.git

cd ~/azure-mol-samples-2nd-ed/04

_instalar __'azurerm'__, que gerencia comunicação e recursos Azure, e os Python SDK do CosmosDB e Azure Storage_
pip install --user azurerm azure-cosmosdb-table azure-storage-queue==2.1.0

_--user é necessário pois não temos permissão para instalar pacotes no core system, assim instalamos na nossa sessão_

## rodar a aplicação
python storage_table_demo.py

_foi necessário utilizar __pip install setuptools__ porque estava dando erro de package_

# Testando Queue Storage...
No mesmo shell anterior:
python storage_queue_demo.py

_Só para visualizar o conceito de __queue__._

