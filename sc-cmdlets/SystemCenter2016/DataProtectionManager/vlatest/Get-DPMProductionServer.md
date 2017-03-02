---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3FA00C73-BD40-4FEF-8C8C-CE3F50A0A7D9
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
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
PS C:\> Get-DPMProductionServer -DPMServerName "DpmTsqa01"
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

[Enable-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMProductionServer.md)

[Disable-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Disable-DPMProductionServer.md)

[Update-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProductionServer.md)
