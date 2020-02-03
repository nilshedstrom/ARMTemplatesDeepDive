# ARMTemplatesDeepDive
Examples and documentation on how to write good ARM templates. 
## Introduction
Azure Resource Manager Templates (ARM Templates) are a way to define a set of resources in Azure. When you deploy the ARM template the Azure Resource Manager will create the resources in your ARM template.
If you are new to ARM templates and want to learn more the [tutorials](http://aka.ms/justlearnarm) at [Azure Resource Manager template documentation](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/) is a really good place to start.

## Chapters
This repo is a source for all the examples used in the presentation [Deep dive into writing good ARM templates](https://sessionize.com/s/nils-hedstrom/deep_dive_into_writing_good_arm_tem/24411) and each topic is covered in one chapter (directory in GitHub).
### [1.First](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/1.First)
Explains the basic structure of ARM templates with an example of a Storage Account

### [2.Parameters](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/2.Parameters)
Explains how you can use parameters to have different resource names and configuration when you deploy the same ARM template to different environments/resource groups.

### [3.Variables](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/3.Variables)
Explains how you can reduce code duplication and increase readability and maintainability of your ARM templates by introducing variables with good names.

### [4.Reference](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/4.Reference)
Explains how you can configure one resource with the run time value of another resource by using the reference function. This can be useful when you want to configure an App Service to use an Application Insights instance that you create in the same ARM template.

### [5.Condition](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/5.Condition)
Explains how you can sometimes skip the creation of a resource by using the condition feature and change the value by using the if-function. This can be useful if you want several App Services to use the same App Service Plan.

### [6.Copy](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/6.Copy)
Explains how to use the copy feature to create multiple resources with similar configuration in the same resource group. This can be useful when you want to create multiple App Services in different locations in the same resource group.

### [7.DeploymentScript](https://github.com/nilshedstrom/ARMTemplatesDeepDive/tree/master/7.DeploymentScript)
Explains how to use Deployment Scripts to run custom Powershell scripts when you deploy your ARM templates. This can be useful when you want to create resources that are not possible with normal ARM Templates, such as: 
* Storage Tables
* Azure Active Directory Applications
* Chatbots
* Certificates in KeyVault

## Other topics
There are some topics that I feel is important but did not have the time to cover in my presentation
### User-defined functions
The concept of user-defined functions is the same as in most programming languages and you can reduce them to reduce code duplication and increase readability and maintainability. 
Check this [article](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-user-defined-functions) to learn how to create your own user-defined functions. Pay attention to the limitations because you cannot use them in all scenarios.
### Unit tests
As with normal code you might want to run Unit tests on your ARM templates. There are two types of Unit tests:
* Static file analysis that can help you verify that your templates are following a standard. [Static Analysis for ARM Templates](https://aka.ms/arm-ttk)
* Unit tests that "deploys" the template, looks at the "deployed" resources and checks if they are what you expected. 
[Test ARM Templates using Pester & Azure DevOps](https://medium.com/charot/test-arm-templates-using-pester-azure-devops-837b5006c30c)
[Testing ARM Templates with Pester](https://platform.deloitte.com.au/articles/testing-arm-templates-with-pester)
### Linked templates
If your ARM templates gets too big or you need to modularize your templates you might might consider splitting your template into several smaller ones and have one call the other ones. The process is described in  [Tutorial: Create linked Azure Resource Manager templates](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-linked-templates) and [Using linked and nested templates when deploying Azure resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/linked-templates). Keep in mind that your deployments will get more complicated.

## Sources of documentation for ARM templates
- [Export template](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/export-template-portal)
  Contains information on how to get ARM templates from the Azure Portal for new an existing resources.
- [Azure Quickstart Templates](https://azure.microsoft.com/en-us/resources/templates/)
  839 templates that show you deploy popular resources to Azure using ARM templates.
- [Resource Manager template reference documentation](https://docs.microsoft.com/en-us/azure/templates/)
  Contains the documentation for what you can write in your ARM templates. 
  Search for the name of the resource ("storage accounts") or resource type ("Microsoft.Storage/storageAccounts") to find the [documentation](https://docs.microsoft.com/en-us/azure/templates/microsoft.storage/2019-04-01/storageaccounts).

## Recommended plugins for Visual Studio Code
* [Azure Resource Manager (ARM) Tools](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools)
A must have when you are working with ARM Templates in Visual Studio code. Gives you code completion, validation, colorization and much more.
* [ARM Template Viewer](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools)
Gives you a graphical preview of your ARM template.
* [ARM Params Generator](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools)
Gives you the ability to extract selected value to parameters or variables and the ability to create a parameters file from for the current ARM template.
* [Highlight](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-highlight)
In the different templates in this repository I have added comments with `<NewStuff>` where the new stuff (since the last chapter) begins and `</NewStuff>` where the new stuff ends.
If you want to make the new stuff **bold** and almost remove the `<NewStuff>` tags you should install this plugin with the following settings in settings.json

```json
"highlight.regexes": {
    "(/\\* <NewStuff> \\*/)(.*?)(/\\* </NewStuff> \\*/)": {
        "regexFlags": "gms",
        "filterLanguageRegex": "arm-template|json|jsonc",
        "decorations": [
            { "opacity": "0.05" },
            {
                "overviewRulerColor": "#00ff00",
                "fontWeight": "bolder"
            },
            { "opacity": "0.05" },
        ]
        }
},
"highlight.maxMatches": 500,
```
