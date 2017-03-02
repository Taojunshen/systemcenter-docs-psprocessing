---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0E15142B-1A88-46B6-BDAC-60AF3ABEBA1E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageLogicalUnit.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageLogicalUnit.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageLogicalUnit.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCStorageLogicalUnit

## SYNOPSIS
Deletes any associations a logical unit has to a host under VMM management.

## SYNTAX

```
Remove-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCStorageLogicalUnit** cmdlet removes any associations a logical unit has to a host under Virtual Machine Manager (VMM) management.
The logical unit information remains in the VMM database.
By default, this operation is not destructive.

Optionally, **Remove-SCStorageLogicalUnit** can delete the logical unit instance from the storage pool, deleting all data contained.

## EXAMPLES

### Example 1: Remove a storage logical unit
```
PS C:\> $LU = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> Remove-SCStorageLogicalUnit -StorageLogicalUnit $LU
```

The first command gets the storage logical unit object named LUN01 and stores the object in the $LU variable.

The second command deletes LUN01.

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

### -StorageLogicalUnit
Specifies a storage logical unit object.

```yaml
Type: StorageLogicalUnit
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

[Get-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageLogicalUnit.md)

[New-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageLogicalUnit.md)

[Register-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageLogicalUnit.md)

[Set-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageLogicalUnit.md)

[Unregister-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageLogicalUnit.md)

