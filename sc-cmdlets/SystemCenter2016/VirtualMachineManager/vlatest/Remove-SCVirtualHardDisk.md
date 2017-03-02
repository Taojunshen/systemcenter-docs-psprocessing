---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5EFCEE2D-F014-4559-B886-59A8D5D22A1F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualHardDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualHardDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualHardDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCVirtualHardDisk

## SYNOPSIS
Removes a virtual hard disk object from a virtual machine or template, or from the VMM library.

## SYNTAX

```
Remove-SCVirtualHardDisk [-VirtualHardDisk] <VirtualHardDisk> [-JobGroup <Guid>] [-Force] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualHardDisk** cmdlet removes a virtual hard disk object from a virtual machine or template, or from the Virtual Machine Manager (VMM) library.
**Remove-VirtualHardDisk** also deletes the corresponding virtual hard disk file (a Windows-based .vhd file, a Citrix XenServer-based .vhd file, or a VMware-based .vmdk file) from the library server.

If the virtual hard disk is attached to a virtual disk drive on a virtual machine or template (and if you do not use the *Force* parameter), VMM lists the container that contains the virtual hard disk and prompts you to confirm that you want to remove the virtual hard disk: 



- If you reply Yes, VMM removes the association between the virtual hard disk and the container to which it is attached, and then deletes the virtual hard disk object from VMM. 


- If you reply No, the operation is cancelled.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a virtual hard disk object from the library
```
PS C:\> $VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "VHD01.vhd" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Remove-SCVirtualHardDisk -VirtualHardDisk $VHD
```

The first command gets the virtual hard disk object named VHD01.vhd stored on LibraryServer01 and stores the returned object in the $VHD variable.

The second command removes the virtual hard disk object stored in $VHD from the library and deletes the corresponding file from the file system on the library server.

### Example 2: Remove a virtual hard disk from a virtual machine
```
PS C:\> Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> $VHD = Get-SCVirtualMachine -Name "VM01" | Get-SCVirtualHardDisk | where { $_.Name -match "DataDisk" }
PS C:\> $VHD | Remove-SCVirtualHardDisk
```

The first command connects to VMMServer01.

The second command gets the virtual machine object named VM01, gets all virtual hard disks on VM01 whose name includes the string "DataDisk", and then stores these virtual hard disk objects in an array named $VHD.

The third command removes each virtual hard disk object stored in the $VHD array from the virtual machine and deletes each corresponding file from the file system on the library server.

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
Forces the command to run without asking for user confirmation.

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

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: VirtualHardDisk
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
* Requires a VMM virtual hard disk object, which can be retrieved by using the **Get-SCVirtualHardDisk** cmdlet.

## RELATED LINKS

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDisk.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

[Move-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualHardDisk.md)

[Set-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDisk.md)

