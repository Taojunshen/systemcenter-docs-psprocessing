---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F4D7FA99-9034-4800-A34F-ADC7B3542FCD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMCheckpoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMCheckpoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMCheckpoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMCheckpoint

## SYNOPSIS
Removes a virtual machine checkpoint object from the VMM database.

## SYNTAX

```
Remove-SCVMCheckpoint -VMCheckpoint <VMCheckpoint> [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMCheckpoint** cmdlet removes a virtual machine checkpoint object from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Remove the most recent checkpoint for a virtual machine
```
PS C:\> $Checkpoint = Get-SCVMCheckpoint -VM "VM01" -MostRecent
PS C:\> Remove-SCVMCheckpoint -VMCheckpoint $Checkpoint -Confirm
```

The first command gets all checkpoint objects for VM01 and stores these objects in the $Checkpoints object array.
This example assumes that VM01 has several checkpoints.

The second command removes the first checkpoint in the array ($Checkpoints\[0\]).
The *Confirm* parameter prompts you to confirm whether you want to remove the checkpoint.

### Example 2: Remove a specified checkpoint for a virtual machine
```
PS C:\> $Checkpoints = Get-SCVMCheckpoint -VM "VM01" 
PS C:\> Remove-SCVMCheckpoint -VMCheckpoint $Checkpoints[0] -Confirm
```

The first command gets all checkpoint objects for VM01 and stores the objects in the $Checkpoints object array.
This example assumes that VM01 has at least two checkpoints.

The second command removes the first checkpoint stored inthe $Checkpoints array, which is the first checkpoint created for VM01.
The command prompts you for confirmation before proceeding.

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

### -VMCheckpoint
Specifies a VMM virtual machine checkpoint object.

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

## NOTES
* Requires a VMM checkpoint object, which you can retrieve by using the **Get-SCVMCheckpoint** cmdlet.

## RELATED LINKS

[Get-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMCheckpoint.md)

[New-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMCheckpoint.md)

[Restore-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restore-SCVMCheckpoint.md)

[Set-SCVMCheckpoint](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMCheckpoint.md)

