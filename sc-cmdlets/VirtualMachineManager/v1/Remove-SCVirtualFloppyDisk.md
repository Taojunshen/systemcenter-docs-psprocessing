---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualFloppyDisk.md
schema: 2.0.0
ms.assetid: 1A44DF74-5838-4183-B7EF-7602863D0641
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualFloppyDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualFloppyDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualFloppyDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualFloppyDisk

## SYNOPSIS
Removes a virtual floppy disk object from VMM.

## SYNTAX

```
Remove-SCVirtualFloppyDisk [-VirtualFloppyDisk] <VirtualFloppyDisk> [-Force] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualFloppyDisk** cmdlet removes a virtual floppy disk object from the Virtual Machine Manager (VMM) library and deletes the corresponding virtual floppy disk file (a Windows-based .vfd file or a VMware-based .flp file) from the library server.

If the virtual floppy disk is attached to a virtual machine, template, or hardware profile (and if you do not use the *Force* parameter), VMM lists the container that contains the virtual floppy disk and prompts you to confirm that you want to remove the virtual floppy disk: 



- If you reply Yes, VMM removes the association between the virtual floppy disk and the container to which it is attached, and then deletes the virtual floppy disk object from VMM. 


- If you reply No, the operation is cancelled.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a virtual floppy disk object from the library and delete the corresponding file
```
PS C:\>$VFD = Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com"  | where { $_.Name -eq "BootFloppy.vfd" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Remove-SCVirtualFloppyDisk -VirtualFloppyDisk $VFD
```

The first command gets the virtual floppy disk file object named BootFloppy.vfd stored on LibraryServer01, and then stores the virtual floppy disk object in the $VFD variable.

The second command removes the floppy disk object stored in $VFD from the library and deletes the corresponding virtual floppy disk file from the library server.

### Example 2: Remove multiple virtual floppy disks and their files
```
PS C:\>$VFDs = Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "Boot" }
PS C:\> $VFDs | Remove-SCVirtualFloppyDisk
```

The first command gets all virtual floppy disk objects whose names include the string "Boot" and stores these objects in the array named $VFDs.

The second command passes each virtual floppy disk object in $VFDs to the **Remove-VirtualFloppyDisk** cmdlet, which removes each virtual floppy disk object from the library.
The command also deletes each corresponding file from the library server on which that virtual floppy disk is stored.

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

### -VirtualFloppyDisk
Specifies a virtual floppy disk object.

```yaml
Type: VirtualFloppyDisk
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
* Requires a VMM virtual floppy disk object, which can be retrieved by using the Get-SCVirtualFloppyDisk cmdlet.

## RELATED LINKS

[Get-SCVirtualFloppyDisk](xref:VirtualMachineManager/v1/Get-SCVirtualFloppyDisk.md)

[Set-SCVirtualFloppyDisk](xref:VirtualMachineManager/v1/Set-SCVirtualFloppyDisk.md)

