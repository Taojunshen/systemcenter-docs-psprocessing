---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Enable-DPMProductionServer.md
schema: 2.0.0
ms.assetid: 3FA00C73-BD40-4FEF-8C8C-CE3F50A0A7D9
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMProductionServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMProductionServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMProductionServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMProductionServer

## SYNOPSIS
Gets computers on which the DPM protection agent is installed.

## SYNTAX

```
Get-DPMProductionServer [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMProductionServer** cmdlet gets computers on which the System Center 2016 - Data Protection Manager (DPM) protection agent is installed.

## EXAMPLES

### Example 1: Get computers protected by a DPM server
```
PS C:\>Get-DPMProductionServer -DPMServerName "DpmTsqa01"
```

This command gets the list of computers on which the protection agents is installed for the DPM server named DpmTsqa01.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server.
This cmdlet gets computers that have the protection agent for the server that this parameter specifies.
If you do not specify a name, the cmdlet uses the current computer name.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ProductionServer

## NOTES

## RELATED LINKS

[Enable-DPMProductionServer](xref:DataProtectionManager/v1/Enable-DPMProductionServer.md)

[Disable-DPMProductionServer](xref:DataProtectionManager/v1/Disable-DPMProductionServer.md)

[Update-DPMProductionServer](xref:DataProtectionManager/v1/Update-DPMProductionServer.md)

