# Virtual Network

# 'Pegar' o nome do resource group
rgname=$(az group list --query "[0].name" -o tsv)
ou
"$(az group list --query "[0].name" -o tsv)" no parâmetro '-g'

## Guia seguido:
1 - https://learn.microsoft.com/en-us/training/modules/describe-azure-compute-networking-services/1-introduction
2 - https://learn.microsoft.com/en-us/training/modules/configure-virtual-networks/1-introduction
3 - https://learn.microsoft.com/en-us/training/modules/introduction-to-azure-virtual-networks/1-introduction


NOTA

HandsOn falho. Utilizando sandbox 
- https://learn.microsoft.com/en-us/training/modules/host-a-web-app-with-azure-app-service/3-exercise-create-a-web-app-in-the-azure-portal?pivots=python - 
da MS e guia 
- https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator/blob/master/Instructions/Labs/LAB_04-Implement_Virtual_Networking.md - 
não foi totalmente completo. Vários passos não foram possíveis.