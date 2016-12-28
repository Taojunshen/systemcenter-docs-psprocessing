---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7D985192-DAEC-41F8-8890-0B1AF2EC6786
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPlacementConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPlacementConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPlacementConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCPlacementConfiguration

## SYNOPSIS
Sets the placement configuration settings for a host group.

## SYNTAX

### SetToMustMeet
```
Set-SCPlacementConfiguration -PlacementConfiguration <PlacementConfigurationSettings> [-MustMeet]
 [-DVDDriveRequirement] [-LoadBalancerRequirement] [-NetworkRequirement] [-PassthroughDiskRequirement]
 [-VMQueueAvailability] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetToInherit
```
Set-SCPlacementConfiguration -PlacementConfiguration <PlacementConfigurationSettings> -Inherit <Boolean>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetToOff
```
Set-SCPlacementConfiguration -PlacementConfiguration <PlacementConfigurationSettings> [-Off]
 [-DVDDriveRequirement] [-LoadBalancerRequirement] [-NetworkRequirement] [-PassthroughDiskRequirement]
 [-VMQueueAvailability] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetToFavor
```
Set-SCPlacementConfiguration -PlacementConfiguration <PlacementConfigurationSettings> [-Favor]
 [-DVDDriveRequirement] [-LoadBalancerRequirement] [-NetworkRequirement] [-PassthroughDiskRequirement]
 [-VMQueueAvailability] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetToShouldMeet
```
Set-SCPlacementConfiguration -PlacementConfiguration <PlacementConfigurationSettings> [-ShouldMeet]
 [-DVDDriveRequirement] [-LoadBalancerRequirement] [-NetworkRequirement] [-PassthroughDiskRequirement]
 [-VMQueueAvailability] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCPlacementConfiguration** cmdlet sets the placement configuration settings for a host group.
To update settings for a host group, that host group must not be inheriting its settings from a parent host group.

## EXAMPLES

### Example 1: Set the placement settings which must be met by a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> Set-SCPlacementConfiguration -PlacementConfiguration $PlacementConfig -MustMeet -ClusterReserveRequirement -HighAvailabilityRequirement -IPAddressAvailabilityRequirement
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and stores the object in the $PlacementConfig variable.

The last command updates the settings for the placement configuration stored in $PlacementConfig.

### Example 2: Reset the placement settings for a host group to inherit from the parent host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> Set-SCPlacementConfiguration -PlacementConfiguration $PlacementConfig -Inherit $True
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and stores the object in the $PlacementConfig variable.

The last command sets the placement configuration stored in $PlacementConfig to inherit its placement settings from its parent host group.

### Example 3: Turn off placement settings for a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $PlacementConfig = Get-SCPlacementConfiguration -VMHostGroup $HostGroup
PS C:\> Set-SCPlacementConfiguration -PlacementConfiguration $PlacementConfig -Off -ClusterReserveRequirement -HighAvailabilityRequirement -IPAddressAvailabilityRequirement
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the placement configuration object for the host group stored in $HostGroup and stores the object in the $PlacementConfig variable.

The last command turns off the specified placement settings for the placement configuration stored in $PlacementConfig.

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

### -DVDDriveRequirement
Indicates that the destination host must have the number of physical DVD drives required by a virtual machine for placement.
If a specific DVD drive letter has been configured on the virtual machine, the host must have a DVD drive that uses that same drive letter.

```yaml
Type: SwitchParameter
Parameter Sets: SetToMustMeet, SetToOff, SetToFavor, SetToShouldMeet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Favor
Indicates that the placement process will select a host even if the host does not meet all requirements; no warning message is displayed to the user.

```yaml
Type: SwitchParameter
Parameter Sets: SetToFavor
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Inherit
Indicates whether settings are inherited from the parent host group.

```yaml
Type: Boolean
Parameter Sets: SetToInherit
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

### -LoadBalancerRequirement
Indicates that the destination host must have access to a load balancer for placement.

```yaml
Type: SwitchParameter
Parameter Sets: SetToMustMeet, SetToOff, SetToFavor, SetToShouldMeet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MustMeet
Indicates that the placement process will not select a host if the host does not meet the requirements.

```yaml
Type: SwitchParameter
Parameter Sets: SetToMustMeet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkRequirement
Indicates that the destination host must have virtual switches that connect to each of the logical networks required by a virtual machine for placement.

```yaml
Type: SwitchParameter
Parameter Sets: SetToMustMeet, SetToOff, SetToFavor, SetToShouldMeet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Off
Indicates that a placement check is turned off, therefore placement will not consider that metric when determining whether the destination host meets placement metrics.

```yaml
Type: SwitchParameter
Parameter Sets: SetToOff
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

### -PassthroughDiskRequirement
Indicates that a destination host must support passthrough disks for placement.

```yaml
Type: SwitchParameter
Parameter Sets: SetToMustMeet, SetToOff, SetToFavor, SetToShouldMeet
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

### -ShouldMeet
Indicates that the placement process will select a host even if the host does not meet all requirements; a warning message is displayed to the user.

```yaml
Type: SwitchParameter
Parameter Sets: SetToShouldMeet
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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMQueueAvailability
Indicates that a destination host must support network optimizations for placement.

```yaml
Type: SwitchParameter
Parameter Sets: SetToMustMeet, SetToOff, SetToFavor, SetToShouldMeet
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

### PlacementConfiguration
This cmdlet returns a **PlacementConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCPlacementConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPlacementConfiguration.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

