# ARMTemplatesDeepDive
Examples and documentation on how to write good ARM templates

## Links
- [Azure Quickstart Templates](https://azure.microsoft.com/en-us/resources/templates/)
- [Resource Manager template reference documentation](https://docs.microsoft.com/en-us/azure/templates/)

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
