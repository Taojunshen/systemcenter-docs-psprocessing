---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalSwitchVirtualNetworkAdapter.md
schema: 2.0.0
ms.assetid: 6EA2834E-2CA9-40DF-B737-C8427CFA5BD2
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitchVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitchVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitchVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLogicalSwitchVirtualNetworkAdapter

## SYNOPSIS
Commits any changes in settings to an existing virtual network adapter (VNIC) that is connected to a logical switch.

## SYNTAX

```
Set-SCLogicalSwitchVirtualNetworkAdapter
 [-LogicalSwitchVirtualNetworkAdapter] <LogicalSwitchVirtualNetworkAdapter>
 [-EthernetAddressType <EthernetAddressType>] [-IPv4AddressType <EthernetAddressType>]
 [-IPv6AddressType <EthernetAddressType>] [-VMNetwork <VMNetwork>] [-VMSubnet <VMSubnet>]
 [-PortClassification <PortClassification>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-IPv4AddressPool <StaticIPAddressPool>] [-IPv6AddressPool <StaticIPAddressPool>]
 [-InheritsAddressFromPhysicalNetworkAdapter <Boolean>] [-IsUsedForHostManagement <Boolean>]
 [-VMMServer <ServerConnection>] [-Name <String>] [-Description <String>] [-RemoveVMNetwork] [-RemoveVMSubnet]
 [-RemovePortClassification] [-RemoveIPv4AddressPool] [-RemoveIPv6AddressPool] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLogicalSwitchVirtualNetworkAdapter** cmdlet commits changes made to an existing virtual network adapter that was added to the Uplink Port Profile as part of the logical switch definition.

## EXAMPLES

### Example 1: Rename a logical switch virtual network adapter
```
PS C:\>$HostVNic= Get-SCLogicalSwitchVirtualNetworkAdapter -Name "LogSw01_hostMgmt"
PS C:\> Set-SCLogicalSwitchVirtualNetworkAdapter -LogicalSwitchVirtualNetworkAdapter $HostVNic -Name "LogSw01_cluster"
```

The first command gets a logical switch virtual network adapter by using the Get-SCLogicalSwitchVirtualNetworkAdapter cmdlet, and then stores it in the $HostVNic variable.

The second command renames the adapter in $HostVNic.

## PARAMETERS

### -Description
Specifies a description for the virtual network adapter.

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

### -EthernetAddressType
Specifies an Ethernet address type.
The acceptable values for this parameter are:

- Dynamic
- Static

```yaml
Type: EthernetAddressType
Parameter Sets: (All)
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4AddressPool
Specifies a static address pool that contains IPv4 addresses.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4AddressType
Specifies an IPv4 address type.
The acceptable values for this parameter are:

- Dynamic
- Static

```yaml
Type: EthernetAddressType
Parameter Sets: (All)
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6AddressPool
Specifies a static address pool that contains IPv6 addresses.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6AddressType
Specifies an IPv6 address type.
The acceptable values for this parameter are:

- Dynamic
- Static

```yaml
Type: EthernetAddressType
Parameter Sets: (All)
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InheritsAddressFromPhysicalNetworkAdapter
Indicates whether the network adapter inherits its address from a physical network adapter.

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

### -IsUsedForHostManagement
Indicates whether the virtual network adapter is used for host management.

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

### -LogicalSwitchVirtualNetworkAdapter
Specifies a logical switch virtual network adapter object.

```yaml
Type: LogicalSwitchVirtualNetworkAdapter
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

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

### -PortClassification
Specifies the port classification of the switch to which the virtual network adapter connects.

```yaml
Type: PortClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RemoveIPv4AddressPool
Indicates that this cmdlet removes an IPv4 address pool.

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

### -RemoveIPv6AddressPool
Indicates that this cmdlet removes an IPv6 address pool.

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

### -RemovePortClassification
Indicates that this cmdlet removes a port classification.

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

### -RemoveVMNetwork
Indicates that this cmdlet removes a virtual machine network.

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

### -RemoveVMSubnet
Indicates that this cmdlet removes a virtual machine subnet.

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

### -VLanEnabled
Indicates whether to enable a virtual LAN (VLAN) for use by virtual machines on a Hyper-V or Citrix XenServer host. 



Example format for a single VLAN: `-VLANEnabled -VLANMode "Access" -VLANID 35`

Example format for multiple VLANs: `-VLANEnabled -VLANMode "Trunk"  -VLANTrunkID 1,2,100,200,1124`

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

### -VLanID
Assigns a numerical identifier in the range 1-4094 to a virtual network adapter on a virtual machine or to a physical network adapter on a virtual machine host.

Configure a VLanID on a Hyper-V, VMware ESX, or Citrix XenServer host on an externally bound physical network adapter when the VLan mode is Access.

Configure a VLanID on a virtual network adapter of a virtual machine bound to a physical network adapter on the host, or bound to an internal virtual network on the host.

Example format: `-VLanEnabled -VLanMode "Access" -VLANID 35`

```yaml
Type: UInt16
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

### -VMNetwork
Specifies a VM network object.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSubnet
Specifies a virtual machine subnet object.

To obtain a **VMSubnet** object, use the Get-SCVMSubnet cmdlet.

```yaml
Type: VMSubnet
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

[Get-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitchVirtualNetworkAdapter.md)

[New-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitchVirtualNetworkAdapter.md)

[Remove-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitchVirtualNetworkAdapter.md)

