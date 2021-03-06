---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 88EEAAA8-77C4-47C7-99E7-41281ACD8070
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCCustomPlacementRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCCustomPlacementRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCCustomPlacementRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCCustomPlacementRule

## SYNOPSIS
Adds a custom placement rule to the placement configuration for a host group.

## SYNTAX

### MustMatch
```
Add-SCCustomPlacementRule -PlacementConfiguration <PlacementConfigurationSettings> -CustomPropertyName <String>
 [-MustMatch] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MustNotMatch
```
Add-SCCustomPlacementRule -PlacementConfiguration <PlacementConfigurationSettings> -CustomPropertyName <String>
 [-MustNotMatch] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShouldNotMatch
```
Add-SCCustomPlacementRule -PlacementConfiguration <PlacementConfigurationSettings> -CustomPropertyName <String>
 [-ShouldNotMatch] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShouldMatch
```
Add-SCCustomPlacementRule -PlacementConfiguration <PlacementConfigurationSettings> -CustomPropertyName <String>
 [-ShouldMatch] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCCustomPlacementRule** cmdlet adds a custom placement rule to the placement configuration for a host group.

## EXAMPLES

### Example 1: Add a new custom placement rule to a placement configuration for a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> $CustomProp = Get-SCCustomProperty -Name "Cost Center"
PS C:\> Add-SCCustomPlacementRule -PlacementConfiguration $PlacementConfig -MustMatch -CustomProperty $CustomProp
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and places the object in the $PlacementConfig variable.

The third command gets the custom property object named Cost Center and stores the object in the $CustomProp variable.

The last command adds a custom placement rule to the placement configuration stored in $PlacementConfig.

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

### -MustMatch
Indicates that the property value of the virtual machine must match the host.

```yaml
Type: SwitchParameter
Parameter Sets: MustMatch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MustNotMatch
Indicates that the property value of the virtual machine must not match the host.

```yaml
Type: SwitchParameter
Parameter Sets: MustNotMatch
Aliases: 

Required: True
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

### -ShouldMatch
Indicates that the property value of the virtual machine should match the host.

```yaml
Type: SwitchParameter
Parameter Sets: ShouldMatch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShouldNotMatch
Indicates that the property value of the virtual machine should not match the host.

```yaml
Type: SwitchParameter
Parameter Sets: ShouldNotMatch
Aliases: 

Required: True
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

### CustomPlacementRule
This cmdlet returns a **CustomPlacementRule** object.

## NOTES

## RELATED LINKS

[Get-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomPlacementRule.md)

[Get-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomProperty.md)

[Get-SCPlacementConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPlacementConfiguration.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Remove-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomPlacementRule.md)

[Set-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomPlacementRule.md)

