---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMPolicySchedule.md
schema: 2.0.0
ms.assetid: 42A48949-2B51-4848-934A-1447B2D698F4
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Set-DPMPolicySchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Set-DPMPolicySchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Set-DPMPolicySchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMPolicySchedule

## SYNOPSIS
Sets the schedule for protection jobs.

## SYNTAX

### ModifySchedule
```
Set-DPMPolicySchedule [-ProtectionGroup] <ProtectionGroup> [-Schedule] <Schedule> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### OffsetSchedule
```
Set-DPMPolicySchedule [-ProtectionGroup] <ProtectionGroup> [-PassThru] [-OffsetInMinutes] <Int32> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### CheckDataIntegrity
```
Set-DPMPolicySchedule [-ProtectionGroup] <ProtectionGroup> [-PassThru] [-JobType] <ProtectionJobType> [-Remove]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMPolicySchedule** cmdlet sets the schedule for protection jobs in System Center 2016 - Data Protection Manager (DPM).

DPM sets default schedules automatically if you specify the protection objective by using the Set-DPMPolicyObjective cmdlet.
To change the default schedules, run the Get-DPMPolicySchedule cmdlet followed by the **Set-DPMPolicySchedule** cmdlet.

This cmdlet includes the following dynamic parameters that you can use to define schedules:

For express full and shadow copy schedule, specify the following parameters, as in the following examples:

\[-TimesOfDay\] \<TimesOfDay\> \[-DaysOfWeek\]\<DaysOfWeek\>
`-TimesOfDay "6:00 AM"`
`-TimesOfDay "12:00 AM" -DaysOfWeek We,Th`

For monthly, half-yearly, and yearly archive schedules, specify the following parameters, as in the following example:

\[-StartTime\] \<StartTime\> \[-RelativeInterval \<RelativeInterval\>\] \[-DaysOfWeek \<DaysOfWeek\>\]
`-StartTime "1/1/2003 6:00 AM" -RelativeInterval First -DaysOfWeek Sa`

For daily archive schedule, specify the following parameter, as in the following example:

\[-TimeOfDay\] \<TimeOfDay\>
`-StartTime "6:00 AM"`

For quarterly archive schedule, specify the following parameter, as in the following example:

\[-StartTime\] \<StartTime\>
`-StartTime "1/1/2003 6:00 AM"`

## EXAMPLES

### Example 1: Create a synchronization schedule for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $ShadowCopysch = Get-PolicySchedule $PGroup -ShortTerm
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $PGroup -Schedule $ShadowCopysch -DaysOfWeek mo -TimesOfDay 02:00
```

The first command gets the protection group from the DPM server named DPMServer02, and then stores the result in the $PGroup variable.

The second command gets the short-term schedule for performing integrity checks from the protection group in $PGroup, and then stores the result in the $ShadowCopysch variable.

The third command sets synchronization to run at 2:00 AM every Monday.

### Example 2: Change a synchronization schedule for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -dpmservername "ContosoDPM1"
PS C:\> $Schedule = Get-DPMPolicySchedule $PGroup[1] -longterm
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup[1]
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -Schedule $Schedule[2] -TimeOfDay "07:00 PM"
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $MPGroup
```

The first command gets protection groups from the DPM server named ContosoDPM1, and then stores them in the $PGroup variable.

The second command gets the long-term synchronization schedule for the second protection group in $PGroup, and then stores the result in the $Schedule variable.

The third command gets the second protection group in in $PGroup, and then stores the group in the $MPGroup variable.
The command gets the protection group in editable format.

The fourth command sets the policy schedule for the third schedule in $Schedule to run at 7:00 PM daily.

The fifth command uses the **Set-DPMProtectionGroup** cmdlet to save your changes.

### Example 3: Schedule an integrity check for a DPM server
```
PS C:\>$PGroup = Get-DPMProtectionGroup "ContosoDPM1"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -JobType CheckDataIntegrity -DaysOfWeek mo -TimesOfDay 18:00
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $MPGroup
```

The first command gets the protection group from the DPM server named ContosoDPM1, and then stores it in the $PGroup variable.

The second command gets the protection group in $PGroup, and then stores it in the $MPGroup variable in editable format.

The third command schedules a data integrity check to run on the server every Monday at 6:00 PM.

The fourth command uses the **Set-DPMProtectionGroup** cmdlet save your changes.

### Example 4: Create online backup and retention schedules for a protection group
```
PS C:\>$RRList = @()
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 18, Days)
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 10, Weeks)
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 6, Month)
PS C:\> $RRList += (New-Object -TypeName Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.RetentionRange -ArgumentList 5, Years)
PS C:\> $PGroup = Get-ProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-ModifiableProtectionGroup -ProtectionGroup $PGroup[0]
PS C:\> Set-DPMPolicyObjective -ProtectionGroup $MPGroup -OnlineRetentionRangeList $RRList
PS C:\> $onlineSch = Get-DPMPolicySchedule -ProtectionGroup $MPGroup -LongTerm Online
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -Schedule $nlineSchedule[0] -TimesOfDay 02:00
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -Schedule $OnlineSchedule[1] -TimesOfDay 02:00 -DaysOfWeek Sa,Su -Interval 1
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -Schedule $OnlineSchedule[2] -TimesOfDay 02:00 -RelativeIntervals First,Third -DaysOfWeek Sa
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -Schedule $OnlineSchedule[3] -TimesOfDay 02:00 -DaysOfMonth 2,5,8,9 -Months Jan,Jul
```

This example creates online backup and retention schedules for a protection group.

The first eight commands set the online policy objective for the protection group from the DPM server named DPMServer02.
For more information, see the **Set-DPMPolicyObjective** cmdlet.

The ninth command gets the online schedules for the protection group stored in $MPGroup, and then stores those schedules in the $OnlineSchedule variable.

The tenth command updates daily backup/retention online schedule.

The eleventh command updates weekly retention online schedule.

The twelfth command updates monthly retention online schedule.

The thirteenth command updates yearly retention online schedule.

## PARAMETERS

### -JobType
Indicates the type of job for which this cmdlet sets options.
The only valid value for this parameter is ConsistencyCheck.

```yaml
Type: ProtectionJobType
Parameter Sets: CheckDataIntegrity
Aliases: 
Accepted values: CheckDataIntegrity

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OffsetInMinutes
Specifies the time, in minutes, by which to offset the start time of a job.

```yaml
Type: Int32
Parameter Sets: OffsetSchedule
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
Specifies a protection group object to which this schedule applies.
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

### -Remove
Indicates that the cmdlet removes a schedule for a protection operation.

```yaml
Type: SwitchParameter
Parameter Sets: CheckDataIntegrity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Schedule
Specifies a schedule object.
A schedule describes the recurrence of a backup job.
Each job type has one schedule, which DPM triggers.
You create a default schedule by using the **Set-DPMPolicyObjective** cmdlet.

Customize a default schedule by using **Get-DPMPolicySchedule**, and then pass the schedule to **Set-DPMPolicySchedule**.

```yaml
Type: Schedule
Parameter Sets: ModifySchedule
Aliases: 

Required: True
Position: 2
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

### ProtectionGroup

## NOTES

## RELATED LINKS

[Get-DPMPolicySchedule](xref:DataProtectionManager/v1/Get-DPMPolicySchedule.md)

[Get-DPMPolicyObjective](xref:DataProtectionManager/v1/Get-DPMPolicyObjective.md)

[Set-DPMPolicyObjective](xref:DataProtectionManager/v1/Set-DPMPolicyObjective.md)

