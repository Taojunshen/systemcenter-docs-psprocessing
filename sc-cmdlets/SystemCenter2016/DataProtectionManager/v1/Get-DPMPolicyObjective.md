---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 6318501C-C09F-4128-9BB0-4D0748877F46
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicyObjective.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicyObjective.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicyObjective.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMPolicyObjective

## SYNOPSIS
Gets the protection policy for a protection group.

## SYNTAX

### LongTerm
```
Get-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> -LongTerm <LongTermLocation> [<CommonParameters>]
```

### ShortTerm
```
Get-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> [-ShortTerm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMPolicyObjective** cmdlet gets the protection policy for a protection group.
A protection policy is the retention range and frequency of synchronization to disk or backup to tape.

## EXAMPLES

### Example 1: Get a short-term policy objective for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMPolicyObjective -ProtectionGroup $PGroup -ShortTerm
```

The first command gets the protection group from the System Center 2016 - Data Protection Manager (DPM) server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the short-term policy objective from the protection group in $PGroup.

### Example 2: Get a long-term policy objective for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMPolicyObjective -ProtectionGroup $PGroup -LongTerm
```

The first command gets the protection group from the DPM server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the long-term policy objective from the protection group in $PGroup.

## PARAMETERS

### -LongTerm
Specifies the type of long-term protection policy that this cmdlet gets.

The acceptable values for this parameter are:

- Tape 
- Online 
- OnlineAndTape

```yaml
Type: LongTermLocation
Parameter Sets: LongTerm
Aliases: 
Accepted values: Online, Tape

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets a policy.
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
Indicates that this cmdlet gets the short-term protection policy.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTerm
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PolicyObjective

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Set-DPMPolicyObjective](xref:SystemCenter2016/DataProtectionManager/v1/Set-DPMPolicyObjective.md)

