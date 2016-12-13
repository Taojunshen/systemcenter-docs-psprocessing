---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCStorageProvider.md
schema: 2.0.0
ms.assetid: 58CD51B9-FAE9-4135-BA82-56FAA3F4FD59
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCStorageProvider

## SYNOPSIS
Removes a storage provider from VMM.

## SYNTAX

```
Remove-SCStorageProvider [-StorageProvider] <StorageProvider> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCStorageProvider** cmdlet removes a storage provider from Virtual Machine Manager (VMM).
Removing a storage provider also removes any associated array, pool, and logical unit information exposed by the provider.
However, this operation does not change or delete any data on the logical units.

## EXAMPLES

### Example 1: Remove a storage provider
```
PS C:\>$Provider = Get-SCStorageProvider -Name "StorProv01.Contoso.com"
PS C:\> Remove-SCStorageProvider -StorageProvider $Provider
```

The first command gets the storage provider named StorProv01 and stores it in the $Provider variable.

The second command deletes the storage provider stored in the $Provider variable.

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

### -StorageProvider
Specifies a storage provider object.

```yaml
Type: StorageProvider
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

[Add-SCStorageProvider](xref:VirtualMachineManager/v1/Add-SCStorageProvider.md)

[Get-SCStorageProvider](xref:VirtualMachineManager/v1/Get-SCStorageProvider.md)

[Import-SCStorageProvider](xref:VirtualMachineManager/v1/Import-SCStorageProvider.md)

[Read-SCStorageProvider](xref:VirtualMachineManager/v1/Read-SCStorageProvider.md)

[Set-SCStorageProvider](xref:VirtualMachineManager/v1/Set-SCStorageProvider.md)

