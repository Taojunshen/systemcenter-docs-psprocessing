---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C827F85F-7E15-4260-BA27-BE1E0080BD8D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitch.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitch.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitch.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCLogicalSwitch

## SYNOPSIS
Creates a logical switch.

## SYNTAX

```
New-SCLogicalSwitch -Name <String> [-VirtualSwitchExtensions <VirtualSwitchExtension[]>]
 [-Description <String>] [-EnableSriov <Boolean>] [-SwitchUplinkMode <SwitchUplinkMode>]
 [-MinimumBandwidthMode <BandwidthMode>] [-VMMServer <ServerConnection>] [-EnablePacketDirect <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLogicalSwitch** cmdlet creates a logical switch object.

## EXAMPLES

### Example 1: Create a logical switch
```
PS C:\> $VSwitchExt = Get-SCVirtualSwitchExtension -Name "VirtualSwitchExtension01"
PS C:\> New-SCLogicalSwitch -Name "LogicalSwitch01" -VirtualSwitchExtensions $VSwitchExt -MinimumBandwidthMode Default
```

The first command gets the virtual switch extension object named VirtualSwitchExtension01 and stores the object in the $VSwitchExt variable.

The second command creates a logical switch named LogicalSwitch01 using VirtualSwitchExtension01.

## PARAMETERS

### -Description
Specifies a description for the logical switch.

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

### -EnablePacketDirect
Enables Packet Direct on the switch.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableSriov
Indicates whether single-root I/O virtualization (SR-IOV) is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -MinimumBandwidthMode
Specifies the minimum bandwidth mode for the logical switch.
The acceptable values for this parameter are:

- Default 
- Weight 
- Absolute 
- None

```yaml
Type: BandwidthMode
Parameter Sets: (All)
Aliases: 
Accepted values: Default, Weight, Absolute, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -SwitchUplinkMode
Specifies a switch uplink mode object.

```yaml
Type: SwitchUplinkMode
Parameter Sets: (All)
Aliases: 
Accepted values: NoTeam, Team, EmbeddedTeam

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

### -VirtualSwitchExtensions
Specifies an array of virtual switch extension objects.

To get a virtual switch extension object, use the **Get-SCVirtualSwitchExtension** cmdlet.

```yaml
Type: VirtualSwitchExtension[]
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

## NOTES

## RELATED LINKS

[Get-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitch.md)

[Get-SCVirtualSwitchExtension](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtension.md)

[Remove-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitch.md)

[Set-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitch.md)

