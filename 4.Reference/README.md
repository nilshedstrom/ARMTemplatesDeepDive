#4.Reference
Explains how you can configure one resource with the run time value of another resource by using the reference function. This can be useful when you want to configure an App Service to use an Application Insights instance that you create in the same ARM template.

The reference and list* function is actually calling the Azure REST API. You can find more information about it (and try it) on [
Azure REST API Reference](https://docs.microsoft.com/en-us/rest/api/azure/)
## Useful links
* [list*](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-functions-resource#list)
* [reference](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-functions-resource#reference)

[Deploy to Azure](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnilshedstrom%2FARMTemplatesDeepDive%2Fmaster%2F4.Reference%2Ftemplate.json)