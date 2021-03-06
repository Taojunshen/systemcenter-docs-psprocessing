---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 85DBEB70-9B62-4002-929C-AA7276DC7690
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
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

[Disable-DPMTapeDrive](xref:SystemCenter2016/DataProtectionManager/vlatest/Disable-DPMTapeDrive.md)

[Enable-DPMTapeDrive](xref:SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMTapeDrive.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

