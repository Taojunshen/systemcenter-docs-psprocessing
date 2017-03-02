---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4B2811EF-8111-4439-A295-D07C66403060
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPackageMapping.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPackageMapping.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPackageMapping.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCPackageMapping

## SYNOPSIS
Creates a package mapping object.

## SYNTAX

### Path
```
New-SCPackageMapping -Path <String> [-PreferPackageResources] [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

### Package
```
New-SCPackageMapping -TemplatePackage <Package> [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCPackageMapping** cmdlet creates a package mapping object.
A package mapping object binds resources to a template.
For information about how to update the bindings in a package mapping object, see **Set-SCPackageMapping**.

## EXAMPLES

### Example 1: Create a package mapping for a template package
```
PS C:\> $TemplatePackage = Get-SCTemplatePackage -Path "C:\TemplateExports\VMTemplate01.xml"
PS C:\> $Mappings = New-SCPackageMapping -TemplatePackage $TemplatePackage
```

The first command gets the template package at the specified path.

The second command creates a package mapping object for the package stored in $TemplatePackage and stores the object in the $Mappings variable.

## PARAMETERS

### -Path
Specifies the destination path for the operation. 

Example formats: 

- Local path: `-Path "F:\"`
- UNC path: `-Path "\\Library\Templates"`
- Volume GUID path: `-Path "\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`
- VMware ESX path: `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`
- Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferPackageResources
Indicates that the resources exported with the package are retained even if similar resources exist at the import destination.

```yaml
Type: SwitchParameter
Parameter Sets: Path
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplatePackage
Specifies an exported template package that contains serialized settings of a service or virtual machine template.

```yaml
Type: Package
Parameter Sets: Package
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PackageMapping
This cmdlet returns a **PackageMapping** object.

## NOTES

## RELATED LINKS

[Get-SCTemplatePackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTemplatePackage.md)

[Set-SCPackageMapping](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPackageMapping.md)

