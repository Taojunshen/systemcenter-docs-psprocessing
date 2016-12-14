---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: 89D54069-4597-4B75-8335-DE5514DAE4E8
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualFloppyDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualFloppyDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualFloppyDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualFloppyDrive

## SYNOPSIS
Gets a VMM virtual floppy drive objects from a virtual machine, a virtual machine template, or a hardware profile.

## SYNTAX

### All
```
Get-SCVirtualFloppyDrive [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### HardwareProfile
```
Get-SCVirtualFloppyDrive -HardwareProfile <HardwareProfile> [<CommonParameters>]
```

### VM
```
Get-SCVirtualFloppyDrive -VM <VM> [<CommonParameters>]
```

### Template
```
Get-SCVirtualFloppyDrive -VMTemplate <Template> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualFloppyDrive** cmdlet gets one or more virtual floppy drive objects in a Virtual Machine Manager (VMM) environment from a virtual machine object, a virtual machine template object, or a hardware profile object.

In VMM, each virtual machine, virtual machine template, or hardware profile has one floppy drive.
You cannot remove this floppy drive or add any additional floppy drives.

By default, the virtual floppy drive is configured as attached to no media.
To configure the virtual floppy drive to use the physical floppy drive on the virtual machine host (typically, drive A:) use the Set-SCVirtualFloppyDrive cmdlet.
Alternatively, you can configure the virtual floppy drive to read an existing virtual floppy disk.

## EXAMPLES

### Example 1: Get the virtual floppy drive from a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Get-SCVirtualFloppyDrive -VM $VM
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the virtual floppy drive object on VM01 and displays information about this drive to the user.

### Example 2: Get the virtual floppy drive from a virtual machine template
```
PS C:\>$VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> Get-SCVirtualFloppyDrive -VMTemplate $VMTemplate
```

The first command gets the virtual machine template object named VMTemplate01 and stores the object in the $VMTemplate variable.

The second command gets the virtual floppy drive object on VMTemplate01 and displays information about the drive to the user.

### Example 3: Get the virtual floppy drive from a hardware profile
```
PS C:\>$HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> Get-SCVirtualFloppyDrive -HardwareProfile $HWProfile
```

The first command gets the hardware profile named NewHWProfile01 and stores the object in the $HWProfile variable.

The second command gets the virtual floppy drive object on NewHWProfile01 and displays information about the drive to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
Aliases: Template

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

### VirtualFloppyDrive
This cmdlet returns a **VirtualFloppyDrive** object.

## NOTES
* Requires a virtual machine object, virtual machine template object, or hardware profile object, which can be retrieved by using the Get-SCVirtualMachine, Get-SCVMTemplate, or Get-SCHardwareProfile cmdlets, respectively.

## RELATED LINKS

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCHardwareProfile.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMTemplate.md)

[Set-SCVirtualFloppyDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVirtualFloppyDrive.md)

