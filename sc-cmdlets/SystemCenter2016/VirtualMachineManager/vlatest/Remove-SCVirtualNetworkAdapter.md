---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0A8395BF-CDB4-4E63-A19B-09F0D0190F88
updated_at: 12/22/2016 11:45 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/69b4a56d68a4e0923028e6be0f8a829d73f2d10b/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCVirtualNetworkAdapter

## SYNOPSIS
Removes a virtual network adapter object from VMM.

## SYNTAX

### VirtualNicSpecified
```
Remove-SCVirtualNetworkAdapter [-VirtualNetworkAdapter] <VirtualNetworkAdapter> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### SlotIdSpecified
```
Remove-SCVirtualNetworkAdapter -SlotID <Int32> -JobGroup <Guid> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualNetworkAdapter** cmdlet removes one or more virtual network adapter objects from a virtual machine, virtual machine template, or hardware profile used in a Virtual Machine Manager (VMM) environment.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to $True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a virtual network adapter with the specified MAC address from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $Adapter = Get-SCVirtualNetworkAdapter -VM $VM | where { $_.PhysicalAddress -eq "00:16:D3:CC:00:1B" }
PS C:\> Remove-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapter
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the virtual network adapter object on VM01 that has the specified MAC address and stores the object in the $Adapter variable.

The last command removes the virtual network adapter stored in $Adapter from VM01.

### Example 2: Remove a virtual network adapter connected to a specific virtual network from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $Adapter = Get-SCVirtualNetworkAdapter -VM $VM | where { $_.VirtualNetwork -eq "ExternalVirtualNetwork01" }
PS C:\> Remove-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapter
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets the virtual network adapter object on VM02 that is connected to the specified virtual network and stores the object in the $Adapter variable.

The last command removes the virtual network adapter object stored in $Adapter from VM02.

### Example 3: Remove the only virtual network adapter from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> $Adapter = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> Remove-SCVirtualNetworkAdapter -VirtualNetworkAdapter $Adapter
```

The first command gets the virtual machine object named VM03 and stores the object in the $VM variable.

The second command gets the virtual network adapter object on VM03 and stores the object in the $Adapter variable.
This example assumes that VM03 has only one virtual network adapter.

The last command removes the virtual network adapter object stored in $Adapter from VM03.

### Example 4: Remove all virtual network adapters from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM04"
PS C:\> $Adapters = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> $Adapters | Remove-SCVirtualNetworkAdapter
```

The first command gets the virtual machine object named VM04 and stores the object in the $VM variable.

The second command gets all virtual network adapter objects on VM04 and stores the objects in the $Adapters object array.

The last command passes each object stored in $Adapters to **Remove-SCVirtualNetworkAdapter**, which removes each virtual network adapter object from VM04.

### Example 5: Remove the second virtual network adapter from a virtual machine that has three virtual network adapters
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM05"
PS C:\> $Adapters = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> $Adapters[1] | Remove-SCVirtualNetworkAdapter
```

The first command gets the virtual machine object named VM05 and stores the object in the $VM variable.

The second command gets all virtual network adapter objects on VM05 and stores the objects in the $Adapters object array.
This example assumes that VM05 has three virtual network adapters.

The last command passes the second virtual network adapter object ($Adapters \[1\]) to the **Remove-SCVirtualNetworkAdapter** cmdlet, which removes this virtual network adapter object from VM05.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: VirtualNicSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: SlotIdSpecified
Aliases: 

Required: True
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -SlotID
Specifies a numerical ID used to identify a device.

```yaml
Type: Int32
Parameter Sets: SlotIdSpecified
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapter
Specifies a virtual network adapter object for a virtual machine.

Types of hosts support the following number of virtual network adapters: 

- Hyper-V. 
Up to four emulated adapters per virtual machine.
There is no driver available for an emulated network adapter on a Windows Server 2003 x64 guest operating system.
- Hyper-V. 
Up to eight synthetic adapters per virtual machine.
- VMware ESX. 
Up to four emulated adapters per virtual machine.
- Citrix XenServer. 
Up to seven emulated adapters per virtual machine.

```yaml
Type: VirtualNetworkAdapter
Parameter Sets: VirtualNicSpecified
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## NOTES
* Requires a VMM virtual network adapter object, which can be retrieved by using the **Get-SCVirtualNetworkAdapter** cmdlet.

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapter.md)

[New-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapter.md)

[Repair-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetworkAdapter.md)

[Set-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapter.md)

