---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: ECEFE03C-2E5D-403B-8C2E-2C79D271A50F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCVirtualDiskDrive

## SYNOPSIS
Tests an existing virtual hard disk.

## SYNTAX

```
Test-SCVirtualDiskDrive [-VirtualDiskDrive] <VirtualDiskDrive> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCVirtualDiskDrive** cmdlet tests an existing virtual hard disk that is attached to a virtual disk drive object.

To test a virtual hard disk, the virtual machine on which the virtual hard disk is configured must be in a stopped state.

## EXAMPLES

### Example 1: Test a dynamic VHD on a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> $VirtDiskDrive = Get-SCVirtualDiskDrive -VM $VM
PS C:\> If ($VM.Status -Eq "Running") {Stop-SCVirtualMachine -VM $VM -Shutdown}
PS C:\> Test-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive
```

The first command gets the virtual machine object named VM03 by using the Get-SCVirtualMachine cmdlet.
This command stores that object in the $VM variable.

The second command gets the virtual disk drive object that is attached to virtual machine VM03, and then stores that object in the $VirtDiskDrive variable.
This example assumes that the virtual machine has only one virtual disk drive object and that the virtual hard disk attached to the virtual disk drive is a dynamic virtual hard disk.

The third command determines whether VM03 is running.
If VM03 is running, the command shuts down the virtual machine.

The last command tests the virtual hard disk stored in $VirtDiskDrive.

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

## NOTES

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVirtualDiskDrive.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualDiskDrive.md)

