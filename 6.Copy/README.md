# 6.Copy
Explains how to use the copy feature to create multiple resources with similar configuration in the same resource group. This can be useful when you want to create multiple App Services in different locations in the same resource group.

In the template.v2.json I introduce 3 pre calculated arrays as variables. This makes the initialization of the variables more complex but when it comes to defining the resources the code becomes much more simple. Decide for yourself what you find more readable and maintainable.

## template.v1.json
Contains the template before array variables was introduced.

## template.v2.json
Contains the template after array variables was introduced.

## Useful links
* [Tutorial: Create multiple resource instances with Resource Manager templates](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-multiple-instances?tabs=azure-cli)
* [Resource, property, or variable iteration in Azure Resource Manager templates](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/create-multiple-instances)

