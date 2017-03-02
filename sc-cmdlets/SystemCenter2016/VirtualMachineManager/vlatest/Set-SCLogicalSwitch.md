---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3C0AC5BD-3960-45E7-8B9A-B474CD05B39A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitch.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitch.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitch.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCLogicalSwitch

## SYNOPSIS
Updates the properties of a logical switch.

## SYNTAX

### WithExtensions (Default)
```
Set-SCLogicalSwitch [-VirtualSwitchExtensions <VirtualSwitchExtension[]>] [-Description <String>]
 [-EnableSriov <Boolean>] [-SwitchUplinkMode <SwitchUplinkMode>] [-MinimumBandwidthMode <BandwidthMode>]
 [-VMMServer <ServerConnection>] [-LogicalSwitch] <LogicalSwitch> [-Name <String>]
 [-EnablePacketDirect <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### RemoveAllExtensions
```
Set-SCLogicalSwitch [-Description <String>] [-EnableSriov <Boolean>] [-SwitchUplinkMode <SwitchUplinkMode>]
 [-MinimumBandwidthMode <BandwidthMode>] [-VMMServer <ServerConnection>] [-LogicalSwitch] <LogicalSwitch>
 [-RemoveAllExtensions] [-Name <String>] [-EnablePacketDirect <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLogicalSwitch** cmdlet updates the properties of a logical switch.

## EXAMPLES

### Example 1: Change the minimum bandwidth mode for a logical switch
```
PS C:\> Get-SCLogicalSwitch -Name "LogicalSwitch01" | Set-SCLogicalSwitch -MinimumBandwidthMode "Weight"
```

This command gets the logical switch object named LogicalSwitch01 and uses the pipeline operator to pass the object to **Set-SCLogicalSwitch**, which changes the minimum bandwitdth mode for logical switch object to Weight.

### Example 2: Remove all virtual switch extensions from a logical switch
```
PS C:\> Get-SCLogicalSwitch -Name "LogicalSwitch01" | Set-SCLogicalSwitch -RemoveAllExtensions
```

This command gets the logical switch object named LogicalSwitch01 and uses the pipeline operator to pass the object to **Set-SCLogicalSwitch**, which removes all virtual switch extensions from the logical switch object.

## PARAMETERS

### -Description
Specifies a description for the specified object.

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
Specifies whether the cmdlet enables Packet Direct on the switch.

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

### -LogicalSwitch
Specifies a logical switch object.

```yaml
Type: LogicalSwitch
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization (PRO) tip that triggered this action.
This allows for auditing of PRO tips.

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

### -RemoveAllExtensions
Indicates that all virtual switch extensions are removed from the logical switch.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveAllExtensions
Aliases: 

Required: True
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
Parameter Sets: WithExtensions
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

[New-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitch.md)

[Remove-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitch.md)

