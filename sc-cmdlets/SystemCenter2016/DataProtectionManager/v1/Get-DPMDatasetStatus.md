---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: B3489A43-6A31-4CA3-A4E5-B9F840E2EA28
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMDatasetStatus.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMDatasetStatus.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMDatasetStatus.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
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
To obtain a **Tape** object, use the Get-DPMTape cmdlet.

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

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMTape.md)

