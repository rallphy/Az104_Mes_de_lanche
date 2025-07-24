# Virtual Network

# 'Pegar' o nome do resource group
rgname=$(az group list --query "[0].name" -o tsv)
ou
"$(az group list --query "[0].name" -o tsv)" no parâmetro '-g'

