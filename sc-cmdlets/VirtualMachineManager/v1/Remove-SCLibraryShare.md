---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLibraryShare.md
schema: 2.0.0
ms.assetid: 46C95B6E-6E25-415D-B620-F528BFA29A22
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCLibraryShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCLibraryShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCLibraryShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCLibraryShare

## SYNOPSIS
Removes a library share from VMM but does not delete the share from the Windows file system.

## SYNTAX

```
Remove-SCLibraryShare [-LibraryShare] <LibraryShare> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLibraryShare** cmdlet removes a library share from the Virtual Machine Manager (VMM) library.
This cmdlet does not remove any shares or files from the file system on the computer.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to $True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a library share object from the VMM library
```
PS C:\>$LibShare = Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "AllVHDs" }
PS C:\> Remove-SCLibraryShare -LibraryShare $LibShare
```

The first command gets the library share object named AllVHDs on LibraryServer01 from the VMM library on VMMServer01 and then stores the object in the $LibShare variable.

The second command removes the library share object and all library objects in this share from the VMM library but does not delete the share or its contents from the file system on the library server.

### Example 2: Remove multiple library share objects from the VMM library
```
PS C:\>$LibShares = Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -match "vhd" }
PS C:\> $LibShares | Remove-SCLibraryShare
```

The first command gets all library share objects on LibraryServer01 whose name includes the string "vhd" from the VMM library on VMMServer01 and then stores these share objects in the $LibShares variable (an object array).

The second command passes each library share object in $LibShares to **Remove-SCLibraryShare**.
The cmdlet removes each of the library share objects and all objects in the share from the VMM library but does not delete the corresponding shares or their contents from the file system on the library server.

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

### -LibraryShare
Specifies a VMM library share object.

```yaml
Type: LibraryShare
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## RELATED LINKS

[Add-SCLibraryShare](xref:VirtualMachineManager/v1/Add-SCLibraryShare.md)

[Find-SCLibraryShare](xref:VirtualMachineManager/v1/Find-SCLibraryShare.md)

[Get-SCLibraryShare](xref:VirtualMachineManager/v1/Get-SCLibraryShare.md)

[Read-SCLibraryShare](xref:VirtualMachineManager/v1/Read-SCLibraryShare.md)

[Set-SCLibraryShare](xref:VirtualMachineManager/v1/Set-SCLibraryShare.md)
