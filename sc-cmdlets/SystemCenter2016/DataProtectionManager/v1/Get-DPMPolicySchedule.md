---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMPolicySchedule.md
schema: 2.0.0
ms.assetid: C060E169-C585-411B-8F85-2E01DF5DDFDB
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicySchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicySchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicySchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMPolicySchedule

## SYNOPSIS
Returns the schedule for protection jobs.

## SYNTAX

### OffsetSchedule
```
Get-DPMPolicySchedule [-ProtectionGroup] <ProtectionGroup> [-OffsetSchedule] [<CommonParameters>]
```

### ShortTerm
```
Get-DPMPolicySchedule [-ProtectionGroup] <ProtectionGroup> [-ShortTerm] [<CommonParameters>]
```

### LongTerm
```
Get-DPMPolicySchedule [-ProtectionGroup] <ProtectionGroup> -LongTerm <LongTermLocation> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMPolicySchedule** cmdlet returns the schedule for protection jobs, such as synchronization, recovery point creation or shadow copy, and tape backups.

## EXAMPLES

### Example 1: Get a short-term synchronization schedule for a protection group
```
PS C:\>$PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMPolicySchedule -ProtectionGroup $PGroup -ShortTerm
```

The first command gets the protection group from the System Center 2016 - Data Protection Manager (DPM) server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the short-term synchronization schedule from the protection group in $PGroup.

### Example 2: Get a long-term synchronization schedule for a protection group
```
PS C:\>$PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMPolicySchedule -ProtectionGroup $PGroup -LongTerm
```

The first command gets the protection group from the DPM server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the long-term synchronization schedule from the protection group in $PGroup.

## PARAMETERS

### -LongTerm
Specifies the long term protection type for a protection group.

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

### -OffsetSchedule
Indicates that the cmdlet returns the schedule for protection jobs that use an offset schedule.

```yaml
Type: SwitchParameter
Parameter Sets: OffsetSchedule
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
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
Indicates that the cmdlet returns the schedule for short-term disk or short-term tape protection jobs.

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

### Schedule

## NOTES

## RELATED LINKS

[Set-DPMPolicySchedule](xref:SystemCenter2016/DataProtectionManager/v1/Set-DPMPolicySchedule.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMProtectionGroup.md)

