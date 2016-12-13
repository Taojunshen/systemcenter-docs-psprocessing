---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPhysicalComputerNetworkAdapterProfile.md
schema: 2.0.0
ms.assetid: 21E92236-5C31-4B80-9698-40338797A719
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCPhysicalComputerNetworkAdapterProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCPhysicalComputerNetworkAdapterProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCPhysicalComputerNetworkAdapterProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCPhysicalComputerNetworkAdapterProfile

## SYNOPSIS
Creates a profile for network configuration applied to an operating system that is deployed to physical computer.

## SYNTAX

### PhysicalManagementNicDhcp
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-ConsistentDeviceName <String>] [-UseDhcpForIPConfiguration] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalGenericNicDhcp
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-ConsistentDeviceName <String>] [-UseDhcpForIPConfiguration] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalManagementNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-ConsistentDeviceName <String>] [-UseStaticIPForIPConfiguration]
 -LogicalNetwork <LogicalNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### PhysicalNicLogicalSwitch
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-ConsistentDeviceName <String>] -LogicalSwitch <LogicalSwitch> -UplinkPortProfileSet <UplinkPortProfileSet>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalGenericNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-ConsistentDeviceName <String>] [-UseStaticIPForIPConfiguration]
 -LogicalNetwork <LogicalNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### VirtualGenericNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicStaticIP
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterProfile>
 [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicDhcp
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterProfile>
 [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualGenericNicDhcp
```
New-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCPhysicalComputerNetworkAdapterProfile** cmdlet creates a profile for network configuration applied to an operating system that is deployed to physical computer.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ConsistentDeviceName
Specifies a consistent device name for a network adapter.

```yaml
Type: String
Parameter Sets: PhysicalManagementNicDhcp, PhysicalGenericNicDhcp, PhysicalManagementNicStaticIP, PhysicalNicLogicalSwitch, PhysicalGenericNicStaticIP
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
Parameter Sets: PhysicalManagementNicStaticIP, PhysicalGenericNicStaticIP
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
Parameter Sets: PhysicalNicLogicalSwitch, VirtualGenericNicStaticIP, VirtualManagementNicStaticIP, VirtualManagementNicDhcp, VirtualGenericNicDhcp
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

### -PortClassification
Specifies the port classification of the switch to which the virtual network adapter connects.

```yaml
Type: PortClassification
Parameter Sets: VirtualGenericNicStaticIP, VirtualManagementNicStaticIP, VirtualManagementNicDhcp, VirtualGenericNicDhcp
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
Parameter Sets: PhysicalManagementNicDhcp, PhysicalManagementNicStaticIP, VirtualManagementNicStaticIP, VirtualManagementNicDhcp
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
Parameter Sets: PhysicalManagementNicDhcp, PhysicalGenericNicDhcp, PhysicalManagementNicStaticIP, PhysicalNicLogicalSwitch, PhysicalGenericNicStaticIP
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
Parameter Sets: VirtualGenericNicStaticIP, VirtualManagementNicStaticIP, VirtualManagementNicDhcp, VirtualGenericNicDhcp
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
Type: PhysicalComputerNetworkAdapterProfile
Parameter Sets: VirtualManagementNicStaticIP, VirtualManagementNicDhcp
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
Parameter Sets: PhysicalManagementNicDhcp, PhysicalGenericNicDhcp, VirtualManagementNicDhcp, VirtualGenericNicDhcp
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
Parameter Sets: PhysicalManagementNicStaticIP, PhysicalGenericNicStaticIP, VirtualGenericNicStaticIP, VirtualManagementNicStaticIP
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
Parameter Sets: VirtualGenericNicStaticIP, VirtualManagementNicStaticIP, VirtualManagementNicDhcp, VirtualGenericNicDhcp
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

### PhysicalComputerNetworkAdapterProfile
This cmdlet returns a **PhysicalComputerNetworkAdapterProfile** object.

## NOTES

## RELATED LINKS

[Get-SCPhysicalComputerNetworkAdapterProfile](xref:VirtualMachineManager/v1/Get-SCPhysicalComputerNetworkAdapterProfile.md)

[Get-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md)

[Get-SCVMNetwork](xref:VirtualMachineManager/v1/Get-SCVMNetwork.md)

[Remove-SCPhysicalComputerNetworkAdapterProfile](xref:VirtualMachineManager/v1/Remove-SCPhysicalComputerNetworkAdapterProfile.md)

