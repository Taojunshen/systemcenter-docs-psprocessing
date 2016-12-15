---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: AD2D7E41-4D97-4341-8292-BC292B4FACF5
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMCheckpoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMCheckpoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMCheckpoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMCheckpoint

## SYNOPSIS
Creates a checkpoint for a virtual machine deployed on a host managed by VMM.

## SYNTAX

```
New-SCVMCheckpoint [-VM] <VM> [-VMMServer <ServerConnection>] [-Description <String>] [-Name <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMCheckpoint** cmdlet creates a checkpoint for a virtual machine deployed on a host managed by Virtual Machine Manager (VMM).
You can use a checkpoint to restore a virtual machine to a previous state.

A typical use is to create a checkpoint before you install an update to the operating system or to an application on the virtual machine so that, if the update fails or adversely affects the virtual machine, you can use the Restore-SCVMCheckpoint cmdlet to revert the virtual machine to its previous state.

For virtual machines deployed on a Hyper-V host, VMware ESX host, or Citrix XenServer host, VMM creates the checkpoint without stopping the virtual machine, so no interruption in service occurs.

It is important to back up data files on a virtual machine before you restore the virtual machine to a checkpoint.
When you restore the virtual machine, user data files on its virtual hard disks are returned to their previous state.

Although checkpoints let you restore a virtual machine to a previous state after a change such as a system or application update, checkpoints do not provide a permanent backup of the operating system, applications, or files.
Checkpoints are stored with the virtual machine on the host.
Therefore, if the host fails, checkpoints for virtual machines deployed on that host are lost.

To provide data protection for your virtual machines, you can use the Volume Shadow Copy Service (VSS).
You can use a backup application such as Data Protection Manager (DPM) to back up virtual machines on any type of host to external storage.

You can grant self-service users permission to create and manage checkpoints for their virtual machines.
For more information, type `Get-Help Set-VMMUserRole -Detailed`.

## EXAMPLES

### Example 1: Create a virtual machine checkpoint for virtual machines that have the same name but reside on different hosts
```
PS C:\>$Checkpoints = Get-SCVirtualMachine -Name "VM01" | New-SCVMCheckpoint
PS C:\> $Checkpoints
```

The first command gets the virtual machine objects named VM01 (this example assumes that more than one host contains a virtual machine named VM01), creates a checkpoint for each virtual machine object, and then stores the checkpoint objects in the $Checkpoints object array.

The second command displays information about each checkpoint object stored in $Checkpoints to the user.

### Example 2: Create a virtual machine checkpoint for a virtual machine asynchronously
```
PS C:\>Get-SCVirtualMachine -Name "VM02" | New-SCVMCheckpoint -RunAsynchronously -JobVariable "NewCheckpiontJob"
PS C:\> Write-Host $NewCheckpointJob
```

This example creates checkpoints in the same manner as Example 1 except that this command uses the *RunAsynchronously* parameter to return control to the command shell immediately, and uses the *JobVariable* parameter to track job progress and store a record of the progress in the NewCheckpointJob variable.
When you use the *JobVariable* parameter, you do not use the dollar sign ($) to create the variable.

The second command displays the contents of $NewCheckpointJob.

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
Specifies a description for the checkpoint.

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

### -Name
Specifies the name of a VMM object.

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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMCheckpoint.md)

[Remove-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMCheckpoint.md)

[Restore-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restore-SCVMCheckpoint.md)

[Set-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMCheckpoint.md)

