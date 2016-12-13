---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: 4DD66B81-D0AC-4840-96D5-068DF73538B3
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVMCheckpoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVMCheckpoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVMCheckpoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMCheckpoint

## SYNOPSIS
Modifies the properties of a virtual machine checkpoint object in VMM.

## SYNTAX

```
Set-SCVMCheckpoint -VMCheckpoint <VMCheckpoint> [-Description <String>] [-Name <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMCheckpoint** cmdlet modifies the properties of a virtual machine checkpoint object in Virtual Machine Manager (VMM).

For information about creating VMM checkpoints, type `Get-Help New-SCVMCheckpoint -Detailed`.

## EXAMPLES

### Example 1: Set the description for all checkpoints to a specified string
```
PS C:\>Get-SCVMCheckpoint | Set-SCVMCheckpoint -Description "All checkpoints created prior to upgrade"
```

This command gets all existing checkpoint objects from the VMM database and updates the description for these checkpoints.

### Example 2: Modify the name and description for all checkpoints
```
PS C:\>Get-SCVMCheckpoint | Set-SCVMCheckpoint -Name "Checkpoint Before Upgrade" -Description "Checkpoint was created prior to upgrade"
```

This command gets all existing checkpoint objects and modifies the name and description for each object.

### Example 3: Modify a specific checkpoint in an array of checkpoints
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> Set-SCVMCheckpoint -VMCheckpoint $VM.VMCheckpoints[0] -Description "First Checkpoint Before Upgrade"
```

The first  command gets the virtual machine object named VM03 and stores the object in the $VM variable.

The last command modifies the description for the first checkpoint object in the VMCheckpoints array for VM03.

## PARAMETERS

### -Description
Specifies a description for a checkpoint.

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
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
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

[Restore-SCVMCheckpoint](xref:VirtualMachineManager/v1/Restore-SCVMCheckpoint.md)

