---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: D2BBB6FA-8330-4F56-AE41-6AAF8ECF2845
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualDiskDrive

## SYNOPSIS
Removes virtual disk drives from a virtual machine or from a virtual machine template.

## SYNTAX

```
Remove-SCVirtualDiskDrive [-VirtualDiskDrive] <VirtualDiskDrive> [-SkipDeleteVHD] [-JobGroup <Guid>] [-Force]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualDiskDrive** cmdlet removes virtual disk drive objects from a virtual machine or from a virtual machine template in a Virtual Machine Manager (VMM) environment.

## EXAMPLES

### Example 1: Remove a virtual disk drive from a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine | Where-Object { $_.VMHost.Name -Eq "VMHost01.Contoso.com" -And $_.Name -Eq "VM01" }
PS C:\> $VirtDiskDrive = @(Get-SCVirtualDiskDrive -VM $VM)
PS C:\> If($VirtDiskDrive.Count -Gt 1){Remove-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive[1]}
```

The first command gets the virtual machine object named VM01 deployed on VMHost01 by using the Get-SCVirtualMachine cmdlet.
The command stores that object in the $VM variable.

The second command gets all virtual disk drive objects on VM01, and then stores the retrieved objects in $VirtDiskDrive.
Using the @ symbol and parentheses makes sure that the command stores the results in an array, even if the command returns a single object or a $Null value.

The last command returns the number of virtual disk drives associated with the virtual machine and then, if more than one exists, the command removes the second virtual disk drive, designated by the \[1\], from the virtual machine.

### Example 2: Remove all pass-through disks attached to a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine | Where-Object {$_.Name -Eq "VM02"}
PS C:\> $VirtDiskDrives = @(Get-SCVirtualDiskDrive -VM $VM | Where-Object {$_.IsVHD -Eq $False})
PS C:\> If($VirtDiskDrives.Count -Gt 0){ForEach($VirtDiskDrive in $VirtDiskDrives){Remove-SCVirtualDiskDrive -Force -VirtualDiskDrive $VirtDiskDrive}}
```

The first command gets the virtual machine object named VM02, and then stores that object in the $VM variable.

The second command gets all virtual disk drive objects attached to VM02 that are not virtual hard disks.
The command gets only objects that represent pass-through disks.
The command stores the pass-through disk objects in the $VDDs object array.

The last command uses an **If** statement to determine whether at least one pass-through virtual disk drive exists.
If the result is one or more, the command then uses the **ForEach** statement to remove each virtual disk drive from the object array.
For more information, type `Get-Help about_If` and `Get-Help about_Foreach`.

The last command specifies the *Force* parameter.
Therefore, the command removes each virtual disk drive from its virtual machine even if other VMM objects depend on that virtual disk drive.

### Example 3: Remove virtual disk drives by name
```
PS C:\>$VM = @(Get-SCVirtualMachine | Where-Object {$_.Name -Match "WebSrvLOB"})
PS C:\> ForEach-Object ($VM in $VMs){$VirtDiskDrives = Get-SCVirtualDiskDrive -VM $VM 
PS C:\> ForEach-Object ($VirtDiskDrive in $VirtDiskDrives){If($VirtDiskDrive.Name -Match "LOBData"){Remove-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive}}}
```

The first command gets all virtual machine objects whose name matches the string WebSrvLOB, and then stores those objects in the $VM array.

The next two commands use the ForEach-Object cmdlet to iterate through the virtual machines stored in $VM to get all virtual disk drive objects from each virtual machine.
The second command stores the virtual disk drive objects in the $VirtDiskDrives object array.

The third command uses a second **ForEach** loop to select all virtual disk drive objects whose name contains the string LOBData from the $VirtDiskDrives array and passes these objects to the current cmdlet.
This cmdlet removes the objects from VMM.

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

### -Force
Forces the operation to finish.

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

### -SkipDeleteVHD
Indicates that this cmdlet does not the VHD file while it removes the virtual disk drive.

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
* Requires a VMM virtual disk drive object, which can be retrieved by using the Get-SCVirtualDiskDrive cmdlet.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDiskDrive.md)

[Test-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVirtualDiskDrive.md)

