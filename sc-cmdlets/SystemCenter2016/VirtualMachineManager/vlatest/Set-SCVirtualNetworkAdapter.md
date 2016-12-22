---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 625431E8-2EBC-4206-8F95-653B05B9E492
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualNetworkAdapter

## SYNOPSIS
Changes properties of a virtual network adapter associated with a virtual machine, a virtual machine template, or a hardware profile used to create virtual machines in VMM.

## SYNTAX

### VirtualNicSpecified
```
Set-SCVirtualNetworkAdapter [-IPv4AddressType <EthernetAddressType>] [-IPv6AddressType <EthernetAddressType>]
 [-EnableMACAddressSpoofing <Boolean>] [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>]
 [-EnableVMNetworkOptimization <Boolean>] [-VMNetwork <VMNetwork>] [-VMNetworkServiceSetting <String>]
 [-PortClassification <PortClassification>] [-VMSubnet <VMSubnet>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-DevicePropertiesAdapterNameMode <DevicePropertiesAdapterNameMode>]
 [-ApplyInfrastructurePortProfileForNetworkController <Boolean>] [-VMMServer <ServerConnection>]
 [-VirtualNetworkAdapter] <VirtualNetworkAdapter> [-VirtualNetwork <String>] [-RequiredBandwidth <Decimal>]
 [-NoConnection] [-MACAddress <String>] [-MACAddressType <String>] [-LogicalNetwork <LogicalNetwork>]
 [-NoLogicalNetwork] [-JobGroup <Guid>] [-VMwarePortGroup <String>] [-NetworkLocation <String>]
 [-NetworkTag <String>] [-NoPortClassification]
 [-IPv4Addresses <System.Collections.Generic.List`1[System.String]>]
 [-IPv6Addresses <System.Collections.Generic.List`1[System.String]>]
 [-IPv4AddressPools <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StaticIPAddressPool]>]
 [-IPv6AddressPools <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StaticIPAddressPool]>]
 [-DevicePropertiesAdapterName <String>] [-PortACL <PortACL>] [-RemovePortACL] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### SlotIdSpecified
```
Set-SCVirtualNetworkAdapter [-IPv4AddressType <EthernetAddressType>] [-IPv6AddressType <EthernetAddressType>]
 [-EnableMACAddressSpoofing <Boolean>] [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>]
 [-EnableVMNetworkOptimization <Boolean>] [-VMNetwork <VMNetwork>] [-VMNetworkServiceSetting <String>]
 [-PortClassification <PortClassification>] [-VMSubnet <VMSubnet>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-DevicePropertiesAdapterNameMode <DevicePropertiesAdapterNameMode>]
 [-ApplyInfrastructurePortProfileForNetworkController <Boolean>] [-VMMServer <ServerConnection>]
 -SlotID <Int32> [-VirtualNetwork <String>] [-RequiredBandwidth <Decimal>] [-NoConnection]
 [-MACAddress <String>] [-MACAddressType <String>] [-LogicalNetwork <LogicalNetwork>] [-NoLogicalNetwork]
 -JobGroup <Guid> [-VMwarePortGroup <String>] [-NetworkLocation <String>] [-NetworkTag <String>]
 [-NoPortClassification] [-DevicePropertiesAdapterName <String>] [-PortACL <PortACL>] [-RemovePortACL]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### IsCheckpoint
```
Set-SCVirtualNetworkAdapter [-VLanEnabled <Boolean>] [-VLanID <UInt16>] [-VMMServer <ServerConnection>]
 [[-VirtualNetworkAdapter] <VirtualNetworkAdapter>] -VirtualNetwork <String> [-Checkpoint] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualNetworkAdapter** cmdlet changes one or more properties of a virtual network adapter associated with a virtual machine, virtual machine template, or hardware profile used to create virtual machines in a Virtual Machine Manager (VMM) environment. 

Operations you can perform include the following: 

- Connect a virtual network adapter to a virtual network. 

- Disconnect a virtual network adapter from a virtual network. 

- Specify a network location and network tag on a virtual network adapter. 

- Specify a MAC address on the virtual network adapter. 

- Enable the use of a virtual local area network (VLAN) and specify a VLAN ID (numerical identifier) for that VLAN on the virtual network adapter.

## EXAMPLES

### Example 1: Connect a virtual network adapter to a virtual network
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $Adapter = Get-SCVirtualNetworkAdapter -VM $VM | where { $_.PhysicalAddress -eq "00:16:D3:CC:00:1B" }
PS C:\> Set-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapter -VirtualNetwork "ExternalVirtualNetwork01"
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets all virtual network adapter objects on VM01, selects the adapter object with the physical (MAC) address of 00:16:D3:CC:00:1B, and then stores the object in the $Adapter variable.

The last command connects the virtual network adapter stored in $Adapter to the virtual network named ExternalVirtualNetwork01 on the host that contains VM01.

### Example 2: Specify a static MAC address for a virtual network adapter
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02" 
PS C:\> $Adapter = Get-SCVirtualNetworkAdapter -VM $VM | where { $_.ID -eq "5c0ee80a-731f-41c8-92f0-85a1619f9a1b" }
PS C:\> Set-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapter -PhysicalAddressType "Static" -PhysicalAddress "00:16:D3:CC:00:1C"
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets all virtual network adapter objects on VM02, selects the virtual network adapter with the specified ID, and then stores the object in the $Adapter variable.
This example assumes that this adapter currently has a dynamic MAC address.

The last command specifies that the virtual network adapter stored in $Adapter use the static MAC address 00:16:D3:CC:00:1C.

### Example 3: Specify a static MAC address and assign it to an existing virtual network adapter
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> Set-SCVirtualNetworkAdapter -VirtualNetworkAdapter (Get-VirtualNetworkAdapter -VM $VM | where { $_.ID -eq "95e9cfda-861c-44a3-b2ba-2f796dfe691c"}) -MACAddressType "Static" -MACAddress "00-00-00-00-00-00"
```

The first command gets the virtual machine object named VM03 and stores the object in the $VM variable.

The second command gets the virtual network adapter object on VM03 by ID, specifies that the adapter uses a static MAC address type, and assigns it a MAC address.

### Example 4: Disconnect the specified virtual network adapter from the virtual network
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM04"
PS C:\> $Adapters = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> Set-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapters[1] -NoConnection
```

The first command gets the virtual machine object named VM04 and stores the object in the $VM variable.

The second command gets all virtual network adapter objects on VM04 and stores the adapter objects in $Adapters.
This example assumes that VM04 has at least two virtual network adapters.

The last command uses the *NoConnection* parameter to disconnect the second virtual network adapter (Adapters\[1\]) from any virtual network that it is connected to.

### Example 5: Specify a VMware port group for an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM05"
PS C:\> $Adapter = $VM.VirtualNetworkAdapters[0]
PS C:\> Set-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapter -VMwarePortGroup "VM Network"
```

The first command gets the virtual machine object named VM05 and stores the object in the $VM variable.

The second command stores the first \[0\] virtual network adapter on VM05 in the $Adapter variable.

The last command sets the virtual network adapter for the adapter stored in $Adapter to VM Network, which is the name of the VMware port group that you want this adapter to connect to.

## PARAMETERS

### -ApplyInfrastructurePortProfileForNetworkController
Unblocks a vNIC connected to a network controller managed switch to allow traffic.
It is meant for infrastructure vNICs as well as non-network controller managed networks connected to a network controller managed switch.

```yaml
Type: Boolean
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Checkpoint
Indicates to use the Can Checkpoint permission.

```yaml
Type: SwitchParameter
Parameter Sets: IsCheckpoint
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DevicePropertiesAdapterName
Specifies the name of a network adapter.

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DevicePropertiesAdapterNameMode
Specifies the adapter name mode.

```yaml
Type: DevicePropertiesAdapterNameMode
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 
Accepted values: Disabled, VMNetwork, Custom

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
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: GuestIPNetworkVirtualizationUpdatesEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableMACAddressSpoofing
Enables, when set to $True, MAC address spoofing.

```yaml
Type: Boolean
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: MACAddressesSpoofingEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableVMNetworkOptimization
Enables, when set to $True, virtual machine network optimization.

This feature improves network performance for virtual machines with network adapters that support virtual machine queue (VMQ) or TCP Chimney Offload.
VMQ enables creating a unique network queue for each virtual network adapter.
TCP Chimney Offload enables network traffic processing to be offloaded from the networking stack.

```yaml
Type: Boolean
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: VMNetworkOptimizationEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4AddressPools
Specifies a list of IPv4 address pools.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StaticIPAddressPool]
Parameter Sets: VirtualNicSpecified
Aliases: IPv4AddressPool

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
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Addresses
Specifies a list of IPv4 addresses.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: VirtualNicSpecified
Aliases: IPv4Address

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6AddressPools
Specifies a list of IPv6 address pools.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StaticIPAddressPool]
Parameter Sets: VirtualNicSpecified
Aliases: IPv6AddressPool

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
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Addresses
Specifies a list of IPv6 addresses.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: VirtualNicSpecified
Aliases: IPv6Address

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: VirtualNicSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: SlotIdSpecified
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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and VLANs that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies the MAC address, or a set of MAC addresses, for a physical or virtual network adapter on a computer.

- Example format for a single MAC address: `-MACAddress "00-15-5D-B4-DC-00"`
- Example format for a set of MAC addresses: `-MACAddress "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: EthernetAddress, PhysicalAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddressType
Specifies the type of MAC address to use for a virtual network adapter.
Valid values are: Static, Dynamic.

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: EthernetAddressType, PhysicalAddressType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkLocation
Specifies the network location for a physical network adapter or for a virtual network adapter, or changes the default network location of a host's physical network adapter. 

Example formats: 
- `-NetworkLocation $NetLoc` ($NetLoc might contain Corp.Contoso.com)
- `-OverrideNetworkLocation $True -NetworkLocation "HostNICNewLocation.Contoso.com"`

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkTag
Specifies a word or phrase to associate with a virtual network adapter that is configured to connect to a specific internal or external network on the host.

The *NetworkTag* parameter identifies all virtual machines with the same *NetworkTag* as members of the same network.
VMM uses a *NeworkTag* (if one exists) when it evaluates hosts as possible candidates on which to deploy a virtual machine.
If the host does not include virtual machines on the network with the same *NetworkTag* as the virtual machine to be placed, the host receives zero stars in the placement process.

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoConnection
Disconnects a virtual network adapter from a virtual network.

```yaml
Type: SwitchParameter
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoLogicalNetwork
Indicates that no logical network is associated with this virtual network adapter.

```yaml
Type: SwitchParameter
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: NoVMNetwork

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoPortClassification
Indicates that a port classification is not provided.

```yaml
Type: SwitchParameter
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### -PortACL
Specifies a port ACL object.

```yaml
Type: PortACL
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
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
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePortACL
Indicates that this operation removes the port access control list (ACL).

```yaml
Type: SwitchParameter
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredBandwidth
Specifies the network bandwidth required by a network adapter.

```yaml
Type: Decimal
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
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

### -SlotID
Specifies a numerical ID used to identify a device.

```yaml
Type: Int32
Parameter Sets: SlotIdSpecified
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VLanEnabled
Indicates whether to enable a virtual LAN (VLAN) for use by virtual machines on a Hyper-V or Citrix XenServer host. 

- Example format for a single VLAN: `-VLANEnabled -VLANMode "Access" -VLANID 35`
- Example format for multiple VLANs: `-VLANEnabled -VLANMode "Trunk"  -VLANTrunkID 1,2,100,200,1124`

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

To get a VM network object, use the **Get-SCVMNetwork** cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkServiceSetting
Specifies a VM network service setting.

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSubnet
Specifies a virtual machine subnet object.

To obtain a **VMSubnet** object, use the **Get-SCVMSubnet** cmdlet.

```yaml
Type: VMSubnet
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMwarePortGroup
Specifies the VMware port group.

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network object.

```yaml
Type: String
Parameter Sets: VirtualNicSpecified, SlotIdSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: IsCheckpoint
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapter
Specifies a virtual network adapter object for a virtual machine.

Types of hosts support the following number of virtual network adapters: 

- Hyper-V. 
Up to four emulated adapters per virtual machine.
There is no driver available for an emulated network adapter on a Windows Server 2003 x64 guest operating system.

- Hyper-V. 
Up to eight synthetic adapters per virtual machine.
- VMware ESX. 
Up to four emulated adapters per virtual machine.
- Citrix XenServer. 
Up to seven emulated adapters per virtual machine.

```yaml
Type: VirtualNetworkAdapter
Parameter Sets: VirtualNicSpecified
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: VirtualNetworkAdapter
Parameter Sets: IsCheckpoint
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualNetworkAdapter
This cmdlet returns a **VirtualNetworkAdapter** object.

## NOTES
* Requires a VMM virtual network adapter object, which can be retrieved by using the **Get-SCVirtualNetworkAdapter** cmdlet.

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapter.md)

[New-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapter.md)

[Remove-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapter.md)

[Repair-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetworkAdapter.md)

