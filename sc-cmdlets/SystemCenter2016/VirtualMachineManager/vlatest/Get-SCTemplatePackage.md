---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4AC0E651-0154-4B18-8549-A0F14CECF907
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTemplatePackage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTemplatePackage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTemplatePackage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCTemplatePackage

## SYNOPSIS
Gets an exported service template or virtual machine template package at a specified location.

## SYNTAX

```
Get-SCTemplatePackage -Path <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCTemplatePackage** cmdlet gets an exported service template or virtual machine template package at a specified location.
After you get the template package object, you can read the properties of the object, or you can input the object into the **Import-SCTemplate** cmdlet.

For more information about importing a template package, type `Get-Help Import-SCTemplate -Detailed`.

## EXAMPLES

### Example 1: Get a template package from a specified location
```
PS C:\> $TemplatePackage = Get-SCTemplatePackage -Path "C:\TemplateExports"
```

This command gets the template package object in C:\TemplateExports and stores the object in the $TemplatePackage variable.

## PARAMETERS

### -Path
Specifies the destination path for the operation. 

Example formats: 

- Local path: `-Path "F:\"`
- UNC path: `-Path "\\\\Library\Templates"`
- Volume GUID path: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`
- VMware ESX path: `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`
- Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

This parameter accepts wildcard characters for a UNC path. 

Example format: 

UNC path:         `-Path "\\\\VMHostServer\MyVMs\*VM*"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### TemplatePackage[]
This cmdlet returns an array of **TemplatePackage** objects.

## NOTES

## RELATED LINKS

