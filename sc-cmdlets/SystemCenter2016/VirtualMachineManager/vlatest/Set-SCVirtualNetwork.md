---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3E836105-1385-4898-86C2-DCD4CA0142D2
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVirtualNetwork

## SYNOPSIS
Changes the properties of a virtual network configured on a host managed by VMM.

## SYNTAX

### Host (Default)
```
Set-SCVirtualNetwork -VirtualNetwork <VirtualNetwork> [-Name <String>] [-Description <String>]
 [-BoundToVMHost <Boolean>] [-HostBoundVLanId <UInt16>] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### StandardSwitchToLogicalSwitch
```
Set-SCVirtualNetwork -VirtualNetwork <VirtualNetwork> -LogicalSwitch <LogicalSwitch> [-Description <String>]
 [-JobGroup <Guid>] [-ConvertToLogicalSwitch] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### LogicalSwitch
```
Set-SCVirtualNetwork -VirtualNetwork <VirtualNetwork> -LogicalSwitch <LogicalSwitch>
 [-VMHostNetworkAdapters <HostNetworkAdapter[]>] [-Description <String>] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Cluster
```
Set-SCVirtualNetwork [-ClusterVirtualNetwork] <ClusterVirtualNetwork> [-Name <String>] [-Description <String>]
 [-BoundToVMHost <Boolean>] [-HostBoundVLanId <UInt16>] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualNetwork** cmdlet changes the properties of a virtual network configured on a host managed by Virtual Machine Manager (VMM).

Virtual network properties that you can change include: 

- Any Host. 
For a virtual network configured for virtual machines deployed on any host supported by VMM (a Hyper-V, VMware ESX, or Citrix XenServer host), you can set or modify the name or description. 

- Hyper-V Host Only.
If the host is a Hyper-V host, you can also  configure whether virtual machines are bound to the host (and can  thus access the host operating system), and you can specify a  numerical identifier for a virtual local area network (VLAN) on the host.

## EXAMPLES

### Example 1: Unbind a virtual network from a host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $VirtualNetwork = Get-SCVirtualNetwork -VMHost $VMHost -Name "InternalVNet01"
PS C:\> Set-SCVirtualNetwork -VirtualNetwork $VirtualNetwork -Name "UnboundVNet01" -BoundToVMHost $False
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the virtual network object named InternalVNet01 from VMHost01 and stores the object in the $VirtualNetwork variable.

The last command renames the virtual network to UnboundVNet01 and sets *VMHostBound* to $False.
This unbinds the virtual network from the host, which prevents any virtual machines that are attached to this virtual network from accessing the host through this network.

## PARAMETERS

### -BoundToVMHost
Indicates whether a virtual network is bound to a host.
Binding a virtual network to a host enables network communication to the host.

```yaml
Type: Boolean
Parameter Sets: Host, Cluster
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterVirtualNetwork
Specifies a cluster virtual network object.

```yaml
Type: ClusterVirtualNetwork
Parameter Sets: Cluster
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ConvertToLogicalSwitch
Indicates that this cmdlet converts the virtual network to a logical switch.

```yaml
Type: SwitchParameter
Parameter Sets: StandardSwitchToLogicalSwitch
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
Parameter Sets: Host, Cluster
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

### -LogicalSwitch
Specifies a logical switch object.

```yaml
Type: LogicalSwitch
Parameter Sets: StandardSwitchToLogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: LogicalSwitch
Parameter Sets: LogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: Host, Cluster
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

### -VMHostNetworkAdapters
Specifies an array of one or more physical network adapter objects on a host to which virtual machines deployed on that host can connect.

Example format: `-VMHostNetworkAdapters $VMHostNICs`

```yaml
Type: HostNetworkAdapter[]
Parameter Sets: LogicalSwitch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network object.

```yaml
Type: VirtualNetwork
Parameter Sets: Host, LogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: VirtualNetwork
Parameter Sets: StandardSwitchToLogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[New-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetwork.md)

[Remove-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetwork.md)

[Repair-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetwork.md)

