---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./New-DPMPGSet.md
schema: 2.0.0
ms.assetid: 70EAC52C-3C7D-4011-B1C0-E88AF9431749
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMPGSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMPGSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMPGSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMPGSet

## SYNOPSIS
Gets protection group sets on a DPM server.

## SYNTAX

```
Get-DPMPGSet [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMPGSet** cmdlet gets the System Center 2016 - Data Protection Manager (DPM) protection group sets on a DPM server.

## EXAMPLES

### Example 1: Get protection group sets
```
PS C:\>Get-DPMPGSet -DPMServerName "DPMServer07"
```

This command gets the protection group sets for the server named DPMServer07.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets protection group sets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMPGSet.md)

[Remove-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMPGSet.md)

[Update-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMPGSet.md)

