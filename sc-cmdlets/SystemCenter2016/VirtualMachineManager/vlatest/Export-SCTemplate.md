---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 084C62FD-2DAF-4EEC-9229-13EFD994CDC6
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Export-SCTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Export-SCTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Export-SCTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Export-SCTemplate

## SYNOPSIS
Exports a template from the VMM library to the specified path.

## SYNTAX

### VMTemplate
```
Export-SCTemplate [-VMTemplate] <Template> -Path <String> [-SettingsIncludePrivate] [-Overwrite]
 [-Password <String>] [-IncludeLibraryResources <ItemBase[]>] [-AllowUnencryptedTransfer]
 [-IncludeAllLibraryResources] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ServiceTemplate
```
Export-SCTemplate [-ServiceTemplate] <ServiceTemplate> -Path <String> [-SettingsIncludePrivate] [-Overwrite]
 [-Password <String>] [-IncludeLibraryResources <ItemBase[]>] [-AllowUnencryptedTransfer]
 [-IncludeAllLibraryResources] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-SCTemplate** cmdlet exports a template from the Virtual Machine Manager (VMM) library to the specified path.
You can also export the library objects on which the template is dependent.

## EXAMPLES

### Example 1: Export a service template with all of its settings
```
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> Export-SCTemplate -ServiceTemplate $ServiceTemplate -Path "C:\TemplateExports" -SettingsIncludePrivate -Overwrite
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command exports the service template stored in $ServiceTemplate, including all settings, and overwrites existing template export packages that have the same name.

### Example 2: Export multiple service templates with all of their settings
```
PS C:\> Get-SCServiceTemplate | Export-SCTemplate -Path "C:\TemplateExports" -SettingsIncludePrivate -Overwrite
```

This command uses the **Get-SCServiceTemplate** cmdlet to get all service template objects.
Then, it uses the pipeline operator to send the objects to the **Export-SCTemplate** cmdlet, which exports the templates, overwriting any existing files.

### Example 3: Export a service template including its dependent library resources
```
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> Export-SCTemplate -ServiceTemplate $ServiceTemplate -Path "C:\TemplateExports" -IncludeAllLibraryResources
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command exports ServiceTemplate01 and all of its dependent resources from the VMM library to C:\TempalteExports.

## PARAMETERS

### -AllowUnencryptedTransfer
Indicates that network file transfers do not require encryption.
If you allow unencrypted network file transfers, it can improve performance if neither the source host nor the destination host requires encryption.

Use this parameter to: 

- Allow unencrypted file transfers into, or out of, the library. 
- Allow unencrypted file transfers into, out of, or within a host group.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeAllLibraryResources
Indicates that all of the dependencies for a template are exported from the VMM library with the template.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeLibraryResources
Specifies dependent library resources that are to be exported with a template.

```yaml
Type: ItemBase[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Overwrite
Indicates that an import or export operation overwrites an existing file with the same name.
Or, that an import operation overwrites an existing virtual machine template or service template object with the same name.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a secure string that contains a password.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: ServiceTemplate
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SettingsIncludePrivate
Indicates that sensitive template settings are included in an import or export operation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: VMTemplate
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SCTemplate
This cmdlet returns an **SCTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Import-SCTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Import-SCTemplate.md)

