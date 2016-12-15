---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: B2307B94-CCD9-49DA-AA4A-D901B8BD42D8
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Expand-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Expand-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Expand-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Expand-SCVirtualDiskDrive

## SYNOPSIS
Expands a virtual hard disk attached to a virtual disk drive object.

## SYNTAX

```
Expand-SCVirtualDiskDrive [-VirtualDiskDrive] <VirtualDiskDrive> -VirtualHardDiskSizeGB <Int32>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Expand-SCVirtualDiskDrive** cmdlet expands a virtual hard disk attached to a virtual disk drive object in order to increase the total capacity of the virtual hard disk.
The virtual machine must be deployed on a host managed by Virtual Machine Manager (VMM) and must be in a stopped state before you can expand the virtual hard disk.

This cmdlet expands a Windows-based.vhd or .vhdx file attached to a virtual disk drive object on a virtual machine deployed on a Hyper-V host.
You can also use this cmdlet to expand a VMware-based a .vmdk file on a virtual machine deployed on an ESX host.
You cannot use this cmdlet to expand a virtual hard disk on a virtual machine deployed on a Citrix XenServer host.

## EXAMPLES

### Example 1: Expand a virtual hard disk
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VirtDiskDrive = Get-SCVirtualDiskDrive -VM $VM | Where-Object {$_.Bus -Eq 0 -And $_.Lun -Eq 0}
PS C:\> Expand-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive -VirtualHardDiskSizeGB 40
```

The first command gets the virtual machine object named VM01 by using the Get-SCVirtualMachine cmdlet.
The command stores that object in the $VM variable.

The second command gets the virtual disk drive object located on the first controller ($_.Bus -Eq 0) and first slot of that controller ($_.Lun -Eq 0) of VM01, and stores that object in the $VirtDiskDrive variable.

The last command expands the size of the virtual hard disk attached to the virtual disk drive to 40 GB.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

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
Specify this parameter and the *OnBehalfOfUser* parameter to remove permissions from a user role that belongs to an on behalf of user.
To obtain a user role object, use the Get-SCUserRole cmdlet.

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

### -VirtualDiskDrive
Specifies a virtual disk drive object.
You can attach either a virtual hard disk or a pass-through disk to a virtual disk drive object.

```yaml
Type: VirtualDiskDrive
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHardDiskSizeGB
Specifies the size, in gigabytes (GB), to which a dynamically expanding virtual hard disk expands.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Size

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

### VirtualHardDisk
This cmdlet returns a **VirtualHardDisk** object.

## NOTES
* This cmdlet requires a VMM virtual disk drive object, which can be retrieved by using the Get-SCVirtualDiskDrive cmdlet.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Convert-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDiskDrive.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDiskDrive.md)

[Test-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVirtualDiskDrive.md)

