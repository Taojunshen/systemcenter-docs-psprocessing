---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B3489A43-6A31-4CA3-A4E5-B9F840E2EA28
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasetStatus.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasetStatus.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasetStatus.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-DPMDatasetStatus

## SYNOPSIS
Gets the status of datasets on an archive tape.

## SYNTAX

```
Get-DPMDatasetStatus [-Tape] <Media> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMDatasetStatus** cmdlet returns the status of datasets on an archive tape.

## EXAMPLES

### Example 1: Get dataset status for an archive tape
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "TestingServer"
PS C:\> $PTape = Get-DPMTape -ProtectionGroup $PGroup
PS C:\> Get-DPMDatasetStatus -Tape $PTape
```

The first command gets the protection groups from the System Center 2016 - Data Protection Manager (DPM) server named TestingServer.
The command stores these protection groups in the $PGroup variable.

The second command gets the tapes associated with the protection groups in $PGroup, and then stores them in the $PTape variable.

The third command returns the status of datasets on the tapes associated with the protection groups in $PGroup.

## PARAMETERS

### -Tape
Specifies a tape for which this cmdlet gets dataset status.
To obtain a **Tape** object, use the [Get-DPMTape](./Get-DPMTape.md) cmdlet.

```yaml
Type: Media
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTape.md)
