---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMLibrary.md
schema: 2.0.0
ms.assetid: 5C031B76-6464-4D9D-83F7-F79C842A80E1
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMTapeSlot.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMTapeSlot.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMTapeSlot.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMTapeSlot

## SYNOPSIS
Gets tape slots in the DPM library.

## SYNTAX

```
Get-DPMTapeSlot [-DPMLibrary] <Library[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMTapeSlot** cmdlet gets tape slots in the System Center 2016 - Data Protection Manager (DPM) library.

## EXAMPLES

### Example 1: Retrieve the tape slots in a library
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> Get-DPMTapeSlot -DPMLibrary $DpmLibrary
```

The first command uses the **Get-DPMLibrary** cmdlet to retrieve the library for the server named Contoso-DPMServer, and then stores the result in the $DpmLibrary variable.

The second command gets the tape slots for the library.

## PARAMETERS

### -DPMLibrary
Specifies an array of DPM library objects.
This cmdlet gets tape slots for the libraries that this cmdlet specifies.
To obtain a DPM library object, use the **Get-DPMLibrary** cmdlet.

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

### SlotNumber

## NOTES

## RELATED LINKS

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMLibrary.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/v1/DataProtectionManager.md)

