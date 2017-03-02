---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 48C38947-7B49-4305-9C0C-DBEA5EE4DD29
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCVirtualMachine

## SYNOPSIS
Removes a virtual machine object from VMM.

## SYNTAX

```
Remove-SCVirtualMachine [-VM] <VM> [-SkipFileRemoval] [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualMachine** cmdlet removes a virtual machine object deployed on a host or stored on a Virtual Machine Manager (VMM) library server.

This cmdlet deletes the virtual machine record from the VMM database, deletes all files associated with the virtual machine, and removes the virtual machine from the host on which it is deployed or from the library server on which it is stored.

If a folder on a host was created for this virtual machine by VMM, instead of by Hyper-V or VMware, and if that folder contains no other virtual machines or other data, you can use the file system to delete the folder after you have removed the virtual machine.

If you specify the *Force* parameter, this cmdlet only deletes the virtual machine from the VMM database.
It does not delete the virtual machine itself.

This cmdlet returns the object upon success that has a value of $True for the **MarkedForDeletion** property.
If it fails, the cmdlet returns an error message.

## EXAMPLES

### Example 1: Remove a specific virtual machine deployed on a host
```
PS C:\> $VM = Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | where { $_.VMHost.Name -eq "VMHost01.Contoso.com" -and $_.Name -eq "VM01" }
PS C:\> Remove-SCVirtualMachine -VM $VM
```

The first command gets the virtual machine object named VM01 deployed on VMHost01, and then stores the virtual machine object in the $VM variable.

The second command removes the object stored in $VM and deletes the corresponding virtual machine files from the file system on its host.

### Example 2: Remove all virtual machines with names that include a specific string
```
PS C:\> $VMs = @(Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -Match "VM0" } )
PS C:\> $VMs | Remove-SCVirtualMachine
```

The first command gets all virtual machine objects deployed on any host whose name includes the string VM0, and then stores these virtual machine objects in the array named $VMs.

The second command removes each virtual machine object in the $VMs array and deletes the corresponding virtual machine files from the file system on each host.

### Example 3: Remove a specific virtual machine stored on a VMM library server
```
PS C:\> $VM = Get-SCVirtualMachine -VMMServer "VMMServer1.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "VM02" }
PS C:\> Remove-SCVirtualMachine -VM $VM
```

The first command gets the object that represents the virtual machine named VM03, and then stores the virtual machine object in $VM.
In this example, only one virtual machine named VM03 exists.

The second command removes the object that represents VM03 from the library and deletes the corresponding virtual machine files from the file system on the library server.

### Example 4: Remove multiple stored virtual machines from the VMM library
```
PS C:\> $VMs = Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -match "VM0" }
PS C:\> $VMs | Remove-SCVirtualMachine -Confirm
```

The first command gets all virtual machine objects whose names include the string VM0 and that are stored stored on LibraryServer01.
The command then stores the virtual machine objects in the array named $VMs.

The second command passes each virtual machine object stored in $VMs to the current cmdlet, which removes each object from the library and deletes the corresponding virtual machine files from the file system on the library server.
The *Confirm* parameter prompts you to confirm whether you want to delete each of these virtual machines.

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
Indicates that this cmdlet only deletes the virtual machine from the VMM database.
It does not delete the virtual machine itself.

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

### -SkipFileRemoval
Indicates that this cmdlet does not remove virtual machine related files directly.
If you specify this parameter, no attempt is made to delete any files directly.

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
* This cmdlet requires a VMM virtual machine object, which can be retrieved by using the **Get-SCVirtualMachine** cmdlet.

## RELATED LINKS

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Save-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

