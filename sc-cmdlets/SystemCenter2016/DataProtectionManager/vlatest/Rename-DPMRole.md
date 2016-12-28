---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DF15F50F-2A1E-43BF-B95C-0CCF0D598C7E
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Rename-DPMRole

## SYNOPSIS
Changes the name or description of a DPM role.

## SYNTAX

```
Rename-DPMRole [-DpmRole] <DpmRole> [[-Name] <String>] [[-Description] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Rename-DPMRole** cmdlet changes the name or description of a System Center 2016 - Data Protection Manager (DPM) role.
DPM roles let Microsoft SQL Server database owners to recover databases without assistance from a DPM administrator.
Save your changes by using the Set-DPMRole cmdlet.

## EXAMPLES

### Example 1: Change the name of a role
```
PS C:\>$DpmRole = Get-DpmRole -Name "OpsMgrSQL" -Editable
PS C:\> Rename-DPMRole -DpmRole $DpmRole -Name "OpsMgrSQL23" 
PS C:\> Set-DPMRole -DPMRole $DpmRole
```

The first command gets the role by using the **Get-DpmRole** cmdlet, and then stores it in the $DpmRole variable.
The command makes the role editable.

The second command renames the role stored in $DpmRole.

The third command saves the change made in the second command for the role stored in $DpmRole by using the **Set-DPMRole** cmdlet.

## PARAMETERS

### -Description
Specifies a description for the DPM role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DpmRole
Specifies a DPM role that this cmdlet modifies.
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

### -Name
Specifies a name for the DPM role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

[Remove-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRole.md)

[Set-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMRole.md)

