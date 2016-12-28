---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FB003E86-BDC9-445F-B95A-D742FBA84EC8
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCMACAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCMACAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCMACAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Grant-SCMACAddress

## SYNOPSIS
Allocates the next available physical address (MAC address) from a MAC address pool, and assigns it to a virtual network adapter.

## SYNTAX

```
Grant-SCMACAddress [-VMMServer <ServerConnection>] [-MACAddress <String>] -MACAddressPool <MACAddressPool>
 -VirtualNetworkAdapter <VirtualNetworkAdapter> [-Description <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-SCMACAddress** cmdlet allocates the next available physical address, specified as a Media Access Control (MAC) address from a MAC address pool and assigns it to a virtual network adapter.
To allocate a specific MAC address, use the *MACAddress* parameter.

For information about creating MAC address pools, type: `New-SCMACAddressPool -Detailed`.

## EXAMPLES

### Example 1: Allocate a MAC address from a MAC address Pool and assign it to a virtual network adapter
```
PS C:\> $VM = Get-SCVirtualMachine -VMHost "VMHost01.Contoso.com" -Name "VM01"
PS C:\> $VNIC = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $MACAddressPool = Get-SCMACAddressPool -VMHostGroup $HostGroup -Name "MAC Address Pool 01"
PS C:\> Grant-SCMACAddress -MACAddressPool $MACAddressPool -VirtualNetworkAdapter $VNIC
```

The first command gets the virtual machine object named VM01 on host VMHost01 and stores the object in the $VM variable.

The second command gets the virtual network adapter object for the virtual machine stored in $VM and stores the object in the $VNIC variable.
This example assumes that the virtual machine has only one virtual network adapter.

The third command gets the host group object at the path All Hosts\HostGroup02\Production and stores the object in the $HostGroup variable.

The fourth command gets the MAC address pool associated with the host group stored in $HostGroup and named MAC Address Pool 01.

The last command assigns a MAC address to the virtual network adapter stored in $VNIC.

### Example 2: Allocate a MAC address from a MAC address Pool and assign it to a specific virtual network adapter
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $VNIC = Get-SCVirtualNetworkAdapter -VM $VM | where {$_.SlotId -eq 1}
PS C:\> $MACAddressPool = Get-SCMACAddressPool -Name "MAC Address Pool 02"
PS C:\> Grant-SCMACAddress -MACAddressPool $MACAddressPool -VirtualNetworkAdapter $VNIC
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets the virtual network adapter object for VM02 with the slot ID of 1 and stores the object in the $VNIC variable.

The third command gets the MAC address Pool named MAC Address Pool 02 and stores the object in the the $MACAddressPool variable.

The last command grants a MAC address from MAC Address Pool 02 to the virtual network adapter stored in $VNIC.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the MAC address.

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

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -MACAddressPool
Specifies a MAC address pool.

```yaml
Type: MACAddressPool
Parameter Sets: (All)
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

### -VMMServer
Specifies a VMM (Virtual Machine Manager) server object.

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

### -VirtualNetworkAdapter
Specifies a virtual network adapter object for a virtual machine.

The maximum number of virtual network adapters varies by the type of host.
If the host type is Hyper-V, the maximum number of virtual network adapters is: 
- Up to four emulated adapters per virtual machine. 
- Up to eight synthetic adapters per virtual machine.
An exception is that no driver is available for an emulated network adapter on a Windows Server 2003 x64 guest.

If the host type is VMware ESX:
- Up to four emulated adapters per virtual machine.

If the host type is Citrix XenServer: 
- Up to seven emulated adapters per virtual machine.

```yaml
Type: VirtualNetworkAdapter
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CloudPairing[]
This cmdlet returns an array of **CloudPairing** objects.

## NOTES
* Requires a VMM MACAddressPool object, which can be retrieved using the **Get-SCMACAddressPool** cmdlet, and a VMM virtual network adapter object, which can be retrieved using the **Get-SCVirtualNetworkAdapter** cmdlet.

## RELATED LINKS

[Get-SCMACAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddress.md)

[Get-SCMACAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddressPool.md)

[Get-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapter.md)

[Revoke-SCMACAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCMACAddress.md)

