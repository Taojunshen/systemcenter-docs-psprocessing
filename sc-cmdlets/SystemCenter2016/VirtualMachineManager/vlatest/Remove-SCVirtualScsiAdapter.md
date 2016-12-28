---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8CA81940-5FF7-4519-A072-24717F6E0E0A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualScsiAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualScsiAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualScsiAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualScsiAdapter

## SYNOPSIS
Removes a virtual SCSI adapter object from VMM.

## SYNTAX

```
Remove-SCVirtualScsiAdapter [-VirtualScsiAdapter] <VirtualSCSIAdapter> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualScsiAdapter** cmdlet removes one or more virtual SCSI adapter objects from a virtual machine, virtual machine template, or hardware profile used in a Virtual Machine Manager (VMM) environment.

The **Remove-SCVirtualSCSIAdapter** cmdlet removes a virtual SCSI adapter successfully only if the adapter does not have any devices attached to it.

A virtual machine on a Citrix XenServer host always has one virtual SCSI adapter.
You cannot remove this adapter.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove the third virtual SCSI adapter from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $Adapter = Get-SCVirtualSCSIAdapter -VM $VM 
PS C:\> $Adapter[2] | Remove-SCVirtualScsiAdapter
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets all virtual SCSI adapter objects on VM01 and stores the objects in the $Adapter object array.
A virtual machine can have up to four virtual SCSI adapters attached.
This example assumes that VM01 has at least three virtual SCSI adapters.

The last command passes the third virtual SCSI adapter ($Adapter\[2\]) to **Remove-SCVirtualScsiAdapter**, which removes this virtual SCSI adapter from VM01.

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

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the **Get-SCUserRole** cmdlet.

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

### -VirtualScsiAdapter
Specifies a virtual SCSI adapter object for a virtual machine.

Type of Host       Number of Virtual SCSI Adapters

Hyper-V:                     Up to four synthetic virtual SCSI adapters per VM, and up to 64 devices per adapter.
Supports a virtual disk drive size up to 2040 GB.
Does not support emulated virtual SCSI adapters. 
VMware ESX:            Up to four virtual SCSI adapters per VM, and up to 15 devices per adapter.
Supports a virtual disk drive size up to 2048 GB. 
Citrix XenServer:    Always one virtual SCSI adapter per VM, and up to eight devices per adapter.
Supports a virtual disk drive size up to 2048 GB.

```yaml
Type: VirtualSCSIAdapter
Parameter Sets: (All)
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
* Requires a VMM virtual SCSI adapter object, which can be retrieved by using the **Get-SCVirtualScsiAdapter** cmdlet.

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualScsiAdapter.md)

[New-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualScsiAdapter.md)

[Set-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualScsiAdapter.md)

