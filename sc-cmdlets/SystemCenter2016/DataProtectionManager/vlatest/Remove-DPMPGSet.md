---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 20091D8C-4CE4-424C-B47A-E48B0F8845B5
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMPGSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMPGSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMPGSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-DPMPGSet

## SYNOPSIS
Deletes a protection group set.

## SYNTAX

```
Remove-DPMPGSet [-PGSet] <PGSet> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMPGSet** cmdlet deletes a System Center 2016 - Data Protection Manager (DPM) protection group set.
A DPM protection group set is a collection of protection groups that you collocate on the same tape.

## EXAMPLES

### Example 1: Remove a protection group set
```
PS C:\>$PGSet = Get-DPMPGSet -DPMServerName "DPMServer07"
PS C:\> Remove-DPMPGSet -PGSet $PGSet[0]
```

The first command uses the **Get-DPMPGSet** cmdlet to get the protection group sets for the specified server, and then stores them in the $PGSet variable.

The second command specifies the first member of $PGSet by using standard array notation.
The command removes that protection group set.

## PARAMETERS

### -PGSet
Specifies the protection group set that this cmdlet deletes.
To obtain a protection group set object, use the Get-DPMPGSet cmdlet.

```yaml
Type: PGSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMPGSet.md)

[New-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMPGSet.md)

[Update-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMPGSet.md)

