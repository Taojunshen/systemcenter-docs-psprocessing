---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageFileShare.md
schema: 2.0.0
ms.assetid: 3B58C058-0644-459B-8FAC-B6E5AA20E3D2
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCStorageFileShare

## SYNOPSIS
Removes a storage file share from VMM.

## SYNTAX

```
Remove-SCStorageFileShare [-ForceRemoveFileSystem] [-StorageFileShare] <StorageFileShare> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCStorageFileShare** cmdlet removes a storage file share from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove a storage file share
```
PS C:\>$FileShare = Get-SCStorageFileShare -Name "FileShare01"
PS C:\> Remove-SCStorageFileShare -StorageFileShare $FileShare
```

The first command gets the storage file share object named FileShare01 and stores the object in the $FileShare variable.

The second command removes FileShare01 from VMM.

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

### -ForceRemoveFileSystem
Indicates that the cmdlet removes the storage file share from the file system and deletes the file system from the pool.

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

### -StorageFileShare
Specifies a storage file share.

```yaml
Type: StorageFileShare
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

## RELATED LINKS

[Get-SCStorageFileShare](xref:VirtualMachineManager/v1/Get-SCStorageFileShare.md)

[New-SCStorageFileShare](xref:VirtualMachineManager/v1/New-SCStorageFileShare.md)

[Register-SCStorageFileShare](xref:VirtualMachineManager/v1/Register-SCStorageFileShare.md)

[Repair-SCStorageFileShare](xref:VirtualMachineManager/v1/Repair-SCStorageFileShare.md)

[Set-SCStorageFileShare](xref:VirtualMachineManager/v1/Set-SCStorageFileShare.md)

[Unregister-SCStorageFileShare](xref:VirtualMachineManager/v1/Unregister-SCStorageFileShare.md)

