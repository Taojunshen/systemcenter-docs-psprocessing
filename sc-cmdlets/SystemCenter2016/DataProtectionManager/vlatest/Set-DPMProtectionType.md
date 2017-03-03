---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4E583C9E-21BD-49D1-88CD-2AA5B7A7875A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionType.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionType.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionType.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-DPMProtectionType

## SYNOPSIS
Sets the protection type for a protection group.

## SYNTAX

```
Set-DPMProtectionType [-ProtectionGroup] <ProtectionGroup> [-ShortTerm <DataLocation>]
 [-LongTerm <LongTermProtection>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMProtectionType** cmdlet sets the protection type for a protection group.

You can use the *ShortTerm* and *LongTerm* parameters individually or in combination to define protection types.

You can set the following combinations of parameter values for a protection type: 

- Disk to disk.
`-ShortTerm Disk`
- Disk to tape.
`-ShortTerm Tape`
- Disk to tape, long-term.
`-LongTerm Tape`
- Disk to disk to tape.
`-ShortTerm Disk -LongTerm Tape`
- Disk to tape to tape.
`-ShortTerm Tape -LongTerm Tape`

## EXAMPLES

### Example 1: Set the protection type to short term on disk
```
PS C:\>$PGroup = New-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Set-DPMProtectionType -ProtectionGroup $PGroup -ShortTerm Disk
```

The first command gets the protection group on the System Center 2016 - Data Protection Manager (DPM) server named DPMServer02, and then stores the group in the $PGroup variable.

The second command sets the protection type for the protection group in $PGroup to short-term on disk.

### Example 2: Set the protection type to disk to disk to tape
```
PS C:\>$PGroup = New- DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Set-DPMProtectionType -ProtectionGroup $PGroup -ShortTerm Disk -LongTerm Tape
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the group in the $PGroup variable.

The second command sets the protection type for the protection group in $PGroup to disk to disk to tape.

## PARAMETERS

### -LongTerm
Specifies that the protection group is set to long-term tape protection.
The acceptable values for this parameter are:

- Tape
- Online
- OnlineAndTape

```yaml
Type: LongTermProtection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ProtectionGroup
Specifies a protection group for which this cmdlet sets a protection type.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

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

### -ShortTerm
Specifies that the protection group is on disk, on tape, or on neither, if you do not specify a value.
The acceptable values for this parameter are: Disk and Tape.

```yaml
Type: DataLocation
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md)

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

