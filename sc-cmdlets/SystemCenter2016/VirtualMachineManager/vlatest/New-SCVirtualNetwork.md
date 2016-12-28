---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C78C1078-7AFF-4744-880D-85D2DEF2DBAB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVirtualNetwork

## SYNOPSIS
Creates a virtual network on a host managed by VMM over which virtual machines on that host can communicate.

## SYNTAX

### NewCluster (Default)
```
New-SCVirtualNetwork -LogicalNetwork <LogicalNetwork[]> [-Name] <String> [-Description <String>]
 [-HostBoundVLanId <UInt16>] -JobGroup <Guid> [-BoundToVMHost <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Host
```
New-SCVirtualNetwork -VMHost <Host> [-Name] <String> [-Description <String>] [-HostBoundVLanId <UInt16>]
 [-JobGroup <Guid>] [-BoundToVMHost <Boolean>] [-VMHostNetworkAdapters <HostNetworkAdapter[]>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### LogicalSwitchWithvNic
```
New-SCVirtualNetwork -VMHost <Host> [-Description <String>] -LogicalSwitch <LogicalSwitch> [-JobGroup <Guid>]
 [-VMHostNetworkAdapters <HostNetworkAdapter[]>] [-DeployVirtualNetworkAdapters] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### LogicalSwitch
```
New-SCVirtualNetwork -VMHost <Host> [-ManagementAdapterName <String>] [-ManagementAdapterVLanId <UInt16>]
 [-ManagementAdapterVMNetwork <VMNetwork>] [-ManagementAdapterVMSubnet <VMSubnet>]
 [-ManagementAdapterPortClassification <PortClassification>]
 [-UseExplicitIPConfigurationForManagementAdapter <Boolean>]
 [-ManagementAdapterIPv4AddressType <EthernetAddressType>]
 [-ManagementAdapterIPv6AddressType <EthernetAddressType>] [-Description <String>]
 -LogicalSwitch <LogicalSwitch> [-JobGroup <Guid>] [-VMHostNetworkAdapters <HostNetworkAdapter[]>]
 [-CreateManagementAdapter] [-ManagementAdapterIPv4AddressPool <StaticIPAddressPool>]
 [-ManagementAdapterIPv6AddressPool <StaticIPAddressPool>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### Cluster
```
New-SCVirtualNetwork -VMHostCluster <HostCluster> -LogicalNetwork <LogicalNetwork[]> [-Name] <String>
 [-Description <String>] [-HostBoundVLanId <UInt16>] [-JobGroup <Guid>] [-BoundToVMHost <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualNetwork** cmdlet creates a virtual network on a host managed by Virtual Machine Manager (VMM) over which virtual machines on that host can communicate.

System Center 2016 - VMM supports the use of virtual switches to implement virtual networking scenarios for Hyper-V and Citrix XenServer hosts.
You can connect, or bind, virtual machines and hosts to a virtual network switch in a manner similar to the way that you connect physical computers to a physical network switch.

For Hyper-V hosts, and the virtual machines deployed on these hosts, VMM also supports the use of virtual switches to implement virtual local area networks (VLANs).
A VLAN is an independent logical virtual network configured within a physical LAN.
If you create multiple VLANs on a physical LAN, these separate logical segments cannot exchange data with each other.

For XenServer hosts, all virtual switches attached to a single network adapter on a XenServer host are represented as a single virtual network within VMM.

In VMM for System Center 2016, you can easily move a virtual machine that is connected to a VLAN from one host to another host and (assuming that both hosts are connected to the same VLAN), the virtual machine in its new location is already configured to resume communicating over the VLAN without any additional administrator effort.
Moving a virtual machine to a new location on a VLAN does not require software reconfiguration in the way that moving a physical computer to a new location on a physical network requires hardware reconfiguration.

VMM for System Center 2016 Networking Scenarios

The following three scenarios summarize VMM for System Center 2016 virtual networking configurations.

Scenario 1: External Virtual Network

In this scenario, virtual machines deployed on a host use a virtual network adapter to connect to a virtual switch on the host, and this virtual switch is, in turn, connected to a physical network adapter on the host.
The host is connected through a physical switch to other computers on its network.
This configuration gives the virtual machines access to the host itself, to the physical network to which the host is connected, and to other physical computers (or other physical devices) that are on the same physical network as the host.

The virtual network can support external access though a VLAN if the physical adapter on the host that it is bound to has been configured appropriately and if the virtual machines on that host are configured to use a VLAN.
For more information, type `Get-Help Add-SCVMHostNetworkAdapter -Detailed`, or `Get-Help New-SCVirtualNetworkAdapter -Detailed`.

Scenario 2: Internal Virtual Network

In this scenario, virtual machines deployed on a host use a virtual network adapter to connect to a virtual switch on the host.
In this scenario, the virtual network is bound to the host but the virtual machines do not connect via the virtual switch to a physical network adapter on the host.
This configuration establishes an internal virtual network that enables virtual machines connected to that virtual switch to communicate with each other and with services and applications on the host, but not with other computers connected to the host's physical network.

If you want to to configure an internal network that is separated into two or more VLANs, you must set the VLAN IDs on a virtual network adapter configured on the virtual machine object.
For more information, type `Get-Help New-SCVirtualNetworkAdapter -Detailed`, `Get-Help Set-SCVirtualNetworkAdapter -Detailed`, or `Get-Help Set-SCVMHostNetworkAdapter -Detailed`.

Scenario 3: Private Virtual Network

In this scenario, virtual machines deployed on a host use a virtual network adapter to connect to a virtual switch on the host.
As in scenario 2, a virtual machine does not connect via that virtual switch to a physical network adapter on the host.
Unlike scenario 2, the virtual network is not bound to the host.
This configuration establishes a private virtual network that virtual machines on the same host can use to communicate with each other, but, in this case, they cannot communicate with services or applications on the host or with any physical computers connected to the host's physical network.

## EXAMPLES

### Example 1: Create an external virtual network on a host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $HostAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "HostLANAdapter01"
PS C:\> New-SCVirtualNetwork -Name "ExternalVirtualNetwork01" -VMHost $VMHost -VMHostNetworkAdapter $HostAdapter
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the physical host network adapter object named HostLANAdapter01 on VMHost01 and stores the object in the $HostAdapter variable.

The third command creates a virtual network on VMHost01 named ExternalVirtualNetwork01, and connects the new virtual network to the host network adapter HostLANAdapter01.

This virtual network is an external virtual network.
It is attached to the physical network adapter on the host and can therefore access the LAN that the host is attached to as if it were another physical computer on that LAN.

### Example 2: Create an internal host-bound virtual network
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> New-SCVirtualNetwork -VMHost $VMHost -Name "InternalVNet01" -Description "Internal Host-Bound Virtual Network" -BoundToVMHost $True
```

The first command gets the host object VMHost01 and stores the object in the $VMHost variable.

The second command creates a virtual network on VMHost01, names it InternalVNet01, specifies a description and tag, and binds the virtual network to the physical host.

This virtual network is an internal, host-bound virtual network.
Because it is not attached to a physical network adapter on the host, it cannot access networks external to the host.
Virtual machines that are connected to this internal virtual network on this host can communicate only with each other.
Because the network is bound to the host, network communication from virtual machines to the host is also possible.

### Example 3: Create a private virtual network that is not bound to the host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> New-SCVirtualNetwork -Name "UnboundVirtualNetwork01" -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command creates a virtual network on VMHost01 named UnboundVirtualNetwork01.

Because the network is not attached to a physical network adapter on the host, it cannot access networks external to the host.
Virtual machines that are connected to this internal virtual network on this host can communicate only with each other.
Because the virtual network is not bound to the host, network communication to the host is not possible.

## PARAMETERS

### -BoundToVMHost
Indicates whether a virtual network is bound to a host.
Binding a virtual network to a host enables network communication to the host.

```yaml
Type: Boolean
Parameter Sets: NewCluster, Host, Cluster
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateManagementAdapter
Indicates that the cmdlet creates the management adapter.

```yaml
Type: SwitchParameter
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeployVirtualNetworkAdapters
Indicates that this cmdlet deploys virtual network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: LogicalSwitchWithvNic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the virtual network.

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

### -HostBoundVLanId
Assigns a VLAN to the virtual network adapter that was created for the host for the specified virtual network.

```yaml
Type: UInt16
Parameter Sets: NewCluster, Host, Cluster
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
Parameter Sets: NewCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: Host, LogicalSwitchWithvNic, LogicalSwitch, Cluster
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
Type: LogicalNetwork[]
Parameter Sets: NewCluster, Cluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalSwitch
Specifies a logical switch object.

```yaml
Type: LogicalSwitch
Parameter Sets: LogicalSwitchWithvNic, LogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementAdapterIPv4AddressPool
Specifies a **StaticIPAddressPool** object.

```yaml
Type: StaticIPAddressPool
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterIPv4AddressType
Specifies an **EthernetAddressType** object.

```yaml
Type: EthernetAddressType
Parameter Sets: LogicalSwitch
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterIPv6AddressPool
Specifies a **StaticIPAddressPool** object.

```yaml
Type: StaticIPAddressPool
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterIPv6AddressType
Specifies an **EthernetAddressType** object.

```yaml
Type: EthernetAddressType
Parameter Sets: LogicalSwitch
Aliases: 
Accepted values: Dynamic, Static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterName
Specifies a name for the management adapter.

```yaml
Type: String
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterPortClassification
Specifies a port classification for the management adapter.

```yaml
Type: PortClassification
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterVLanId
Specifies a VLAN ID for the management adapter.

```yaml
Type: UInt16
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterVMNetwork
Specifies a VM network for the management adapter.

```yaml
Type: VMNetwork
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementAdapterVMSubnet
Specifies a VM subnet for the management adapter.

```yaml
Type: VMSubnet
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: NewCluster, Host, Cluster
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

### -UseExplicitIPConfigurationForManagementAdapter
Indicates whether to use explicit IP configuration for a management adapter.

```yaml
Type: Boolean
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, type `Get-Help Add-SCVMHost -Detailed`.
See the examples for a specific cmdlet to determine how that cmdlet uses this parameter.

```yaml
Type: Host
Parameter Sets: Host, LogicalSwitchWithvNic, LogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: Cluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostNetworkAdapters
Specifies an array of one or more physical network adapter objects on a host to which virtual machines deployed on that host can connect.

Example format: `-VMHostNetworkAdapters $VMHostNICs`

```yaml
Type: HostNetworkAdapter[]
Parameter Sets: Host, LogicalSwitchWithvNic, LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualNetwork
This cmdlet returns a **VirtualNetwork** object.

## NOTES

## RELATED LINKS

[Get-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetwork.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostNetworkAdapter.md)

[Remove-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetwork.md)

[Repair-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetwork.md)

[Set-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetwork.md)

