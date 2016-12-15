---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMRole.md
schema: 2.0.0
ms.assetid: AC42C0E6-326C-411B-A0EC-E59BB9BA7024
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-DPMRole

## SYNOPSIS
Deletes a DPM role.

## SYNTAX

```
Remove-DPMRole [-DpmRole] <DpmRole> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMRole** cmdlet deletes a System Center 2016 - Data Protection Manager (DPM) role.
DPM roles let Microsoft SQL Server database owners to recover databases without assistance from a DPM administrator.

## EXAMPLES

### Example 1: Remove a role
```
PS C:\>$DpmRole = Get-DpmRole -Name "OpsMgrSQL" -Editable
PS C:\> Remove-DPMRole -DpmRole $DpmRole
```

The first command gets the role by using the **Get-DPMRole** cmdlet, and then stores it in the $DpmRole variable.
The command makes the role editable.

The second command removes the role stored in $DpmRole.

## PARAMETERS

### -DpmRole
Specifies a DPM role that this cmdlet removes.
To obtain a DPM role object, use the Get-DPMRole cmdlet.

```yaml
Type: DpmRole
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

[Get-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRole.md)

[New-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRole.md)

[Rename-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMRole.md)

[Set-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMRole.md)

