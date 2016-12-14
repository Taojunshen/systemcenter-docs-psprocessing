---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Enable-DPMProductionServer.md
schema: 2.0.0
ms.assetid: 3FA00C73-BD40-4FEF-8C8C-CE3F50A0A7D9
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMProductionServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMProductionServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMProductionServer.md
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

[Enable-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/v1/Enable-DPMProductionServer.md)

[Disable-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/v1/Disable-DPMProductionServer.md)

[Update-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/v1/Update-DPMProductionServer.md)
