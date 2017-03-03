---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1CBB0DC4-CA51-475F-874A-4BA914C1A200
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerNetworkAdapterConfig.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerNetworkAdapterConfig.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerNetworkAdapterConfig.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCPhysicalComputerNetworkAdapterConfig

## SYNOPSIS
Creates a network adapter configuration that is applied to an operating system deployed on a physical computer.

## SYNTAX

### PhysicalGenericNicDhcp
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-UseDhcpForIPConfiguration] [-MACAddress <String>] [-ConsistentDeviceName <String>]
 [-DisableAdapterDNSRegistration <Boolean>] [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalGenericNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-UseStaticIPForIPConfiguration] -LogicalNetwork <LogicalNetwork> [-MACAddress <String>]
 [-ConsistentDeviceName <String>] [-IPv4Subnet <String>] [-IPv6Subnet <String>] [-IPv4Address <String>]
 [-IPv6Address <String>] [-DisableAdapterDNSRegistration <Boolean>] [-AdapterName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalNicLogicalSwitch
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 -LogicalSwitch <LogicalSwitch> -UplinkPortProfileSet <UplinkPortProfileSet> [-MACAddress <String>]
 [-ConsistentDeviceName <String>] [-DisableAdapterDNSRegistration <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalManagementNicDhcp
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-UseDhcpForIPConfiguration] [-MACAddress <String>] [-ConsistentDeviceName <String>]
 [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalManagementNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-UseStaticIPForIPConfiguration] -LogicalNetwork <LogicalNetwork> [-MACAddress <String>]
 [-ConsistentDeviceName <String>] [-IPv4Subnet <String>] [-IPv6Subnet <String>] [-IPv4Address <String>]
 [-IPv6Address <String>] [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicDhcp
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterConfig>
 [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-MACAddress <String>] [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterConfig>
 [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-MACAddress <String>] [-IPv4Subnet <String>] [-IPv6Subnet <String>]
 [-IPv4Address <String>] [-IPv6Address <String>] [-AdapterName <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualGenericNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-MACAddress <String>]
 [-IPv4Subnet <String>] [-IPv6Subnet <String>] [-IPv4Address <String>] [-IPv6Address <String>]
 [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualGenericNicDhcp
```
New-SCPhysicalComputerNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-MACAddress <String>]
 [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCPhysicalComputerNetworkAdapterConfig** cmdlet creates a network adapter configuration that is applied to an operating system deployed on a physical computer.

## EXAMPLES


## PARAMETERS

### -AdapterName
Specifies the name of the network adapter.

```yaml
Type: String
Parameter Sets: PhysicalGenericNicDhcp, PhysicalGenericNicStaticIP, PhysicalManagementNicDhcp, PhysicalManagementNicStaticIP, VirtualManagementNicDhcp, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP, VirtualGenericNicDhcp
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsistentDeviceName
Specifies a consistent device name for a network adapter.

```yaml
Type: String
Parameter Sets: PhysicalGenericNicDhcp, PhysicalGenericNicStaticIP, PhysicalNicLogicalSwitch, PhysicalManagementNicDhcp, PhysicalManagementNicStaticIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAdapterDNSRegistration
Indicates whether to disable DNS registration for the network adapter.

```yaml
Type: Boolean
Parameter Sets: PhysicalGenericNicDhcp, PhysicalGenericNicStaticIP, PhysicalNicLogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Address
Specifies an IPv4 address.

```yaml
Type: String
Parameter Sets: PhysicalGenericNicStaticIP, PhysicalManagementNicStaticIP, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4Subnet
Specifies an IPv4 subnet.

```yaml
Type: String
Parameter Sets: PhysicalGenericNicStaticIP, PhysicalManagementNicStaticIP, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP
Aliases: 

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
Parameter Sets: PhysicalGenericNicStaticIP, PhysicalManagementNicStaticIP, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Subnet
Specifies an IPv6 subnet.

```yaml
Type: String
Parameter Sets: PhysicalGenericNicStaticIP, PhysicalManagementNicStaticIP, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP
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
Parameter Sets: PhysicalGenericNicStaticIP, PhysicalManagementNicStaticIP
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
Parameter Sets: PhysicalNicLogicalSwitch, VirtualManagementNicDhcp, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP, VirtualGenericNicDhcp
Aliases: 

Required: True
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
Parameter Sets: VirtualManagementNicDhcp, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP, VirtualGenericNicDhcp
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

### -SetAsGenericNIC
Indicates that the network adapter is not the management network adapter for the host.

```yaml
Type: SwitchParameter
Parameter Sets: PhysicalGenericNicDhcp, PhysicalGenericNicStaticIP, VirtualGenericNicStaticIP, VirtualGenericNicDhcp
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetAsManagementNIC
Indicates that the network adapter is the management network adapter for the host.

```yaml
Type: SwitchParameter
Parameter Sets: PhysicalManagementNicDhcp, PhysicalManagementNicStaticIP, VirtualManagementNicDhcp, VirtualManagementNicStaticIP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetAsPhysicalNetworkAdapter
Indicates that the network adapter is a physical network adapter.

```yaml
Type: SwitchParameter
Parameter Sets: PhysicalGenericNicDhcp, PhysicalGenericNicStaticIP, PhysicalNicLogicalSwitch, PhysicalManagementNicDhcp, PhysicalManagementNicStaticIP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetAsVirtualNetworkAdapter
Indicates that the network adapter is a virtual network adapter.

```yaml
Type: SwitchParameter
Parameter Sets: VirtualManagementNicDhcp, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP, VirtualGenericNicDhcp
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransientManagementNetworkAdapter
Specifies the physical network adapter that the management virtual network adapter binds to during the initial operating system deployment phase.
This property is used temporarily before the host is deployed.

```yaml
Type: PhysicalComputerNetworkAdapterConfig
Parameter Sets: VirtualManagementNicDhcp, VirtualManagementNicStaticIP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UplinkPortProfileSet
Specifies an uplink port profile set object.

To obtain an uplink port profile set object, use the **Get-SCUplinkPortProfileSet** cmdlet.

```yaml
Type: UplinkPortProfileSet
Parameter Sets: PhysicalNicLogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDhcpForIPConfiguration
Indicates that the IP address for the network adapter is obtained by using DHCP.

```yaml
Type: SwitchParameter
Parameter Sets: PhysicalGenericNicDhcp, PhysicalManagementNicDhcp, VirtualManagementNicDhcp, VirtualGenericNicDhcp
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseStaticIPForIPConfiguration
Indicates that the network adapter is configured with a static IP address.

```yaml
Type: SwitchParameter
Parameter Sets: PhysicalGenericNicStaticIP, PhysicalManagementNicStaticIP, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP
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

### -VMNetwork
Specifies a VM network object.

To get a VM network object, use the **Get-SCVMNetwork** cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: VirtualManagementNicDhcp, VirtualManagementNicStaticIP, VirtualGenericNicStaticIP, VirtualGenericNicDhcp
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PhysicalComputerNetworkAdapterConfig
This cmdlet returns a **PhysicalComputerNetworkAdapterConfig** object.

## NOTES

## RELATED LINKS

[Get-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUplinkPortProfileSet.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetwork.md)

