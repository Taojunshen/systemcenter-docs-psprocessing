---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0810DDBB-AF78-4BD7-BFDF-B7262AFADE22
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterNativePortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterNativePortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterNativePortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCVirtualNetworkAdapterNativePortProfile

## SYNOPSIS
Creates a virtual network adapter native port profile.

## SYNTAX

```
New-SCVirtualNetworkAdapterNativePortProfile [-Description <String>] [-VMMServer <ServerConnection>]
 [-Name] <String> [-AllowTeaming <Boolean>] [-AllowMacAddressSpoofing <Boolean>]
 [-AllowIeeePriorityTagging <Boolean>] [-EnableDhcpGuard <Boolean>]
 [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>] [-EnableRouterGuard <Boolean>]
 [-MinimumBandwidthWeight <Int32>] [-MinimumBandwidthAbsolute <Int32>] [-MaximumBandwidth <Int32>]
 [-EnableVmq <Boolean>] [-EnableIPsecOffload <Boolean>] [-EnableIov <Boolean>] [-EnableVrss <Boolean>]
 [-EnableRdma <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualNetworkAdapterNativePortProfile** cmdlet creates a network adapter native port profile.

## EXAMPLES

### Example 1: Create a virtual network adapter native port profile
```
PS C:\> New-SCVirtualNetworkAdapterNativePortProfile -Name "VirtualNetworkAdapterNativePortProf01" -AllowMacAddressSpoofing $True
```

This command creates a virtual network adapter native port profile named VirtualNetworkAdapterNativePortProf01 and allows MAC address spoofing.

## PARAMETERS

### -AllowIeeePriorityTagging
Indicates whether outgoing packets from the virtual machine adapter are allowed to be tagged with IEEE 802.1p priority.
When set to $False, the priority value in the packet is reset to zero.

The default value is $False.

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

### -AllowMacAddressSpoofing
Indicates whether media access control (MAC) address spoofing is enabled.
MAC address spoofing allows virtual machines to change the source MAC address in outgoing packets to one that is not assigned to them.

The default value is $False.

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

### -AllowTeaming
Indicates whether guest teaming is allowed.
Guest teaming allows the virtual network adapter to be teamed with other network adapters that are connected to the same switch.

The default value is $False.

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

### -Description
Specifies a description for the port profile.

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

### -EnableDhcpGuard
Indicates whether Dynamic Host Configuration Protocol (DHCP) guard is enabled.
DHCP guard drops DHCP server messages from unauthorized virtual machines pretending to be DHCP servers.

The default value is $False.

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

### -EnableGuestIPNetworkVirtualizationUpdates
Indicates whether IP network virtualization updates by a guest is enabled.

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

### -EnableIPsecOffload
Indicates whether IPsec task offloading is enabled.
When sufficient hardware resources are not available, the security associations are not offloaded and are handled in software by the guest operating system.
Support from a physical network adapter and the guest operating system is required to offload IPsec tasks.

The default value is $False.

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

### -EnableIov
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

### -EnableRdma
The default value is $False.

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

### -EnableRouterGuard
Indicates whether router advertisement and redirection messages from authorized virtual machines pretending to be routers are dropped.

The default value is $False.

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

### -EnableVmq
Indicates whether virtual machine queue (VMQ) is enabled.
A physical network adapter is required to enable VMQ.

The default value is $False.

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

### -EnableVrss
Indicates whether to enable virtual receive-side scaling for this port profile.

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

### -MaximumBandwidth
Specifies the maximum bandwidth, in Megabits per second (Mbps), for a virtual network adapter port profile.

The default value is 0.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBandwidthAbsolute
Specifies the minimum bandwidth, in Megabits per second (Mbps), for a virtual network adapter port profile.

The default value is 0.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumBandwidthWeight
Specifies the minimum bandwidth relative to how much bandwidth the virtual network adapter intends to use compared to other virtual network adapters connected to the same switch.
Valid values are 0 to 100.

The default value is 0.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

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
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCVirtualNetworkAdapterNativePortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterNativePortProfile.md)

[Remove-SCVirtualNetworkAdapterNativePortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapterNativePortProfile.md)

[Set-SCVirtualNetworkAdapterNativePortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterNativePortProfile.md)

