---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCCustomPlacementRule.md
schema: 2.0.0
ms.assetid: 577DF718-F80E-4AA5-8FB4-2E3730D46CE1
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCustomPlacementRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCustomPlacementRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCustomPlacementRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCustomPlacementRule

## SYNOPSIS
Gets the custom placment rules for a placement configuration.

## SYNTAX

```
Get-SCCustomPlacementRule -PlacementConfiguration <PlacementConfigurationSettings>
 [-VMMServer <ServerConnection>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCustomPlacementRule** cmdlet gets the customm placement rules that have been added to the placement configuration for a host group.

## EXAMPLES

### Example 1: Get all of the custom placement rules for a specified host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> $CustomPlacementRule = Get-SCCustomPlacementRule -PlacementConfiguration $PlacementConfig
PS C:\> $CustomPlacementRule
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and places the object in the $PlacementConfig variable.

The third command gets all custom placement rule objects for the placement configuration stored in $PlacementConfig and stores the objects in the $CustomPlacementRule variable.

The last command displays information about the custom placement rules stored in $CustomPlacementRule for the user.

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

### CustomPlacementRule
This cmdlet returns a **CustomPlacementRule** object.

## NOTES

## RELATED LINKS

[Add-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCCustomPlacementRule.md)

[Get-SCPlacementConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCPlacementConfiguration.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHostGroup.md)

[Remove-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCCustomPlacementRule.md)

[Set-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCCustomPlacementRule.md)

