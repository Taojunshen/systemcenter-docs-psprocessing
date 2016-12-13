---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 1DAD3052-FF84-4E20-B55D-494C1D643E8D
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMModifiableProtectionGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMModifiableProtectionGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMModifiableProtectionGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMModifiableProtectionGroup

## SYNOPSIS
Gets a DPM protection group in an editable mode.

## SYNTAX

```
Get-DPMModifiableProtectionGroup [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMModifiableProtectionGroup** cmdlet gets a System Center 2016 - Data Protection Manager (DPM) protection group in an editable mode.

Once you have made the changes to the protection group, save the changes by using the Set-DPMProtectionGroup cmdlet.

Follow this sequence of steps when you work with a modifiable protection group:

- Run the **Get-DPMProtectionGroup** cmdlet to get the unmodifiable protection group.
- Run the Get-DPMModifiableProtectionGroup cmdlet to get the protection group from the previous step in modifiable form.
- Perform actions on the protection group.
- Run the **Set-DPMProtectionGroup** cmdlet to save the changed protection group.

## EXAMPLES

### Example 1: Get a protection group in a modifiable state
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07"
PS C:\> Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup
```

The first command gets the protection group from the DPM server named TestingServer, and then stores that group in the variable named $PGroup.

The second command gets the protection group from $PGroup in a modifiable.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group that this cmdlet gets.
To obtain a **ProtectionGroup** object, use the **Get-DPMProtectionGroup** cmdlet.

```yaml
Type: ProtectionGroup
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

### ProtectionGroup (Editable)

## NOTES

## RELATED LINKS

[Set-DPMProtectionGroup](xref:DataProtectionManager/v1/Set-DPMProtectionGroup.md)

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

