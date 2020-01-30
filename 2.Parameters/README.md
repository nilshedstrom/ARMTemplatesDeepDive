# 2.Parameters
Explains how you can use parameters to have different resource names and configuration when you deploy the same ARM template to different environments/resource groups.

If the values to your parameters are secret (like passwords, keys and connection strings) you do not want to add them in an ARM template or parameter file. It is a better idea to keep that value secret in a KeyVault and then access that secret when you are deploying your ARM template. This is described in [Pass sensitive values](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/key-vault-parameter?tabs=azure-cli)

## Useful links
* [Tutorial: Add parameters to your Resource Manager template](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-add-parameters?tabs=azure-powershell)
* [Create Resource Manager parameter file](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/parameter-files)

[Deploy to Azure](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnilshedstrom%2FARMTemplatesDeepDive%2Fmaster%2F2.Parameters%2Ftemplate.json)