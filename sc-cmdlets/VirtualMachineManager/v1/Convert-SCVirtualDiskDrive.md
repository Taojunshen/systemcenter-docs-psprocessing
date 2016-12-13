---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: E9185938-C626-466B-B146-2CDF9866ECEC
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Convert-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Convert-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Convert-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Convert-SCVirtualDiskDrive

## SYNOPSIS
Converts a virtual hard disk from dynamic to fixed, from fixed to dynamic, from VHD to VHDX, or converts a pass-through disk to a virtual hard disk.

## SYNTAX

### Fixed
```
Convert-SCVirtualDiskDrive [-Fixed] [-VirtualDiskDrive] <VirtualDiskDrive> [-Path <String>]
 [-FileName <String>] [-VHDFormatType <VHDFormatType>] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Dynamic
```
Convert-SCVirtualDiskDrive [-Dynamic] [-VirtualDiskDrive] <VirtualDiskDrive> [-Path <String>]
 [-FileName <String>] [-VHDFormatType <VHDFormatType>] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VHDX
```
Convert-SCVirtualDiskDrive [-VHDX] [-DeleteSource] [-ValidateOnCompletion]
 [-VirtualDiskDrive] <VirtualDiskDrive> [-Path <String>] [-FileName <String>] [-JobGroup <Guid>]
 [-BlockSizeBytes <Int32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Convert-SCVirtualDiskDrive** cmdlet converts an existing virtual hard disk attached to a virtual disk drive object from dynamic to fixed or from fixed to dynamic, from VHD to VHDX, or converts a pass-through disk attached to a virtual disk drive object to a virtual hard disk.

To convert the virtual hard disk from one format to the other, the virtual machine on which the virtual hard disk is configured must be in a stopped state.

You can only convert the disk format of a Windows-based .vhd file on a virtual machine deployed on a Hyper-V host.

A VMware-based .vmdk file) on a virtual machine that is deployed on an ESX host is fixed in format.
You cannot convert it to a dynamic format.

A Citrix XenServer-based .vhd file on a virtual machine that is deployed on a Citrix XenServer host is fixed in format.
You cannot convert it to a dynamic format.

You can only convert the disk format of a Windows-based virtual hard disk file from VHD to VHDX on a virtual machine that is deployed on a Hyper-V host.
To convert a VHD to VHDX, the virtual machine on which the virtual hard disk is configured must be in a stopped state.

A pass-through disk is a physical hard disk on the host that a virtual machine can use instead of using a virtual hard disk.
This cmdlet converts a pass-through disk attached to a virtual disk drive on a virtual machine to a virtual hard disk.
The virtual machine must be on a Hyper-V host, and must be in a stopped state.

## EXAMPLES

### Example 1: Convert a pass-through disk on a virtual machine to a virtual hard disk
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VirtDiskDrive = Get-SCVirtualDiskDrive -VM $VM
PS C:\> Convert-VirtualDiskDrive $VirtDiskDrive -Fixed -Path "C:\VirtualDiskDrives"
```

The first command gets the virtual machine object named VM01 by using the Get-SCVirtualMachine cmdlet.
The command stores that object in the $VM variable.
This example assumes that VM01 is currently configured to use a pass-through disk and that the virtual machine has only one pass-through disk.

The second command gets the virtual disk drive object on VM01, and then stores that object in the $VirtDiskDrive variable.

The last command converts the pass-through disk drive stored in $VirtDiskDrive to a fixed virtual hard disk.
The command moves the virtual hard disk to the destination folder C:\VirtualDiskDrives.

### Example 2: Convert one of several pass-through disks on a virtual disk drive on a virtual machine to a virtual hard disk
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $VirtDiskDrive = Get-SCVirtualDiskDrive -VM $VM
PS C:\> $VirtDiskDrive[2] | Convert-SCVirtualDiskDrive -Dynamic -Path "D:\"
```

The first command gets the virtual machine object named VM02, and then stores that object in the $VM variable.
This example assumes that VM02 has three virtual disk drive objects and that the first virtual disk drive is bound to a virtual hard disk drive whereas both the second and third virtual disk drives are bound to pass-through disks.

The second command gets all virtual disk drive objects on VM02, and then stores those objects in the $VirtDiskDrive object array.

The last command converts the third pass-through disk, which is the third member of the $VirtDiskDrive array, to a dynamically expanding virtual hard disk.
The commandmoves this new virtual hard disk to the destination folder D:\.

### Example 3: Convert a dynamic VHD attached to a virtual disk drive object on a virtual machine to a fixed format
```
PS C:\>$VirtDiskDrive = Get-SCVirtualDiskDrive -VM (Get-SCVirtualMachine -Name "VM03")
PS C:\> Convert-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive -Fixed
```

The first command gets the virtual disk drive object that is attached to virtual machine VM03, and then stores that virtual disk drive object in the $VirtDiskDrive variable.
This example assumes that the virtual machine has only one virtual disk drive object and that the virtual hard disk attached to the virtual disk drive is a dynamic virtual hard disk.

The second command converts the virtual hard disk stored in $VirtDiskDrive to a fixed disk.

### Example 4: Convert a dynamic VHD on a virtual machine to fixed VHDX
```
PS C:\>$VirtDiskDrive = Get-SCVirtualDiskDrive -VM (Get-SCVirtualMachine -Name "VM03")
PS C:\> Convert-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive -VHDX
```

The first command gets the virtual disk drive object that is attached to virtual machine VM03, and stores that object in the $VirtDiskDrive variable.
This example assumes that the virtual machine has only one virtual disk drive object and that the virtual hard disk attached to the virtual disk drive is a dynamic virtual hard disk.
This example also assumes that the virtual machine is in a stopped state.

The second command converts the virtual hard disk stored in $VirtDiskDrive to a VHDX disk.

### Example 5: Convert a differencing VHD to a differencing VHDX
```
PS C:\>$VirtDiskDrive = Get-VirtualDiskDrive -VM (Get-SCVirtualMachine -Name "VM04")
PS C:\> Convert-VirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive -VHDX -BlockSizeBytes 1MB -DeleteSource -ValidateOnCompletion
```

The first command gets the virtual disk drive object that is attached to virtual machine VM04, and then stores that object in the $VirtDiskDrive variable.
This example assumes that the virtual machine has only one virtual disk drive object and that the virtual hard disk attached to the virtual disk drive is a dynamic virtual hard disk.
This example also assumes that the virtual machine is in a stopped state.

The second command converts the differencing virtual hard disk stored in $VirtDiskDrive to a differencing VHDX disk.
This command deletes the source disk.

## PARAMETERS

### -BlockSizeBytes
Specifies the block size, in bytes, for the virtual hard disk.

```yaml
Type: Int32
Parameter Sets: VHDX
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteSource
Indicates that this cmdlet deletes the source virtual hard disk after a successful conversion.

```yaml
Type: SwitchParameter
Parameter Sets: VHDX
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dynamic
Specifies that a virtual hard disk can expand dynamically.

```yaml
Type: SwitchParameter
Parameter Sets: Dynamic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName
Specifies the file name to use when you rename a virtual hard disk file as you add it to a virtual machine.

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

### -Fixed
Indicates that a virtual hard disk is fixed in size.
Specifies that a virtual hard disk is fixed in size.

```yaml
Type: SwitchParameter
Parameter Sets: Fixed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Path
Specifies the logical unit number (LUN) for a virtual disk drive object or for a virtual disk drive object on a SCSI bus.

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

### -VHDFormatType
Specifies the hard disk format type.
Valid values are:

- VHD
- VMDK
- VHDX

```yaml
Type: VHDFormatType
Parameter Sets: Fixed, Dynamic
Aliases: 
Accepted values: VHD, VMDK, VHDX, VHDS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDX
Indicates that a virtual hard disk type is VHDX.

```yaml
Type: SwitchParameter
Parameter Sets: VHDX
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidateOnCompletion
Indicates that this cmdlet validates the converted virtual hard disk after a successful conversion.

```yaml
Type: SwitchParameter
Parameter Sets: VHDX
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

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Compress-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[New-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Remove-SCVirtualDiskDrive.md)

[Set-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Set-SCVirtualDiskDrive.md)

[Test-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Test-SCVirtualDiskDrive.md)

