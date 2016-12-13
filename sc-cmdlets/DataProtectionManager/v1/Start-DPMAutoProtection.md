---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMAutoProtectIntent.md
schema: 2.0.0
ms.assetid: 11A85CED-4391-42E1-9959-831F0D37E159
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMAutoProtection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMAutoProtection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMAutoProtection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMAutoProtection

## SYNOPSIS
Adds SQL Server databases to a DPM protection group.

## SYNTAX

```
Start-DPMAutoProtection [[-DPMServerName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMAutoProtection** cmdlet adds Microsoft SQL Server databases to a System Center 2016 - Data Protection Manager (DPM) protection group.
The cmdlet searches for new SQL Server databases that belong to SQL Server instances configured for auto-protection.
The cmdlet adds those databases to the protection group for a specified DPM server.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet adds databases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
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

[Get-DPMAutoProtectIntent](xref:DataProtectionManager/v1/Get-DPMAutoProtectIntent.md)

[Set-DPMAutoProtectIntent](xref:DataProtectionManager/v1/Set-DPMAutoProtectIntent.md)

