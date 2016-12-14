---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Convert-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: 7A0A8252-8547-4612-AF46-DC46684DE80F
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Compress-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Compress-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Compress-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Compress-SCVirtualDiskDrive

## SYNOPSIS
Compresses a dynamically expanding virtual hard.

## SYNTAX

```
Compress-SCVirtualDiskDrive [-VirtualDiskDrive] <VirtualDiskDrive> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Compress-SCVirtualDiskDrive** cmdlet compresses a dynamically expanding virtual hard disk attached to a virtual disk drive object to reduce the size of the virtual hard disk.
The virtual machine must be stopped before you can compress the virtual hard disk.

This cmdlet compresses a Windows-based virtual hard disk file attached to a virtual disk drive object on a virtual machine that is deployed on a Hyper-V host.
Virtual hard disks are .vhd or .vhdx files.

A VMware-based.vmdk file on a virtual machine deployed on an ESX Server 3.0 or 3.5 host is not dynamic.
You cannot compress a fixed virtual hard disk.

A Citrix XenServer-based.vhd file on a virtual machine deployed on a XenServer host is not dynamic.
You cannot compress a fixed disk.

## EXAMPLES

### Example 1: Compress a virtual hard disk on a virtual machine deployed on a host
```
PS C:\>$VirtDiskDrive = Get-SCVirtualDiskDrive -VM (Get-SCVirtualMachine -Name "VM01")
PS C:\> Compress-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive
```

The first command gets the virtual disk drive object attached to VM01, and then stores that object in the $VDD variable.
This example assumes the virtual machine has only one virtual disk drive and that the virtual hard disk attached to the virtual disk drive is, a dynamic virtual hard disk.

The second command compresses the dynamically expanding virtual hard disk that is attached to the virtual disk drive on VM01.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualDiskDrive
This cmdlet returns a **VirtualDiskDrive** object.

## NOTES
* This cmdlet requires a VMM virtual disk drive object that is currently associated with a virtual machine deployed on a host, which can be retrieved by using the Get-SCVirtualDiskDrive cmdlet.

## RELATED LINKS

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualDiskDrive.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVirtualDiskDrive.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVirtualDiskDrive.md)

[Test-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Test-SCVirtualDiskDrive.md)
