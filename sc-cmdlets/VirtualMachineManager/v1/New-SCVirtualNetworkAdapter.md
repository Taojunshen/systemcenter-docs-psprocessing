---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: C39433AC-96AA-4BF0-9375-AF62A17A6CDA
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVirtualNetworkAdapter

## SYNOPSIS
Creates a virtual network adapter on a virtual machine, virtual machine template, or hardware profile used in VMM.

## SYNTAX

### VM (Default)
```
New-SCVirtualNetworkAdapter [-IPv4AddressType <EthernetAddressType>] [-IPv6AddressType <EthernetAddressType>]
 [-EnableMACAddressSpoofing <Boolean>] [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>]
 [-EnableVMNetworkOptimization <Boolean>] [-VMNetwork <VMNetwork>] [-PortClassification <PortClassification>]
 [-VMSubnet <VMSubnet>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-ApplyInfrastructurePortProfileForNetworkController <Boolean>] -VM <VM> [[-VirtualNetwork] <String>]
 [-MACAddress <String>] [-MACAddressType <String>] [-NoConnection] [-Synthetic]
 [-LogicalNetwork <LogicalNetwork>] [-NoVMNetwork] [-VMwarePortGroup <String>] [-NetworkLocation <String>]
 [-NetworkTag <String>] [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### JobGroup
```
New-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] [-IPv4AddressType <EthernetAddressType>]
 [-IPv6AddressType <EthernetAddressType>] [-EnableMACAddressSpoofing <Boolean>]
 [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>] [-EnableVMNetworkOptimization <Boolean>]
 [-VMNetwork <VMNetwork>] [-PortClassification <PortClassification>] [-VMSubnet <VMSubnet>]
 [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-DevicePropertiesAdapterNameMode <DevicePropertiesAdapterNameMode>]
 [-ApplyInfrastructurePortProfileForNetworkController <Boolean>] [-VMHost <Host>]
 [-LogicalSwitch <LogicalSwitch>] -JobGroup <Guid> [[-VirtualNetwork] <String>] [-MACAddress <String>]
 [-MACAddressType <String>] [-NoConnection] [-Synthetic] [-LogicalNetwork <LogicalNetwork>]
 [-VMNetworkServiceSetting <String>] [-NoVMNetwork] [-VMwarePortGroup <String>] [-NetworkLocation <String>]
 [-NetworkTag <String>] [-DevicePropertiesAdapterName <String>] [-PortACL <PortACL>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### HardwareProfile
```
New-SCVirtualNetworkAdapter [-IPv4AddressType <EthernetAddressType>] [-IPv6AddressType <EthernetAddressType>]
 [-EnableMACAddressSpoofing <Boolean>] [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>]
 [-EnableVMNetworkOptimization <Boolean>] [-VMNetwork <VMNetwork>] [-PortClassification <PortClassification>]
 [-VMSubnet <VMSubnet>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-DevicePropertiesAdapterNameMode <DevicePropertiesAdapterNameMode>]
 [-ApplyInfrastructurePortProfileForNetworkController <Boolean>] -HardwareProfile <HardwareProfile>
 [[-VirtualNetwork] <String>] [-MACAddress <String>] [-MACAddressType <String>] [-NoConnection] [-Synthetic]
 [-LogicalNetwork <LogicalNetwork>] [-VMNetworkServiceSetting <String>] [-NoVMNetwork]
 [-VMwarePortGroup <String>] [-NetworkLocation <String>] [-NetworkTag <String>]
 [-DevicePropertiesAdapterName <String>] [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
New-SCVirtualNetworkAdapter [-IPv4AddressType <EthernetAddressType>] [-IPv6AddressType <EthernetAddressType>]
 [-EnableMACAddressSpoofing <Boolean>] [-EnableGuestIPNetworkVirtualizationUpdates <Boolean>]
 [-EnableVMNetworkOptimization <Boolean>] [-VMNetwork <VMNetwork>] [-PortClassification <PortClassification>]
 [-VMSubnet <VMSubnet>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-DevicePropertiesAdapterNameMode <DevicePropertiesAdapterNameMode>]
 [-ApplyInfrastructurePortProfileForNetworkController <Boolean>] -VMTemplate <Template>
 [[-VirtualNetwork] <String>] [-MACAddress <String>] [-MACAddressType <String>] [-NoConnection] [-Synthetic]
 [-LogicalNetwork <LogicalNetwork>] [-VMNetworkServiceSetting <String>] [-NoVMNetwork]
 [-VMwarePortGroup <String>] [-NetworkLocation <String>] [-NetworkTag <String>]
 [-DevicePropertiesAdapterName <String>] [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMHost
```
New-SCVirtualNetworkAdapter [-IPv4AddressType <EthernetAddressType>] [-IPv6AddressType <EthernetAddressType>]
 [-VMNetwork <VMNetwork>] [-PortClassification <PortClassification>] [-VMSubnet <VMSubnet>]
 [-VLanEnabled <Boolean>] [-VLanID <UInt16>] [-IPv4AddressPool <StaticIPAddressPool>]
 [-IPv6AddressPool <StaticIPAddressPool>] [-InheritsAddressFromPhysicalNetworkAdapter <Boolean>] -VMHost <Host>
 -LogicalSwitch <LogicalSwitch> [-JobGroup <Guid>] [-Name <String>] [-MACAddress <String>]
 [-MACAddressType <String>] [-IPv4Address <String>] [-IPv6Address <String>] [-PortACL <PortACL>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualNetworkAdapter** cmdlet creates a virtual network adapter on a virtual machine, virtual machine template, or hardware profile used to create virtual machines managed by Virtual Machine Manager (VMM).

Network Location


You can use the **New-SCVirtualNetworkAdapter** cmdlet to specify a network location and connect the virtual network adapter to a virtual network configured on the host when you create the adapter, or you can configure those and other settings later by using the Set-SCVirtualNetworkAdapter cmdlet.

Static or Dynamic MAC Address


You can specify whether the virtual network adapter uses a static or dynamic MAC address, and you can specify a static MAC address.

Emulated or Synthetic Virtual Network Adapters


You can use the **New-SCVirtualNetworkAdapter** cmdlet to create an adapter whose type is either emulated (the default) or synthetic.

For virtual machines on any type of host (Hyper-V, VMware, or XenServer), you can configure a virtual network adapter on the virtual machine that emulates a specific physical network adapter.

For virtual machines on Hyper-V hosts, if the guest operating system installed on a virtual machine is a virtualization-aware operating system (for example, Windows Server 2008 or Windows Server 2016, and some versions of Linux), VMM lets you configure a high-performance synthetic virtual network adapter on the virtual machine to communicate with the physical hardware on the host.
You must explicitly specify that a virtual network adapter is synthetic by using the *Synthetic* parameter.

Virtual Local Area Network


VMM includes support for configuring one or more virtual area networks (VLANs) on a host for use by virtual machines deployed on that host.
You can use the **New-SCVirtualNetworkAdapter** cmdlet (or the Set-SCVirtualNetworkAdapter cmdlet) with the *VLAN parameters to attach the virtual network adapter on a virtual machine to a VLAN.
To configure corresponding VLAN settings on the host network adapter, use the Add-SCVMHostNetworkAdapter cmdlet or the Set-SCVMHostNetworkAdapter cmdlet.

For an illustration of how to configure VLANs, see the examples for this cmdlet, and see the examples for New-SCVMHostNetworkAdapterConfig and Set-SCVMHostNetworkAdapter.

## EXAMPLES

### Example 1: Create a virtual network adapter on a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> New-SCVirtualNetworkAdapter -VM $VM
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a virtual network adapter on VM01.

### Example 2: Create a virtual network adapter on a virtual machine template
```
PS C:\>$VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> New-SCVirtualNetworkAdapter -VMTemplate $VMTemplate
```

The first command gets the virtual machine template object named VMTemplate01 and stores the object in the $VMTemplate variable.

The second command creates a virtual network adapter on VMTemplate01.

### Example 3: Create an emulated virtual network adapter and a synthetic virtual network adapter on a hardware profile
```
PS C:\>$HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> New-SCVirtualNetworkAdapter -HardwareProfile $HWProfile
PS C:\> New-SCVirtualNetworkAdapter -HardwareProfile $HWProfile -Synthetic
```

The first command gets the hardware profile object named NewHWProfile01 from the VMM library and stores the object in the $HWProfile variable.

The second command creates a virtual network adapter (a "native" or emulated adapter) on NewHWProfile01.

The last command creates a synthetic virtual network adapter on NewHWProfile01.

### Example 4: Create a virtual network adapter on a virtual machine and assign it a unique MAC address
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM04"
PS C:\> $VNIC = New-SCVirtualNetworkAdapter -VM $VM
PS C:\> $MACPool = Get-SCMACAddressPool -Name "MAC Address Pool 01"
PS C:\> Grant-SCMACAddress -MACAddressPool $MACPool -VirtualNetworkAdapter $VNIC
```

The first command gets the virtual machine object named VM04 and stores the object in the $VM variable.

The second command creates a virtual network adapter on the virtual machine stored in $VM (VM04) and stores the object in the $VNIC variable.

The third command gets the MAC address pool object named MAC Address Pool 01 and stores the object in the $MACPool variable.

The last command gets the next available MAC address from the address pool stored in $MACPool, and assigns it to the virtual network adapter stored in $VNIC.

### Example 5: Create a virtual network adapter with a static MAC address and a specific VLAN ID
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM05"
PS C:\> $LogicalNet = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> $VirtualNet = Get-SCVirtualNetwork -Name "ExternalVirtualNetwork01"
PS C:\> New-SCVirtualNetworkAdapter -VM $VM -LogicalNetwork $LogicalNet -VirtualNetwork $VirtualNet -MACAddress "00-16-D3-CC-00-1A" -MACAddressType "Static" -VLANEnabled $True -VLANId 3
```

The first command gets the virtual machine object named VM05 and stores the object in the $VM variable.

The second command gets the logical network object named LogicalNetwork01 and stores the object in the $LogicalNet variable.

The third command gets the virtual network object named ExternalVirtualNetwork01 and stores the object in the $VirtualNet variable.

The last command creates a new virtual network adapter for VM05, connects the adapter to the logical network stored in $LogicalNet and the virtual network stored in $VirtualNet.
The command provides a static MAC address for the virtual network adapter, enables VLAN and specifies a VLAN ID of 3.

Note: This example assumes that that your host is already connected to a VLAN or, if not, that your host has two network adapters.
If your host has a single network adapter, assigning the adapter to a VLAN that is unavailable to the VMM server will prevent VMM from managing the host.

## PARAMETERS

### -ApplyInfrastructurePortProfileForNetworkController
Unblocks a vNIC connected to a Network Controller managed switch to allow traffic.
It is meant for infrastructure vNICs as well as non- Network Controller managed networks connected to an Network Controller managed switch.

```yaml
Type: Boolean
Parameter Sets: VM, JobGroup, HardwareProfile, Template
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DevicePropertiesAdapterName
Specifies the name of a network adapter.

```yaml
Type: String
Parameter Sets: JobGroup, HardwareProfile, Template
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
Parameter Sets: JobGroup, HardwareProfile, Template
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
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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
Parameter Sets: VM, JobGroup, HardwareProfile, Template
Aliases: VMNetworkOptimizationEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IPv4Address
Specifies an IPv4 address.

```yaml
Type: String
Parameter Sets: VMHost
Aliases: 

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
Parameter Sets: VMHost
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

### -IPv6Address
Specifies an IPv6 address.

```yaml
Type: String
Parameter Sets: VMHost
Aliases: 

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
Parameter Sets: VMHost
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
Parameter Sets: VMHost
Aliases: 

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
Parameter Sets: JobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: VMHost
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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and VLANs that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: LogicalSwitch
Parameter Sets: VMHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MACAddress
Specifies the MAC address, or a set of MAC addresses, for a physical or virtual network adapter on a computer.

Example format for a single MAC address: 
`-MACAddress "00-15-5D-B4-DC-00"`

Example format for a set of MAC addresses: 
`-MACAddress "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: EthernetAddressType, PhysicalAddressType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a network object.

```yaml
Type: String
Parameter Sets: VMHost
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkLocation
Specifies the network location for a physical network adapter or for a virtual network adapter, or changes the default network location of a host's physical network adapter. 



Example formats: 
`-NetworkLocation $NetLoc` ($NetLoc might contain Corp.Contoso.com)
`-OverrideNetworkLocation $True -NetworkLocation "HostNICNewLocation.Contoso.com"`

```yaml
Type: String
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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
Parameter Sets: VM, JobGroup, HardwareProfile, Template
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoVMNetwork
Indicates that a virtual machine network is not specified.

```yaml
Type: SwitchParameter
Parameter Sets: VM, JobGroup, HardwareProfile, Template
Aliases: NoLogicalNetwork

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
To obtain a user role, use the Get-SCUserRole cmdlet.
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

### -Synthetic
Specifies that a device, such as a virtual network adapter, on a virtual machine deployed on a Hyper-V host is a high-performance synthetic device.
Requires a virtualization-aware guest operating system on the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: Host
Parameter Sets: VMHost
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
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetwork
Specifies a virtual machine network object.

To get a virtual machine network object, use the Get-SCVMNetwork cmdlet.

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

### -VMNetworkServiceSetting
Specifies a virtual machine network service setting.

```yaml
Type: String
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: HardwareProfile, Template
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMwarePortGroup
Specifies the VMware port group.

```yaml
Type: String
Parameter Sets: VM, JobGroup, HardwareProfile, Template
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
Parameter Sets: VM, JobGroup, HardwareProfile, Template
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualNetworkAdapter
This cmdlet returns a **VirtualNetworkAdapter** object.

## NOTES
* Requires a VMM virtual machine object, virtual machine template object, or hardware profile object, which can be retrieved by using the Get-SCVirtualMachine, Get-SCVMTemplate, and Get-SCHardwareProfile cmdlets, respectively.

## RELATED LINKS

[Get-SCHardwareProfile](xref:VirtualMachineManager/v1/Get-SCHardwareProfile.md)

[Get-SCLogicalNetwork](xref:VirtualMachineManager/v1/Get-SCLogicalNetwork.md)

[Get-SCMACAddressPool](xref:VirtualMachineManager/v1/Get-SCMACAddressPool.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCVirtualNetwork](xref:VirtualMachineManager/v1/Get-SCVirtualNetwork.md)

[Get-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Get-SCVirtualNetworkAdapter.md)

[Get-SCVMTemplate](xref:VirtualMachineManager/v1/Get-SCVMTemplate.md)

[Grant-SCMACAddress](xref:VirtualMachineManager/v1/Grant-SCMACAddress.md)

[Remove-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapter.md)

[Repair-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Repair-SCVirtualNetworkAdapter.md)

[Set-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Set-SCVirtualNetworkAdapter.md)

