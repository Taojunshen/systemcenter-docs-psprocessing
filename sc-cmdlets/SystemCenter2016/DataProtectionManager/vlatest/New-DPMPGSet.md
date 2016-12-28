---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 33F037D7-D8CA-4040-99FC-4DE4C12DBB7A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMPGSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMPGSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMPGSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMPGSet

## SYNOPSIS
Creates a DPM protection group set.

## SYNTAX

```
New-DPMPGSet [[-DPMServerName] <String>] [-AllowDifferentRetentionPeriods] [-Name] <String>
 [[-PGList] <ProtectionGroup[]>] [[-WritePeriodUnit] <TimeUnit>] [[-WritePeriodValue] <UInt32>]
 [[-ExpiryToleranceUnit] <TimeUnit>] [[-ExpiryToleranceValue] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMPGSet** cmdlet creates a System Center 2016 - Data Protection Manager (DPM) protection group set.
A DPM protection group is a collection of protection groups that you collocate on the same tape.

## EXAMPLES

### Example 1: Create a protection group set
```
PS C:\>$PGroups = Get-DPMProtectionGroup -DPMServerName "DPMServer07" | where {($_.friendlyname) -match "PG1" -or ($_.friendlyname) -match "PG2"} 
PS C:\> New-DPMPGSet -Name "PGSET2" -PGList $PGroups
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to get protection groups that have names that contain either PG1 or PG2, and then stores them in the $PGroups variable.

The second command creates a protection set named PGSET2 that contains the protection groups stored in $PGroups.

## PARAMETERS

### -AllowDifferentRetentionPeriods
Indicates that protection groups with different retention periods can be part of the same protection group set.

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

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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
Parameter Sets: (All)
Aliases: 
Accepted values: Invalid, Day, Week, Month, Year

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryToleranceValue
Specifies the maximum length of time for which an expired recovery point remains on a tape before DPM marks the tape as expired.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the protection group set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PGList
Specifies an array of protection groups to add to the protection group set.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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
Parameter Sets: (All)
Aliases: 
Accepted values: Invalid, Day, Week, Month, Year

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WritePeriodValue
Specifies the length of time for which a tape is available for writing new backups.
DPM marks the tape as Offsite Ready after this interval.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMPGSet.md)

[Remove-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMPGSet.md)

[Update-DPMPGSet](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMPGSet.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

