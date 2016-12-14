---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMPolicyObjective.md
schema: 2.0.0
ms.assetid: B245C387-1666-4A33-8D46-536A9CF8DC73
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMPolicyObjective.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMPolicyObjective.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMPolicyObjective.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMPolicyObjective

## SYNOPSIS
Sets the policy objective for a protection group.

## SYNTAX

### ShortTermDisk (Default)
```
Set-DPMPolicyObjective [-RetentionRangeDays] <Int32> [-ProtectionGroup] <ProtectionGroup>
 [[-SynchronizationFrequencyMinutes] <Int32>] [-BeforeRecoveryPoint] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ShortTermTape
```
Set-DPMPolicyObjective [-RetentionRangeInWeeks] <Int32> [-ShortTermBackupFrequency] <BackupFrequency>
 [-ProtectionGroup] <ProtectionGroup> [-CreateIncrementals] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LongTermTape
```
Set-DPMPolicyObjective [-LongTermBackupFrequency] <BackupFrequency> [-ProtectionGroup] <ProtectionGroup>
 [-RetentionRange] <RetentionRange> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LongTermTapeCustom
```
Set-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> [-RetentionRangeList] <RetentionRange[]>
 [-FrequencyList] <Int32[]> [-GenerationList] <GenerationType[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LongTermCloud
```
Set-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> [-OnlineRetentionRange] <Int32> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LongTermCloudGFS
```
Set-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> [-OnlineRetentionRangeList] <RetentionRange[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ColocateDatasources
```
Set-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> [-ColocateDatasources] <Boolean> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AlertThresholdInDays
```
Set-DPMPolicyObjective [-ProtectionGroup] <ProtectionGroup> [-AlertThresholdInDays] <Int32> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMPolicyObjective** cmdlet sets the policy objective for a System Center 2016 - Data Protection Manager (DPM) protection group.
You can set the policy to back up to disk or tape and specify a retention range for the protection group.

If you specify the protection objective by using the **Set-DPMPolicyObjective** cmdlet, DPM sets default schedules automatically.
To change the default schedules, use the Get-DPMPolicySchedule cmdlet followed by the **Set-DPMPolicySchedule** cmdlet.

## EXAMPLES

### Example 1: Set the policy objective for a protection group
```
PS C:\>$PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-ModifiableProtectionGroup $PGroup[0]
PS C:\> Set-DPMPolicyObjective -ProtectionGroup $MPGroup -RetentionRangeInDays 10 -SynchronizationFrequency 360
```

The first command gets the protection group objects from the DPM server named DPMServer02, and then stores them in the $PGroup variable.

The second command uses standard array notation to specify the second member of the $PGroup array in editable format, and stores the protection group in the $MPGroup variable.

The third command sets the policy objective for the protection group in $MPGroup to a retention range of 10 days and synchronization frequency of 6 hours, which is 360 minutes.

### Example 2: Set the retention range for a DPM server
```
PS C:\>$Rr = New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 1,"months"
PS C:\> $PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-ModifiableProtectionGroup $PGroup[0]
PS C:\> Set-DPMPolicyObjective -ProtectionGroup $MPGroup -RetentionRange 360 -LongTermBackupFrequency Weekly
```

The first command creates a **RetentionRange** object, and then stores it in the $Rr variable.

The second command gets protection groups from the DPM server named DPMServer02, and then stores them in the $PGroup variable.

The third command uses standard array notation to specify the first member of the $PGroup array in editable form, and stores the editable protection group in the $MPGroup variable.

The fourth command sets the retention range for the protection group to 360 days and the long-term backup frequency to weekly.

### Example 3: Set a retention range
```
PS C:\>$PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-ModifiableProtectionGroup $PGroup[0]
PS C:\> Set-DPMPolicyObjective -RetentionRangeInWeeks 12 -ShortTermBackupFrequency Daily -ProtectionGroup $MPGroup
```

This example shows another way to set a retention range for a DPM server.

The first command gets protection groups from the DPM server named DPMServer02, and then stores them in the $PGroup variable.

The second command uses standard array notation to specify the first member of the $PGroup array in editable form, and stores the editable protection group in the $MPGroup variable.

The third command sets the retention range for the protection group to 12 weeks and the short-term backup frequency to daily.

### Example 4: Set the retention ranges for online protection
```
PS C:\>$RRList = @()
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 180, Days)
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 104, Weeks)
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 60, Month)
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 10, Years)
PS C:\> $PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-ModifiableProtectionGroup -ProtectionGroup $PGroup[0]
PS C:\> Set-DPMPolicyObjective -ProtectionGroup $MPGroup -OnlineRetentionRangeList $RRList
```

The first command creates a **RetentionRange** object array stored in the $RRlist variable.

The second, third, fourth, and fifth commands create **RetentionRange** objects, and add them to $RRlist.

The sixth command gets protection groups from the DPM server named DPMServer02, and then stores them in the $PGroup variable.

The seventh command uses standard array notation to specify the first member of the $PGroup array in editable form, and stores the editable protection group in the $MPGroup variable.

The final command sets the online retention ranges for the protection group and the long-term online backup frequency to daily.

## PARAMETERS

### -AlertThresholdInDays
Specifies the number of days after the most recent backup that DPM waits before it raises an alert.

```yaml
Type: Int32
Parameter Sets: AlertThresholdInDays
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BeforeRecoveryPoint
Indicates that DPM runs synchronization before it creates recovery points.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTermDisk
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ColocateDatasources
Indicates whether DPM enables colocation.

```yaml
Type: Boolean
Parameter Sets: ColocateDatasources
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateIncrementals
Indicates that DPM creates incremental backups.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTermTape
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrequencyList
Specifies an array of backup frequencies that the three protection objectives define.

The acceptable values for this parameter are:

- 6.
Yearly 
- 5.
Half yearly 
- 4.
Quarterly 
- 3.
Monthly 
- 2.
Biweekly 
- 1.
Weekly 
- 0.
Daily

```yaml
Type: Int32[]
Parameter Sets: LongTermTapeCustom
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerationList
Specifies an array of generations that the three protection objectives define.

The acceptable values for this parameter are:

- GreatGrandfather
- Grandfather
- Father
- Son

```yaml
Type: GenerationType[]
Parameter Sets: LongTermTapeCustom
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LongTermBackupFrequency
Specifies the backup frequency for long-term protection.

The acceptable values for this parameter are:

- Daily 
- Weekly 
- BiWeekly 
- Monthly 
- Quarterly 
- HalfYearly 
- Yearly

```yaml
Type: BackupFrequency
Parameter Sets: LongTermTape
Aliases: 
Accepted values: Daily, Weekly, BiWeekly, Monthly, Quarterly, HalfYearly, Yearly

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlineRetentionRange
Specifies the retention range for online protection.

```yaml
Type: Int32
Parameter Sets: LongTermCloud
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlineRetentionRangeList
Specifies an array of retention periods that define the retention ranges for online protection.

```yaml
Type: RetentionRange[]
Parameter Sets: LongTermCloudGFS
Aliases: 

Required: True
Position: 2
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
Specifies a protection group for which this cmdlet sets a policy objective.
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

### -RetentionRange
Specifies the duration for which DPM keeps data on tape for long-term protection.

```yaml
Type: RetentionRange
Parameter Sets: LongTermTape
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionRangeDays
Specifies the number of days for which DPM keeps a replica.

```yaml
Type: Int32
Parameter Sets: ShortTermDisk
Aliases: RetentionRangeInDays

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionRangeInWeeks
Specifies the number of weeks for which DPM keeps a replica.

```yaml
Type: Int32
Parameter Sets: ShortTermTape
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionRangeList
Specifies an array of retention periods that the three protection objectives define.

```yaml
Type: RetentionRange[]
Parameter Sets: LongTermTapeCustom
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShortTermBackupFrequency
Specifies the backup frequency for short-term protection.

The acceptable values for this parameter are:

- Daily 
- Weekly 
- BiWeekly 
- Monthly 
- Quarterly 
- HalfYearly 
- Yearly

```yaml
Type: BackupFrequency
Parameter Sets: ShortTermTape
Aliases: 
Accepted values: Daily, Weekly, BiWeekly, Monthly, Quarterly, HalfYearly, Yearly

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SynchronizationFrequencyMinutes
Specifies the frequency of synchronization, in minutes.

```yaml
Type: Int32
Parameter Sets: ShortTermDisk
Aliases: SynchronizationFrequency
Accepted values: 15, 30, 45, 60, 120, 240, 360, 720, 1440

Required: False
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

### Schedule

## NOTES

## RELATED LINKS

[Get-DPMPolicyObjective](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicyObjective.md)

[Get-DPMPolicySchedule](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMPolicySchedule.md)

[Set-DPMPolicySchedule](xref:SystemCenter2016/DataProtectionManager/v1/Set-DPMPolicySchedule.md)

