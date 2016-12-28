---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F9624456-2CA3-4022-950F-77497CF7E1BD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCHostReserve.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCHostReserve.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCHostReserve.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCHostReserve

## SYNOPSIS
Modifies the host reserve settings for a host group.

## SYNTAX

### FromCPUEnabled
```
Set-SCHostReserve -Enabled <Boolean> [-CPU] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromNetworkEnabled
```
Set-SCHostReserve -Enabled <Boolean> [-Network] -HostReserve <HostReserveSettings>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromMemoryEnabled
```
Set-SCHostReserve -Enabled <Boolean> [-Memory] -HostReserve <HostReserveSettings>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskSpaceEnabled
```
Set-SCHostReserve -Enabled <Boolean> [-DiskSpace] -HostReserve <HostReserveSettings>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskIOEnabled
```
Set-SCHostReserve -Enabled <Boolean> [-DiskIO] -HostReserve <HostReserveSettings>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromCPUPlacementLevel
```
Set-SCHostReserve [-CPU] -HostReserve <HostReserveSettings> -PlacementLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromCPUVMHostReserveLevel
```
Set-SCHostReserve [-CPU] -HostReserve <HostReserveSettings> -VMHostReserveLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromCPUStartOptimizationLevel
```
Set-SCHostReserve [-CPU] -HostReserve <HostReserveSettings> -StartOptimizationLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskIOPercent
```
Set-SCHostReserve [-DiskIO] [-Percent] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromDiskIOPlacementLevel
```
Set-SCHostReserve [-DiskIO] -HostReserve <HostReserveSettings> -PlacementLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskIOStartOptimizationLevel
```
Set-SCHostReserve [-DiskIO] -HostReserve <HostReserveSettings> -StartOptimizationLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskIOVMHostReserveLevel
```
Set-SCHostReserve [-DiskIO] -HostReserve <HostReserveSettings> -VMHostReserveLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskIOIOPS
```
Set-SCHostReserve [-DiskIO] [-IOPS] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromDiskSpacePlacementLevel
```
Set-SCHostReserve [-DiskSpace] -HostReserve <HostReserveSettings> -PlacementLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskSpaceVMHostReserveLevel
```
Set-SCHostReserve [-DiskSpace] -HostReserve <HostReserveSettings> -VMHostReserveLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromDiskSpaceGB
```
Set-SCHostReserve [-DiskSpace] [-GB] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromDiskSpaceMB
```
Set-SCHostReserve [-DiskSpace] [-MB] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromDiskSpacePercent
```
Set-SCHostReserve [-DiskSpace] [-Percent] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromMemoryGB
```
Set-SCHostReserve [-Memory] [-GB] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromMemoryPercent
```
Set-SCHostReserve [-Memory] [-Percent] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromMemoryPlacementLevel
```
Set-SCHostReserve [-Memory] -HostReserve <HostReserveSettings> -PlacementLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromMemoryStartOptimizationLevel
```
Set-SCHostReserve [-Memory] -HostReserve <HostReserveSettings> -StartOptimizationLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromMemoryVMHostReserveLevel
```
Set-SCHostReserve [-Memory] -HostReserve <HostReserveSettings> -VMHostReserveLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromMemoryMB
```
Set-SCHostReserve [-Memory] [-MB] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromNetworkPlacementLevel
```
Set-SCHostReserve [-Network] -HostReserve <HostReserveSettings> -PlacementLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromNetworkMbps
```
Set-SCHostReserve [-Network] [-Mbps] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromNetworkPercent
```
Set-SCHostReserve [-Network] [-Percent] -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromNetworkVMHostReserveLevel
```
Set-SCHostReserve [-Network] -HostReserve <HostReserveSettings> -VMHostReserveLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromNetworkStartOptimizationLevel
```
Set-SCHostReserve [-Network] -HostReserve <HostReserveSettings> -StartOptimizationLevel <UInt64>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ToInherit
```
Set-SCHostReserve -Inherit <Boolean> -HostReserve <HostReserveSettings> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCHostReserve** cmdlet modifies the host reserve settings for a host group.
To modify the host reserve settings for a host group, that host group must not be inheriting its settings from a parent host group.

When you set the host reserve levels, the unit parameters, such as *GB* or *Percentage*, dictate the units in which the other levels, such as *StartOptimizationLevel* and *PlacementLevel*, are expressed.

The values for *VMHostReserveLevel*, *StartOptimizationLevel* and *PlacementLevel* must be represented in order.
For example, the value for *StartOptimizationLevel* cannot be less than the value for *VMHostReserveLevel*, and the value for *PlacementLevel* cannot be less than the value for *StartOptimizationLevel*.

When the host has less than the specified amount for *StartOptimizationLevel* available, Dynamic Optimization attempts to rebalance the load.

A host will never be forced by Power Optimization to have less than the specified amount for *PlacementLevel* available because of another node being powered off.

## EXAMPLES

### Example 1: Modify the CPU host reserve and placement settings for a specified host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $HostReserve = Get-SCHostReserve -VMHostGroup $HostGroup
PS C:\> $HostReserve | Set-SCHostReserve -CPU -PlacementLevel 75 -StartOptimizationLevel 80 -VMHostReserveLevel 90
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the host reserve object for the host group stored in $HostGroup, and then stores the object in the $HostReserve variable.

The last command uses the pipeline operator to pass the host reserve stored in $HostReserve to the **Set-SCHostReserve** cmdlet, which updates the host reerve and placement settings.

## PARAMETERS

### -CPU
Specifies a host reserve CPU resource type.

```yaml
Type: SwitchParameter
Parameter Sets: FromCPUEnabled, FromCPUPlacementLevel, FromCPUVMHostReserveLevel, FromCPUStartOptimizationLevel
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DiskIO
Specifies a host reserve Disk I/O resource type.

```yaml
Type: SwitchParameter
Parameter Sets: FromDiskIOEnabled, FromDiskIOPercent, FromDiskIOPlacementLevel, FromDiskIOStartOptimizationLevel, FromDiskIOVMHostReserveLevel, FromDiskIOIOPS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSpace
Specifies a host reserve Disk Space resource type.

```yaml
Type: SwitchParameter
Parameter Sets: FromDiskSpaceEnabled, FromDiskSpacePlacementLevel, FromDiskSpaceVMHostReserveLevel, FromDiskSpaceGB, FromDiskSpaceMB, FromDiskSpacePercent
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Enables an object when set to $True, or disables an object when set to $False.
For example, if you want to upgrade software on a virtual machine template, you can disable the template object in the VMM library to temporarily prevent users from using that object.

```yaml
Type: Boolean
Parameter Sets: FromCPUEnabled, FromNetworkEnabled, FromMemoryEnabled, FromDiskSpaceEnabled, FromDiskIOEnabled
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GB
Indicates that the unit for a host reserve resource is expressed in gigabytes (GB).

```yaml
Type: SwitchParameter
Parameter Sets: FromDiskSpaceGB, FromMemoryGB
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostReserve
Specifies a host reserve settings object.

```yaml
Type: HostReserveSettings
Parameter Sets: FromCPUEnabled, FromNetworkEnabled, FromMemoryEnabled, FromDiskSpaceEnabled, FromDiskIOEnabled, FromCPUPlacementLevel, FromCPUVMHostReserveLevel, FromCPUStartOptimizationLevel, FromDiskIOPlacementLevel, FromDiskIOStartOptimizationLevel, FromDiskIOVMHostReserveLevel, FromDiskSpacePlacementLevel, FromDiskSpaceVMHostReserveLevel, FromMemoryPlacementLevel, FromMemoryStartOptimizationLevel, FromMemoryVMHostReserveLevel, FromNetworkPlacementLevel, FromNetworkVMHostReserveLevel, FromNetworkStartOptimizationLevel, ToInherit
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: HostReserveSettings
Parameter Sets: FromDiskIOPercent, FromDiskIOIOPS, FromDiskSpaceGB, FromDiskSpaceMB, FromDiskSpacePercent, FromMemoryGB, FromMemoryPercent, FromMemoryMB, FromNetworkMbps, FromNetworkPercent
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IOPS
Indicates that the unit for a host reserve resource is expressed in disk input/output operations per second (IOPS).

```yaml
Type: SwitchParameter
Parameter Sets: FromDiskIOIOPS
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
Parameter Sets: ToInherit
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

### -MB
Indicates that the unit for a host reserve resource is expressed in megabytes (MB).

```yaml
Type: SwitchParameter
Parameter Sets: FromDiskSpaceMB, FromMemoryMB
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mbps
Indicates that the unit for a host reserve resource is expressed in megabits per second (Mbps).

```yaml
Type: SwitchParameter
Parameter Sets: FromNetworkMbps
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Memory
Specifies a host reserve Memory resource type.

```yaml
Type: SwitchParameter
Parameter Sets: FromMemoryEnabled, FromMemoryGB, FromMemoryPercent, FromMemoryPlacementLevel, FromMemoryStartOptimizationLevel, FromMemoryVMHostReserveLevel, FromMemoryMB
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Network
Specifies a host reserve Network I/O resource type.

```yaml
Type: SwitchParameter
Parameter Sets: FromNetworkEnabled, FromNetworkPlacementLevel, FromNetworkMbps, FromNetworkPercent, FromNetworkVMHostReserveLevel, FromNetworkStartOptimizationLevel
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

### -Percent
Indicates that the unit for a host reserve resource is expressed in percent (%).

```yaml
Type: SwitchParameter
Parameter Sets: FromDiskIOPercent, FromDiskSpacePercent, FromMemoryPercent, FromNetworkPercent
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlacementLevel
Specifies the host reserve level above which placement is acceptable.

```yaml
Type: UInt64
Parameter Sets: FromCPUPlacementLevel, FromDiskIOPlacementLevel, FromDiskSpacePlacementLevel, FromMemoryPlacementLevel, FromNetworkPlacementLevel
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

### -StartOptimizationLevel
Specifies the host reserve level at which dynamic optimization is started.

```yaml
Type: UInt64
Parameter Sets: FromCPUStartOptimizationLevel, FromDiskIOStartOptimizationLevel, FromMemoryStartOptimizationLevel, FromNetworkStartOptimizationLevel
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostReserveLevel
Specifies the host reserve level at which placement returns an error if starting a virtual machine would require dropping below this level.

```yaml
Type: UInt64
Parameter Sets: FromCPUVMHostReserveLevel, FromDiskIOVMHostReserveLevel, FromDiskSpaceVMHostReserveLevel, FromMemoryVMHostReserveLevel, FromNetworkVMHostReserveLevel
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

### HostReserve
This cmdlet returns a HostReserve object.

## NOTES

## RELATED LINKS

[Get-SCHostReserve](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHostReserve.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

