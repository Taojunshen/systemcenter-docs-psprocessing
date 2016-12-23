---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: EEC729D0-F1CD-4586-AAAE-67C5F5E3F52D
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMLibrary

## SYNOPSIS
Gets libraries associated with a DPM server.

## SYNTAX

```
Get-DPMLibrary [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMLibrary** cmdlet gets the libraries associated with a System Center 2016 - Data Protection Manager (DPM) server.
You can use this cmdlet to get libraries to use with other cmdlets, such as the [Enable-DPMLibrary](./Enable-DPMLibrary.md) and [Disable-DPMLibrary](./Disable-DPMLibrary.md) cmdlets, or you can use the **Get-DPMLibrary** cmdlet to view the libraries associated with a DPM server and the library status.

## EXAMPLES

### Example 1: Get libraries associated with a server
```
PS C:\>Get-DPMLibrary -DPMServerName "DPMServer07"
```

This command gets the libraries associated with the DPM server named DPMServer07.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets libraries.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Library

## NOTES

## RELATED LINKS

[Disable-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Disable-DPMLibrary.md)

[Enable-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMLibrary.md)

[Rename-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMLibrary.md)
