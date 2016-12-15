---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceTemplate.md
schema: 2.0.0
ms.assetid: 4757D36C-5E0A-49CF-8B95-D397C2C910B0
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServiceTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServiceTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServiceTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCServiceTemplate

## SYNOPSIS
Deletes a service template from the VMM library.

## SYNTAX

```
Remove-SCServiceTemplate [-ServiceTemplate] <ServiceTemplate> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCServiceTemplate** cmdlet deletes one or more service templates from the VMM library.

## EXAMPLES

### Example 1: Remove a specific service template from the library
```
PS C:\>$SvcTemplate = Get-SCServiceTemplate -VMMServer "VMMServer01.Contoso.com" -Name "ServiceTemplate01"
PS C:\> Remove-SCServiceTemplate -ServiceTemplate $SvcTemplate -Confirm
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $SvcTemplate variable.

The second command removes the service template object in $SvcTemplate from the VMM database and deletes the corresponding service template object and all other associated objects in the library.
A confirmation prompt is displayed before the the service template object is removed.

### Example 2: Remove all service templates from the library
```
PS C:\>$SvcTemplates = Get-SCServiceTemplate -VMMServer "VMMServer01.Contoso.com"
PS C:\> $SvcTemplates | Remove-SCServiceTemplate -Confirm
```

The first command gets all service template objects on VMMServer01 and stores the objects in the $SvcTemplates variable.

The second command removes all service template objects from the VMM database and deletes the corresponding service template object and all other associated objects in the library.
A confirmation prompt is displayed before the service template objects are removed.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[New-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCServiceTemplate.md)

[Read-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCServiceTemplate.md)

[Resolve-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resolve-SCServiceTemplate.md)

[Set-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCServiceTemplate.md)

[Test-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCServiceTemplate.md)

