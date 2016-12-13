---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: 8C7079DE-0FAF-4F94-84AA-EE40411DF2D7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Restore-SCVMCheckpoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Restore-SCVMCheckpoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Restore-SCVMCheckpoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Restore-SCVMCheckpoint

## SYNOPSIS
Restores a virtual machine to a specified checkpoint.

## SYNTAX

```
Restore-SCVMCheckpoint -VMCheckpoint <VMCheckpoint> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Restore-SCVMCheckpoint** cmdlet restores a virtual machine to a specified checkpoint.
A virtual machine checkpoint is a point-in-time "snapshot" of a virtual machine.
You can use the checkpoint to revert a virtual machine to a previous state.

If the restore operation is successful, the **Restore-VMCheckpoint** cmdlet returns the checkpoint object.
If the operation fails, the cmdlet returns an error message.

Restoring a virtual machine to an earlier checkpoint discards all changes made to the virtual machine since the most recent checkpoint was created.
However, all checkpoints, including those made after the checkpoint to which you restore a virtual machine, remain available.
Therefore, a good practice is to create a new checkpoint before you restore the virtual machine to ensure that the current state of the virtual machine is available after the restore operation.

## EXAMPLES

### Example 1: Restore a virtual machine to its most recent checkpoint
```
PS C:\>Get-SCVMCheckpoint -VM "VM01" -MostRecent | Restore-SCVMCheckpoint
```

This command gets the most recent checkpoint object for virtual machine VM01 and restores VM01 to the state that it was in at the time its most recent checkpoint was created.

### Example 2: Restore a virtual machine to the specified checkpoint
```
PS C:\>$Checkpoints = Get-SCVMCheckpoint -VM "VM02"
PS C:\> Restore-SCVMCheckpoint -VMCheckpoint $Checkpoints[$Checkpoints.count - 2]
```

The first command gets all checkpoint objects for virtual machine VM02 and stores the objects in the $Checkpoints object array.

The second command restores VM02 to the second-from-last checkpoint (this example assumes you have at least two checkpoints).
VMM retains the checkpoints created after the checkpoint that you restore to, enabling you to restore the virtual machine to a later checkpoint.
To restore a virtual machine to its most recent checkpoint, see Example 1.

### Example 3: View the hardware profile of the last restored checkpoint on a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $VM.LastRestoredVMCheckpoint.CheckpointHWProfile
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.This example assumes that the virtual machine has been restored to one of its checkpoints.

The second command displays information about the hardware profile of the last restored checkpoint on VM02.

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
To obtain a user role, use the Get-SCUserRole cmdlet.
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

### -VMCheckpoint
Specifies a Virtual Machine Manager (VMM) virtual machine checkpoint object.

```yaml
Type: VMCheckpoint
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### VMCheckpoint
This cmdlet returns a **VMCheckpoint** object.

## NOTES
* Requires a VMM checkpoint object, which you can retrieve by using the Get-SCVMCheckpoint cmdlet.

## RELATED LINKS

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCVMCheckpoint](xref:VirtualMachineManager/v1/Get-SCVMCheckpoint.md)

[New-SCVMCheckpoint](xref:VirtualMachineManager/v1/New-SCVMCheckpoint.md)

[Remove-SCVMCheckpoint](xref:VirtualMachineManager/v1/Remove-SCVMCheckpoint.md)

[Set-SCVMCheckpoint](xref:VirtualMachineManager/v1/Set-SCVMCheckpoint.md)

