---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCCustomPlacementRule.md
schema: 2.0.0
ms.assetid: 7632A678-0188-468D-AD04-5AECB36A09F9
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCCustomPlacementRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCCustomPlacementRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCCustomPlacementRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCCustomPlacementRule

## SYNOPSIS
Deletes a custom placement rule from a placement configuration.

## SYNTAX

```
Remove-SCCustomPlacementRule -PlacementConfiguration <PlacementConfigurationSettings>
 -CustomPropertyName <String> [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCCustomPlacementRule** cmdlet deletes a custom placement rule from a placement configuration for a host group.

## EXAMPLES

### Example 1: Remove a custom placement rule from a placement configuration
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> $PlacementConfig | Remove-SCCustomPlacementRule -CustomPropertyName "Cost Center" -Confirm
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and places the object in the $PlacementConfig variable.

The last command uses the pipeline operator to pass the placement configuration stored in $PlacementConfig to the **Remove-SCCustomPlacementRule** cmdlet.
**Remove-SCCustomPlacementRule** removes the custom placement rule named Cost Center from the placement configuration for HostGroup01 after prompting the user for confirmation.

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

### -CustomPropertyName
Specifies the name for a custom property.

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

### -PlacementConfiguration
Specifies a placement configuration object.

```yaml
Type: PlacementConfigurationSettings
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Add-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCCustomPlacementRule.md)

[Get-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCCustomPlacementRule.md)

[Get-SCPlacementConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCPlacementConfiguration.md)

[Set-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCCustomPlacementRule.md)

