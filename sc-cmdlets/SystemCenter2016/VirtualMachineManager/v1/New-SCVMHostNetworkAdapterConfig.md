---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalSwitch.md
schema: 2.0.0
ms.assetid: 8CCB4166-324E-48E3-ABBC-11207B911F48
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostNetworkAdapterConfig.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostNetworkAdapterConfig.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostNetworkAdapterConfig.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMHostNetworkAdapterConfig

## SYNOPSIS
Creates a host network adapter configuration.

## SYNTAX

### PhysicalGenericNicDhcp
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-UseDhcpForIPConfiguration] [-MACAddress <String>] [-ConsistentDeviceName <String>]
 [-DisableAdapterDNSRegistration <Boolean>] [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalGenericNicStaticIP
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-UseStaticIPForIPConfiguration] -LogicalNetwork <LogicalNetwork> [-MACAddress <String>]
 [-ConsistentDeviceName <String>] [-IPv4Subnet <String>] [-IPv6Subnet <String>] [-IPv4Address <String>]
 [-IPv6Address <String>] [-DisableAdapterDNSRegistration <Boolean>] [-AdapterName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalNicLogicalSwitch
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 -LogicalSwitch <LogicalSwitch> -UplinkPortProfileSet <UplinkPortProfileSet> [-MACAddress <String>]
 [-ConsistentDeviceName <String>] [-DisableAdapterDNSRegistration <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalManagementNicDhcp
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-UseDhcpForIPConfiguration] [-MACAddress <String>] [-ConsistentDeviceName <String>]
 [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalManagementNicStaticIP
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-UseStaticIPForIPConfiguration] -LogicalNetwork <LogicalNetwork> [-MACAddress <String>]
 [-ConsistentDeviceName <String>] [-IPv4Subnet <String>] [-IPv6Subnet <String>] [-IPv4Address <String>]
 [-IPv6Address <String>] [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicDhcp
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterConfig>
 [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-MACAddress <String>] [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicStaticIP
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterConfig>
 [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-MACAddress <String>] [-IPv4Subnet <String>] [-IPv6Subnet <String>]
 [-IPv4Address <String>] [-IPv6Address <String>] [-AdapterName <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualGenericNicStaticIP
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-MACAddress <String>]
 [-IPv4Subnet <String>] [-IPv6Subnet <String>] [-IPv4Address <String>] [-IPv6Address <String>]
 [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualGenericNicDhcp
```
New-SCVMHostNetworkAdapterConfig [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-MACAddress <String>]
 [-AdapterName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMHostNetworkAdapterConfig** cmdlet creates a host network adapter configuration that is used during the host operating system deployment process.

## EXAMPLES

### Example 1: Create a management physical host network adapter configuration by using a static IP address
```
PS C:\>$LogicalNetwork = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> New-SCVMHostNetworkAdapterConfig -SetAsPhysicalNetworkAdapter -SetAsManagementNIC -UseStaticIPForIPConfiguration -LogicalNetwork $LogicalNetwork -MacAddress "00-1D-D8-B7-1C-00" -IPv4Subnet "10.0.0.1/24"
```

The first command gets the logical network object named LogicalNetwork01 and stores the object in the $LogicalNetwork variable.

The second command creates a physical host network adapter configuration, setting it as the management network adapter and uses a static IP address during IP configuration.
The configuration includes LogicalNetwork01, the provided MAC address, and specified subnet.

### Example 2: Create a physical host network adapter configuration that uses a logical switch
```
PS C:\>$LogicalSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> $UplinkPortProfSet = Get-SCUplinkPortProfileSet -Name "UplinkPortProfileSet01"
PS C:\> New-SCVMHostNetworkAdapterConfig -SetAsPhysicalNetworkAdapter -LogicalSwitch $LogicalSwitch -UplinkPortProfileSet $UplinkPortProfSet
```

The first command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogicalSwitch variable.

The second command gets the uplink port profile set object named UplinkPortProfileSet01 and stores the object in the $UplinkPortProfSet variable.

The last command creates a physical host network adapter configuration with LogicalSwitch01 and UplinkPortProfileSet01.

### Example 3: Create a generic virtual host network adapter configuration by using DHCP
```
PS C:\>$LogicalSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> $VMNetwork = Get-SCVMNetwork -Name "VMNetwork01"
PS C:\> New-SCVMHostNetworkAdapterConfig -SetAsVirtualNetworkAdapter -SetAsGenericNIC -UseDhcpForIPConfiguration -LogicalSwitch $LogicalSwitch -VMNetwork $VMNetwork
```

The first command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogicalSwitch variable.

The second command gets the VM network object named VMNetwork01 and stores the object in the $VMNetwork variable.

The last command creates a generic virtual host network configuration with LogicalSwtich01 and VMNetwork01 that uses DHCP to obtain an IP address.

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
Specifies the Media Access Control (MAC) address, or a set of MAC addresses, for a physical or virtual network adapter on a computer.
Valid values are: one or more MAC addresses.

Example format for a single MAC address: 

`-MACAddress "00-15-5D-B4-DC-00"`

Example format for a set of MAC addresses: 

`-MACAddress "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`

Example format for a set of MAC addresses: 

`$Macs = "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`
`Set-SCPXEServer -MACAddress $Macs`

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

To obtain an uplink port profile set object, use the Get-SCUplinkPortProfileSet cmdlet.

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

To get a VM network object, use the Get-SCVMNetwork cmdlet.

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

### HostNetworkAdapterConfig
This cmdlet returns a **HostNetworkAdapterConfig** object.

## NOTES

## RELATED LINKS

[Get-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalSwitch.md)

[Get-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMNetwork.md)

