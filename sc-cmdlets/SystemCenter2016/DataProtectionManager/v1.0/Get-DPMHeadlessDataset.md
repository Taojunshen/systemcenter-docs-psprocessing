---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMLibrary.md
schema: 2.0.0
ms.assetid: FA23B5DE-60C3-4102-AC4C-9A428ADD37F8
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMHeadlessDataset.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMHeadlessDataset.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMHeadlessDataset.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMHeadlessDataset

## SYNOPSIS
Returns incomplete datasets on the archive tape.

## SYNTAX

```
Get-DPMHeadlessDataset [-Tape] <Media[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMHeadlessDataset** cmdlet returns incomplete datasets on the archive tape in System Center 2016 - Data Protection Manager (DPM).

## EXAMPLES

### Example 1: Return an incomplete dataset
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> $DpmTape = Get-DPMTape -DPMLibrary $DpmLibrary
PS C:\> Get-DPMHeadlessDataset -Tape $DpmTape[2]
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library for the server named Contoso-DPMServer.
The command stores the library in the $DpmLibrary variable.

The second command uses the **Get-DPMTape** cmdlet to get the tapes in the library, and stores them in the $DpmTape variable.

The third command retrieves the dataset on the third tape.

## PARAMETERS

### -Tape
Specifies an array of tape objects on which this cmdlet operates.
To obtain a **Tape** object, use the Get-DPMTape cmdlet.

```yaml
Type: Media[]
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

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMLibrary.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMTape.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/v1.0/DataProtectionManager.md)

