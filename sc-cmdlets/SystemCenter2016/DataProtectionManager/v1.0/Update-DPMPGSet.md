---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMPGSet.md
schema: 2.0.0
ms.assetid: EB06672B-B135-49EB-918D-95BB641BA7B6
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Update-DPMPGSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Update-DPMPGSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Update-DPMPGSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-DPMPGSet

## SYNOPSIS
Updates and saves changes to a protection group set.

## SYNTAX

### AllParams (Default)
```
Update-DPMPGSet [-AllowDifferentRetentionPeriods] [-PGSet] <PGSet> [-Name] <String>
 [-WritePeriodUnit] <TimeUnit> [-WritePeriodValue] <UInt32> [-ExpiryToleranceUnit] <TimeUnit>
 [-ExpiryToleranceValue] <UInt32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllowDiffRetnPeriodsFlag
```
Update-DPMPGSet [-AllowDifferentRetentionPeriods] [-PGSet] <PGSet> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemovePG
```
Update-DPMPGSet [-PGSet] <PGSet> [-Remove] <ProtectionGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ChangeName
```
Update-DPMPGSet [-PGSet] <PGSet> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ChangeTimePeriods
```
Update-DPMPGSet [-PGSet] <PGSet> [-WritePeriodUnit] <TimeUnit> [-WritePeriodValue] <UInt32>
 [-ExpiryToleranceUnit] <TimeUnit> [-ExpiryToleranceValue] <UInt32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AddPG
```
Update-DPMPGSet [-PGSet] <PGSet> [-Add] <ProtectionGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-DPMPGSet** cmdlet updates and saves changes to a System Center 2016 - Data Protection Manager (DPM) protection group set.
A DPM protection group is a collection of protection groups that you collocate on the same tape.

## EXAMPLES

### Example 1: Update write period and expiry tolerance
```
PS C:\>$PGSet = Get-DPMPGSet -DPMServerName "DPMServer07"
PS C:\> Update-DPMPGSet -PGSet $PGSet[0] -Name "PGSset3" -WritePeriodUnit day -WritePeriodValue 60 -ExpiryToleranceUnit Day -ExpiryToleranceValue 10
```

This example updates the first protection group set from protection group sets on the on the server DPMServer07 with values for write period and expiry tolerance.

The first command uses the **Get-DPMPGSet** cmdlet to get the protection group sets for the specified server and stores them in the $PGSet variable.

The second command specifies the first member of $PGSet by using standard array notation.
The command updates values for write period and expiry tolerance.

### Example 2: Add a protection group to a protection group set
```
PS C:\>$PGSet = Get-DPMPGSet -DPMServerName "DPMServer07"
PS C:\> $PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07" | where {($_.friendlyname) -match "PG1" }
PS C:\> Update-DPMPGSet -PGSet $PGSet[0] -Add $PGroup
```

This example adds a protection group from DPMServer07 to the first protection group set on that DPM server.

The first command uses the **Get-DPMPGSet** cmdlet to get the protection group sets for the specified server and stores them in the $PGSet variable.

The second command uses the **Get-DPMProtectionGroup** cmdlet to get a protection group from the specified DPM server that has a name that contains PG1, and then stores it in the $PGroup variable.

The third command specifies the first member of the $PGSet variable by using standard array notation.
The command updates that set to contain the protection group stored in $PGroup.

### Example 3: Remove a protection group from a protection group set
```
PS C:\>$PGSet = Get-DPMPGSet -DPMServerName "DPMServer07"
PS C:\> $PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07" | where { ($_.friendlyname) -match "PG1" }
PS C:\> Update-DPMPGSet -PGSet $PGSet[0] -Remove $PGroup
```

This example removes the first protection group set from the list of protection group sets on the DPM server TestingServer.

The first command uses the **Get-DPMPGSet** cmdlet to get the protection group sets for the specified server and stores them in the $PGSet variable.

The second command uses the **Get-DPMProtectionGroup** cmdlet to get a protection group from the specified DPM server that has a name that contains PG1, and then stores it in the $PGroup variable.

The third command specifies the first member of $PGSet by using standard array notation.
The command updates that set to no longer contain the protection group stored in $PGroup.

## PARAMETERS

### -Add
Specifies a protection group.
The cmdlet adds this protection group to the protection group set.

```yaml
Type: ProtectionGroup
Parameter Sets: AddPG
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowDifferentRetentionPeriods
Indicates that protection groups with different retention periods can be part of the same protection group set.

```yaml
Type: SwitchParameter
Parameter Sets: AllParams
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: AllowDiffRetnPeriodsFlag
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryToleranceUnit
Specifies the measurement unit for expiry tolerance.
The acceptable values for this parameter are:

- Day 
- Week 
- Month 
- Year

```yaml
Type: TimeUnit
Parameter Sets: AllParams, ChangeTimePeriods
Aliases: 
Accepted values: Invalid, Day, Week, Month, Year

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryToleranceValue
Specifies the maximum length of time for which an expired recovery point remains on a tape before DPM marks the tape as expired.

```yaml
Type: UInt32
Parameter Sets: AllParams, ChangeTimePeriods
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a new name for the protection group set.

```yaml
Type: String
Parameter Sets: AllParams, ChangeName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PGSet
Specifies a protection group set that this cmdlet updates.
To obtain a protection group set object, use the Get-DPMPGSet cmdlet.

```yaml
Type: PGSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Remove
Specifies a protection group.
The cmdlet removes this protection group from the protection group set.

```yaml
Type: ProtectionGroup
Parameter Sets: RemovePG
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WritePeriodUnit
Specifies the measurement unit for the write period.
The acceptable values for this parameter are:

- Day 
- Week 
- Month 
- Year

```yaml
Type: TimeUnit
Parameter Sets: AllParams, ChangeTimePeriods
Aliases: 
Accepted values: Invalid, Day, Week, Month, Year

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WritePeriodValue
Specifies the length of time for which a tape is available for writing new backups.
DPM marks the tape as Offsite Ready after this interval.

```yaml
Type: UInt32
Parameter Sets: AllParams, ChangeTimePeriods
Aliases: 

Required: True
Position: 3
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

[Get-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMPGSet.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroup.md)

[New-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/v1.0/New-DPMPGSet.md)

[Remove-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/v1.0/Remove-DPMPGSet.md)

