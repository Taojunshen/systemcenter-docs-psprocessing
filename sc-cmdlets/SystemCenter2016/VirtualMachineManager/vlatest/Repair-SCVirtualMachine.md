---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5D3FECD4-1ED3-42FB-8D91-C445666298BF
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Repair-SCVirtualMachine

## SYNOPSIS
Repairs a virtual machine in a failed state.

## SYNTAX

### Dismiss
```
Repair-SCVirtualMachine [-VM] <VM> [-Dismiss] [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Undo
```
Repair-SCVirtualMachine [-VM] <VM> [-Undo] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Retry
```
Repair-SCVirtualMachine [-VM] <VM> [-Retry] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Agent
```
Repair-SCVirtualMachine [-VM] <VM> [-Agent] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### MigrateDBOnlyVM
```
Repair-SCVirtualMachine [-VM] <VM> [-MigrateDBOnlyVM] -VMHost <Host> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-SCVirtualMachine** cmdlet repairs a virtual machine in a failed state that is on a host managed by Virtual Machine Manager (VMM).
A virtual machine can be in one of the following types of failed state: 

- Creation Failed
- Migration Failed
- Update Failed
- Deletion Failed

You can use this command to repair a failure as follows: 

- Retry.
Tries to perform the failed job again. 
- Undo.
Try to undo any changes that were made to the virtual machine and restore it to a healthy state.
For example, if a Move-SCVirtualMachine job fails, Undo tries to move the virtual machine back to its previous host. 
- Dismiss.
Dismisses the failed job and updates the virtual machine based on its current state.
If you manually fix a failure, you can use the Dismiss option to refresh the data for the virtual machine in the VMM database.
However, using the Dismiss option might return the object to the failed state.

When you run this cmdlet, you can specify only one type of action at a time.

You can run this cmdlet to repair an in-guest agent for a virtual machine that is part of a service by using the Agent parameter.

## EXAMPLES

### Example 1: Repair a failed migration task by retrying the migration task
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Repair-SCVirtualMachine -VM $VM -Retry
```

The first command gets the virtual machine object named VM01, and then stores that object in the $VM variable.
In this example,  you want to repair a failed move action.

The second command repairs the virtual machine object stored in $VM by restarting the previous failed migration task.

### Example 2: Repair or upgrade the VMM In-guest agent on a specified virtual machine that is part of a service
```
PS C:\> $VM = Get-SCVirtualMachine -Name "ServiceVM01"
PS C:\> $Creds = Get-Credential
PS C:\> Repair-SCVirtualMachine -VM $VM -Credential $Creds -Agent
```

The first command gets the virtual machine object named ServiceVM01, and then stores that object in the $VM variable.
In this example, the virtual machine is part of a service.

The second command gets a credential object, which must be a local administrator on the virtual machine to be repaired, and then stores that object in the $Creds variable.

The third command repairs the in-guest agent on the virtual machine object stored in $VM.

## PARAMETERS

### -Agent
Indicates that this cmdlet repairs or upgrades the VMM in-guest agent, as applicable.

```yaml
Type: SwitchParameter
Parameter Sets: Agent
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dismiss
Dismisses the error on an object or an update notification on a service instance.

After an error is dismissed, the object is refreshed.
If the error reappears, refreshing does not solve the problem and you must fix the error.

```yaml
Type: SwitchParameter
Parameter Sets: Dismiss
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the operation to finish.

```yaml
Type: SwitchParameter
Parameter Sets: Dismiss
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies the name of a variable for job progress.

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

### -MigrateDBOnlyVM
Indicates that this cmdlet uses MigrateDBOnlyVM.

```yaml
Type: SwitchParameter
Parameter Sets: MigrateDBOnlyVM
Aliases: 

Required: True
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -Retry
Indicates that this cmdlet retries the last task that failed on the virtual machine in an attempt to complete the task successfully.

```yaml
Type: SwitchParameter
Parameter Sets: Retry
Aliases: 

Required: True
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

### -Undo
Indicates that this cmdlet cancels the last job run on the virtual machine and reverses any changes that were made.
This parameter is available only if the most recent job failed.

```yaml
Type: SwitchParameter
Parameter Sets: Undo
Aliases: 

Required: True
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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.
For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: MigrateDBOnlyVM
Aliases: 

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

### VirtualMachine

## NOTES
* This cmdlet requires a virtual machine object, which can be retrieved by using the **Get-SCVirtualMachine** cmdlet.

## RELATED LINKS

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Register-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md)

[Reset-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Reset-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

