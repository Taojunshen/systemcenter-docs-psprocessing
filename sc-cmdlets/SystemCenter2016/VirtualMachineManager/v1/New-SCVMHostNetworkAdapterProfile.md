---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalSwitch.md
schema: 2.0.0
ms.assetid: 87F3D3CA-8308-4B82-8305-9F6722BD4139
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostNetworkAdapterProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostNetworkAdapterProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostNetworkAdapterProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMHostNetworkAdapterProfile

## SYNOPSIS
Creates a host network adapter profile.

## SYNTAX

### PhysicalManagementNicDhcp
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-ConsistentDeviceName <String>] [-UseDhcpForIPConfiguration] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalGenericNicDhcp
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-ConsistentDeviceName <String>] [-UseDhcpForIPConfiguration] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalManagementNicStaticIP
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsManagementNIC] [-ConsistentDeviceName <String>] [-UseStaticIPForIPConfiguration]
 -LogicalNetwork <LogicalNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### PhysicalNicLogicalSwitch
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-ConsistentDeviceName <String>] -LogicalSwitch <LogicalSwitch> -UplinkPortProfileSet <UplinkPortProfileSet>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalGenericNicStaticIP
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsPhysicalNetworkAdapter]
 [-SetAsGenericNIC] [-ConsistentDeviceName <String>] [-UseStaticIPForIPConfiguration]
 -LogicalNetwork <LogicalNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### VirtualGenericNicStaticIP
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicStaticIP
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterProfile>
 [-UseStaticIPForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualManagementNicDhcp
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsManagementNIC] -TransientManagementNetworkAdapter <PhysicalComputerNetworkAdapterProfile>
 [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch> [-PortClassification <PortClassification>]
 -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VirtualGenericNicDhcp
```
New-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-SetAsVirtualNetworkAdapter]
 [-SetAsGenericNIC] [-UseDhcpForIPConfiguration] -LogicalSwitch <LogicalSwitch>
 [-PortClassification <PortClassification>] -VMNetwork <VMNetwork> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMHostNetworkAdapterProfile** cmdlet creates a network adapter profile.

Note that after you have created a network adapter profile, it cannot be updated.
To change a network adapter profile, you must remove the network adapter profile and then re-create it.

## EXAMPLES

### Example 1: Create a generic physical host network adapter profile by using DHCP
```
PS C:\>New-SCVMHostNetworkAdapterProfile -SetAsPhysicalNetworkAdapter -SetAsGenericNIC -UseDhcpForIPConfiguration -ConsistentDeviceName "Physical host network adapter profile 01"
```

This command creates a physical host network adapter profile.

The switches used in this command indicate that this is a physical network adapter and that the network adapter is not the management network adapter for the host.
Additionally, DHCP is used to obtain an IP address for the network adapter.

### Example 2: Create a physical network adapter profile with a logical switch
```
PS C:\>$LogSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> $UplinkPortProfSet = Get-SCUplinkPortProfileSet -Name "UplinkPortProfileSet01"
PS C:\> New-SCVMHostNetworkAdapterProfile -SetAsPhysicalNetworkAdapter -LogicalSwitch $LogSwitch -UplinkPortProfileSet $UplinkPortProfSet -ConsistentDeviceName "Physical host network adapter profile 02"
```

The first command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogSwitch variable.

The second command gets the uplink port profile set object named UplinkPortProfileSet01 and stores the object in the $UplinkPortProfSet variable.

The last command creates a physical host network adapter profile using LogicalSwitch01 and UplinkPortProfileSet01.

### Example 3: Create a management virtual host network adapter profile by using a static IP address
```
PS C:\>$TransMgmtNIC = Get-SCVMHostNetworkAdapterProfile -ID "259f47c7-c5a9-429d-a421-d232f9b34991"
PS C:\> $LogSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> $VMNetwork = Get-SCVMNetwork -Name "VMNetwork01"
PS C:\> New-SCVMHostNetworkAdapterProfile -SetAsVirtualNetworkAdapter -SetAsManagementNIC -TransientManagementNetworkAdapter $TransMgmtNIC -UseStaticIPForIPConfiguration -LogicalSwitch $LogSwitch -VMNetwork $VMNetwork
```

The first command gets the host network adapter profile object with the ID of 259f47c7-c5a9-429d-a421-d232f9b34991 and stores the object in the $TransMgmtNIC variable.

The second command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogSwitch variable.

The third command gets the VM network object named VMNetwork01 and stores the object in the $VMNetwork variable.

The last command creates a virtual host network adapter prfile as a management network adapter using LogicalSwitch01 and VMNetwork01.

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

### HostNetworkAdapterProfile
This cmdlet returns a **HostNetworkAdapterProfile** object.

## NOTES

## RELATED LINKS

[Get-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalSwitch.md)

[Get-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md)

[Get-SCVMHostNetworkAdapterProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHostNetworkAdapterProfile.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMNetwork.md)

[Remove-SCVMHostNetworkAdapterProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHostNetworkAdapterProfile.md)

