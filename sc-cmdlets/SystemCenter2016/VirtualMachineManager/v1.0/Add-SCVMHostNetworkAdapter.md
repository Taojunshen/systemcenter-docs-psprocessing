---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualNetwork.md
schema: 2.0.0
ms.assetid: DCEB6A2A-7EF5-4573-8F8F-0AB5E44419F9
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Add-SCVMHostNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Add-SCVMHostNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Add-SCVMHostNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCVMHostNetworkAdapter

## SYNOPSIS
Adds a physical network adapter on a host managed by VMM to a virtual network.

## SYNTAX

```
Add-SCVMHostNetworkAdapter -VirtualNetwork <VirtualNetwork> [-VLanEnabled] [-VLanMode <VlanMode>]
 [-VLanID <UInt16>] [-VLanTrunkID <UInt16[]>] [-VMHostNetworkAdapter] <HostNetworkAdapter> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVMHostNetworkAdapter** cmdlet adds a physical network adapter (also called a network interface card, or NIC) on a host managed by Virtual Machine Manager (VMM) to a virtual network.
Each virtual machine on that host can also connect through a virtual network adapter to that virtual network.

A virtual network configured on a host can connect to multiple virtual network adapters on virtual machines deployed on that host.

VMM for System Center 2016 includes virtual networking support for configuring one or more Virtual Local Area Networks (VLANs) on a host.
You can use the Add-SCVMHostNetworkAdapter cmdlet or the Set-SCVMHostNetworkAdapter cmdlet to configure a single VLAN or multiple VLANs on a host.
To configure corresponding VLAN settings on a virtual machine, use the New-SCVirtualNetworkAdapter cmdlet or the Set-SCVirtualNetworkAdapter cmdlet.

For an illustration of each type of VLAN, see the examples for this cmdlet.

## EXAMPLES

### Example 1: Add a physical host network adapter to a virtual network
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> $VirtualNetwork = Get-SCVirtualNetwork -VMHost $VMHost -Name "ExternalVirtualNetwork01"
PS C:\> $VMHostNetworkAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "HostAdapter01"
PS C:\> Add-SCVMHostNetworkAdapter -VirtualNetwork $VirtualNetwork -VMHostNetworkAdapter $VMHostNetworkAdapter
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the virtual network object named ExternalVirtualNetwork01 on VMHost01 and stores the object in the $VirtualNetwork variable.

The third command gets the physical network adapter object named HostAdapter01 on VMHost01 and stores the object in the $VMHostNetworkAdapter variable.

The last command adds HostAdapter01 to ExternalVirtualNetwork01.

Note: You can add only one physical host adapter per virtual network.
Therefore, the last command will fail if an adapter is already associated with the specified virtual network.
To add a new adapter to the virtual network, you must first remove the existing host adapter.

### Example 2: Add a physical host network adapter to a VLAN that uses "Trunk" mode
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost02"
PS C:\> $VirtualNetwork = Get-SCVirtualNetwork -VMHost $VMHost -Name "ExternalNetwork02"
PS C:\> $VMHostNetworkAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "HostAdapter02"
PS C:\> Add-SCVMHostNetworkAdapter -VirtualNetwork $VirtualNetwork -VMHostNetworkAdapter $VMHostNetworkAdapter -VLANEnabled -VLANMode "Trunk" -VLANTrunkID 1,2,100,200,1124
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command gets the virtual network object named ExternalNetwork02 on VMHost02 and stores the object in the $VirtualNetwork variable.

The third command gets the network adapter object named HostAdapter02 on VMHost02 and stores the adapter object in the $VMHostNetworkAdapter variable.

The last command adds HostAdapter02 to virtual network ExternalNetwork02 and enables access from ExternalNetwork02 to an external networking device using 802.1Q tagged VLANs 1, 2, 100, 200, and 1124.

Note: You can add only one host adapter per virtual network, so the last command will fail if an adapter is already associated with the specified virtual network.

### Example 3: Add a physical host network adapter to a VLAN that uses "Access" mode
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost03.Contoso.com"
PS C:\> $VirtualNetwork = Get-SCVirtualNetwork -VMHost $VMHost -Name "ExternalVirtualNetwork03"
PS C:\> $VMHostNetworkAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "HostAdapter03"
PS C:\> Add-SCVMHostNetworkAdapter -VirtualNetwork $VirtualNetwork -VMHostNetworkAdapter $VMHostNetworkAdapter -VLanEnabled -VLanMode "Access" -VLanID 22
```

The first command gets the host object named VMHost03 and stores the object in the $VMHost variable.

The second command gets the virtual network object named ExternalNetwork03 on VMHost03 and stores the object in the $VirtualNetwork variable.

The third command gets the network adapter object named HostAdapter03 on VMHost03 and stores the adapter object in the$VMHostNetworkAdapter variable.

The last command adds HostAdapter03 to virtual network ExternalNetwork03 and restricts access to ExternalNetwork03 to VLANID 22.

Note: You can add only one host adapter per virtual network, so the last command will fail if an adapter is already associated with the specified virtual network.

Caution: This example assumes that that your host is already connected to a VLAN or, if not, ensure that your host has two network adapters.
If your host has a single network adapter, assigning the adapter to a VLAN that is unavailable to the VMM server will prevent VMM from managing the host.
You can perform the steps in this example on a host that has only one network adapter if you first install the Microsoft Loopback Adapter on your server.

## PARAMETERS

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

### -VLanEnabled
Enables a virtual LAN (VLAN) for use by virtual machines on a Hyper-V or Citrix XenServer host. 

Example format for a single VLAN: `-VLANEnabled -VLANMode "Access" -VLANID 35`
Example format for multiple VLANs: `-VLANEnabled -VLANMode "Trunk"  -VLANTrunkID 1,2,100,200,1124`

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

### -VLanID
Assigns a numerical identifier in the range 1-4094 to a virtual network adapter on a virtual machine or to a physical network adapter on a virtual machine host. 

Configure a VLanID on a Hyper-V, VMware ESX, or Citrix XenServer host: 

 -- On an externally bound physical network adapter when the VLan mode is Access.

Configure a VLanID on a virtual network adapter of a virtual machine: 

- Bound to a physical network adapter on the host, or
- Bound to an internal virtual network on the host.

Example format:  `-VLanEnabled``-VLanMode "Access" -VLANID 35`

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

### -VLanMode
Specifies whether a virtual LAN (VLAN) on a virtual machine host supports traffic across a single VLAN (Access mode) or across multiple VLANs (Trunk mode).
Valid values are: Access, Trunk.

```yaml
Type: VlanMode
Parameter Sets: (All)
Aliases: 
Accepted values: Access, Trunk, Invalid

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VLanTrunkID
Assigns a list of numerical identifiers in the range 1-4094 to a physical network adapter on a Hyper-V host. 

Example format: `-VLANEnabled -VLANMode "Trunk" -VLANTrunkID 1,2,100,200,1124`

```yaml
Type: UInt16[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostNetworkAdapter
Specifies a physical network adapter object on a host to which virtual machines deployed on that host can connect. 

Example format: `-VMHostNetworkAdapter $VMHostNIC`

```yaml
Type: HostNetworkAdapter
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network object.

```yaml
Type: VirtualNetwork
Parameter Sets: (All)
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

### VMHostNetworkAdapter
This cmdlet returns a **VMHostNetworkAdapter** object.

## NOTES

## RELATED LINKS

[Get-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualNetwork.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHost.md)

[Get-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHostNetworkAdapter.md)

[Remove-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVMHostNetworkAdapter.md)

[Set-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMHostNetworkAdapter.md)

