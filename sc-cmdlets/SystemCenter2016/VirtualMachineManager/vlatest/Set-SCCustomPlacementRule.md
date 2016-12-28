---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 76F60843-4EF2-4ECE-AD73-5FDEA9EDEEDA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomPlacementRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomPlacementRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomPlacementRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCCustomPlacementRule

## SYNOPSIS
Modifes a custom placement rule in the placement configuration of a host group.

## SYNTAX

### ShouldNotMatch
```
Set-SCCustomPlacementRule -CustomPlacementRule <CustomPlacementRule> [-ShouldNotMatch]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ShouldMatch
```
Set-SCCustomPlacementRule -CustomPlacementRule <CustomPlacementRule> [-ShouldMatch]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### MustNotMatch
```
Set-SCCustomPlacementRule -CustomPlacementRule <CustomPlacementRule> [-MustNotMatch]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### MustMatch
```
Set-SCCustomPlacementRule -CustomPlacementRule <CustomPlacementRule> [-MustMatch]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCCustomPlacementRule** cmdlet modifies an existing custom placement rule in the placement configuration for a host group.

## EXAMPLES

### Example 1: Modify an existing custom placement rule in the placement configuration for a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> $CPRule = Get-SCCustomPlacementRule -PlacementConfiguration $PlacementConfig | where {$_.CustomPropertyName -eq "Charge Code"}
PS C:\> Set-SCCustomPlacementRule -MustMatch -CustomPlacementRule $CPRule
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and places the object in the $PlacementConfig variable.

The third command gets the custom placement rule object named Charge Code and stores the object in the $CPRule variable.

The last command modifes the custom placement rule for custom property Charge Code to be a Must Match rule.

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

### -CustomPlacementRule
Specifies a custom placement rule object.

```yaml
Type: CustomPlacementRule
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

## NOTES

## RELATED LINKS

[Add-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCCustomPlacementRule.md)

[Get-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomPlacementRule.md)

[Get-SCPlacementConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPlacementConfiguration.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Remove-SCCustomPlacementRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomPlacementRule.md)

