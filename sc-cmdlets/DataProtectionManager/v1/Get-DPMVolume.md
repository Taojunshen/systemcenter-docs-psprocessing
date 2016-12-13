---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./DataProtectionManager.md
schema: 2.0.0
ms.assetid: F959C45C-C47B-4AD0-9531-993218925A58
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMVolume.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMVolume.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMVolume.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMVolume

## SYNOPSIS
Gets the volumes on the DPM server.

## SYNTAX

```
Get-DPMVolume [[-DPMServerName] <String>] [-AlreadyInUseByDPM] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMVolume** cmdlet retrieves the volumes on the System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Retrieve volumes on a DPM server
```
PS C:\>Get-DPMVolume -DPMServerName "Contoso-DPMServer"
```

This command retrieves the DPM volumes on the server named Contoso-DPMServer.

## PARAMETERS

### -AlreadyInUseByDPM
Indicates whether to include volumes that are already being used on the DPM server.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server from which this cmdlet gets volumes.

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

## NOTES

## RELATED LINKS

[Data Protection Manager Cmdlets](xref:DataProtectionManager/v1/DataProtectionManager.md)

