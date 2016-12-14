---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHostNetworkAdapter.md
schema: 2.0.0
ms.assetid: A0F6131F-C2B4-43BF-B605-977BB823E668
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMHostNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMHostNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMHostNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMHostNetworkAdapter

## SYNOPSIS
Changes network-related properties for a physical network adapter on a host managed by VMM.

## SYNTAX

### LogicalNetwork (Default)
```
Set-SCVMHostNetworkAdapter [-VMHostNetworkAdapter] <HostNetworkAdapter> [-Description <String>]
 [-VLanMode <VlanMode>] [-AvailableForPlacement <Boolean>] [-UsedForManagement <Boolean>]
 [-SubnetVLan <SubnetVLan[]>] [-RemoveUnassignedVLan <UInt16[]>] [-AddOrSetLogicalNetwork <LogicalNetwork>]
 [-RemoveLogicalNetwork <LogicalNetwork>] [-EnableNetworkVirtualization <Boolean>]
 [-UplinkPortProfileSet <UplinkPortProfileSet>] [-RemoveUplinkPortProfileSet] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Manual
```
Set-SCVMHostNetworkAdapter [-VMHostNetworkAdapter] <HostNetworkAdapter> [-Description <String>]
 [-VLanEnabled <Boolean>] [-VLanMode <VlanMode>] [-VLanID <UInt16>] [-VLanTrunkID <UInt16[]>]
 [-AvailableForPlacement <Boolean>] [-UsedForManagement <Boolean>] [-RemoveUnassignedVLan <UInt16[]>]
 [-EnableNetworkVirtualization <Boolean>] [-UplinkPortProfileSet <UplinkPortProfileSet>]
 [-RemoveUplinkPortProfileSet] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMHostNetworkAdapter** cmdlet changes network-related properties for a physical network adapter on a host managed by Virtual Machine Manager (VMM).

Properties that you can change with this cmdlet include: 

* VLAN settings: You can use the VLAN parameters to create or modify a single VLAN or multiple VLANs.
For an illustration of how to specify VLAN settings, see the examples.

For more information about VLANs and additional examples that illustrate VLAN settings, type `Get-Help Add-SCVMHostNetworkAdapter -Detailed`.

## EXAMPLES

### Example 1: Create a new virtual network on a host network adapter and specify a VLAN ID for the virtual network
```
PS C:\>$VMHost = Get-SCVMHost -Computername "VMHost02.Contoso.com"
PS C:\> $HostAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost |  where {$_.Name -like "Intel(R) PRO/1000*" }
PS C:\> New-SCVirtualNetwork -Name "VirtualNetwork01" -VMHost $VMHost -VMHostNetworkAdapter $HostAdapter
PS C:\> Set-SCVMHostNetworkAdapter -VMHostNetworkAdapter $HostAdapter -VLanEnabled $True -VLanMode "Access" -VLANID 35
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command gets the host network adapter object with a name that begins with "Intel(R) PRO/1000 on VMHost02 and stores the object in the $HostAdapter variable.

The third command creates a virtual network named VirtualNetwork01 on VMHost02 that is bound to the host adapter stored in $HostAdapter.

The last command enables a VLAN, sets the mode to Access (which routes traffic internally within a single VLAN), and assigns the network adapter a VLANID of 35.

Note: This example assumes that that your host is already connected to a VLAN or, if not, that your host has two network adapters.
If your host has a single network adapter, assigning the adapter to a VLAN that is unavailable to the VMM server will prevent VMM from managing the host.

### Example 2: Add VLan tags to a host network adapter configured in Trunk mode
```
PS C:\>$VMHost = Get-SCVMHost -Computername "VMHost03.Contoso.com"
PS C:\> $VMHostNIC = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "Adapter #3"
PS C:\> $NewVlanTags = $VMHostNIC.VlanTags + @(177,355,1012)
PS C:\> Set-SCVMHostNetworkAdapter -VMHostNetworkAdapter $VMHostNIC -VLANEnabled $TRUE -VLanMode "Trunk" -VLanTrunkID $NewVLanTags
```

The first command gets the host object named VMHost03 and stores the object in the $VMHost variable.

The second command gets the host network adapter object by specifying the adapter name and stores the object in the $VMHostNIC variable.

The third command uses the VlanTags property of the host network adapter object ($VMHostNIC.VlanTags) and concatenates a new array of tags.
The updated array retains the exisiting VlanTags and adds the listed tags to the array.
The result of the concatenation is stored in $NewVlanTags.

The last command passes the new list of VLAN tags to the *VLANTrunkID* parameter of **Set-VMHostNetworkAdapter**.
The *VLANMode* parameter must specify the value "Trunk" whenever the *VLANTrunkID* parameter is used to modify the list of VLAN trunk numerical identifiers.

## PARAMETERS

### -AddOrSetLogicalNetwork
Specifies a logical network that will be added or updated.

```yaml
Type: LogicalNetwork
Parameter Sets: LogicalNetwork
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AvailableForPlacement
Indicates whether the VMM placement process considers this host or this volume on a host to be eligible as a possible location on which to deploy virtual machines.
If this parameter is set to $False, you can choose to deploy virtual machines on this host or volume anyway.
The default value is $True.
This parameter does not apply to VMware ESX hosts.

When this parameter is used with network adapters, if set to $False, then placement will not consider the logical networks configured on this network adapter to determine if the host is suitable for connecting a virtual machine.

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

### -Description
States a description for the specified object.

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

### -EnableNetworkVirtualization
Specifies whether network virtualization is enabled.
The default value is $False.

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

### -RemoveLogicalNetwork
Specifies a logical network that will be removed.

```yaml
Type: LogicalNetwork
Parameter Sets: LogicalNetwork
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveUnassignedVLan
Specifies that the specified VLANs will be removed from the VLAN trunk of the adapter if they are not associated with a logical network.

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

### -RemoveUplinkPortProfileSet
Removes the uplink port profile set from the host network adapter.

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

### -SubnetVLan
Specifies one or more IP subnet and VLAN sets.

For information about creating a SubnetVLan, type `Get-Help New-SCSubNetVLan`.

```yaml
Type: SubnetVLan[]
Parameter Sets: LogicalNetwork
Aliases: 

Required: False
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsedForManagement
Indicates whether the object is used to manage hosts.

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

### -VLanEnabled
Enables a virtual LAN (VLAN) for use by virtual machines on a Hyper-V or Citrix XenServer host. 


Example format for a single VLAN: `-VLANEnabled -VLANMode "Access" -VLANID 35`

Example format for multiple VLANs: `-VLANEnabled -VLANMode "Trunk" -VLANTrunkID 1,2,100,200,1124`

```yaml
Type: Boolean
Parameter Sets: Manual
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


 -- Bound to a physical network adapter on the host, or

 -- Bound to an internal virtual network on the host. 



Example format: `-VLanEnabled -VLanMode "Access" -VLANID 35`

```yaml
Type: UInt16
Parameter Sets: Manual
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
Parameter Sets: Manual
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMHostNetworkAdapter
This cmdlet returns a **VMHostNetworkAdapter** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCVMHostNetworkAdapter.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHost.md)

[Get-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHostNetworkAdapter.md)

[New-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVirtualNetwork.md)

[Remove-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVMHostNetworkAdapter.md)

