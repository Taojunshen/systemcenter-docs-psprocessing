---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Disable-DPMTapeDrive.md
schema: 2.0.0
ms.assetid: 85DBEB70-9B62-4002-929C-AA7276DC7690
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMTapeDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMTapeDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMTapeDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMTapeDrive

## SYNOPSIS
Retrieves the tape drives in a library.

## SYNTAX

```
Get-DPMTapeDrive [-DPMLibrary] <Library[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMTapeDrive** cmdlet retrieves the tape drives in a library on a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Retrieve a list of tape drives in a library
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> Get-DPMTapeDrive -DPMLibrary $DpmLibrary
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library for the server named Contoso-DPMServer.
The command stores it in the $DpmLibrary variable.

The second command uses the **Get-DPMTapeDrive** cmdlet to get the tape drives for the library in $DpmLibrary.

## PARAMETERS

### -DPMLibrary
Specifies an array of DPM library objects for which this cmdlet gets tape drives.
To obtain a DPM library object, use the Get-DPMLibrary cmdlet.

```yaml
Type: Library[]
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

### TapeDrive

## NOTES

## RELATED LINKS

[Disable-DPMTapeDrive](xref:DataProtectionManager/v1/Disable-DPMTapeDrive.md)

[Enable-DPMTapeDrive](xref:DataProtectionManager/v1/Enable-DPMTapeDrive.md)

[Get-DPMLibrary](xref:DataProtectionManager/v1/Get-DPMLibrary.md)

