# Virtual Network

# 'Pegar' o nome do resource group
rgname=$(az group list --query "[0].name" -o tsv)
ou
"$(az group list --query "[0].name" -o tsv)" no parâmetro '-g'

NOTA

HandsOn falho. Utilizando sandbox 
- https://learn.microsoft.com/en-us/training/modules/host-a-web-app-with-azure-app-service/3-exercise-create-a-web-app-in-the-azure-portal?pivots=python - 
da MS e guia 
- https://github.com/MicrosoftLearning/AZ-104-MicrosoftAzureAdministrator/blob/master/Instructions/Labs/LAB_04-Implement_Virtual_Networking.md - 
não foi totalmente completo. Vários passos não foram possíveis.