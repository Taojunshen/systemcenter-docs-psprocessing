---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CAD42FD4-F7E5-495F-BF66-14CC7EA82FC4
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMBackupWindow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMBackupWindow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMBackupWindow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-DPMBackupWindow

## SYNOPSIS
Sets the backup window settings for a protection group.

## SYNTAX

```
Set-DPMBackupWindow [-ProtectionGroup] <ProtectionGroup> [[-DaysOfWeek] <WeekDayType[]>]
 [-StartTime] <DateTime> [-DurationInHours] <Int32> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMBackupWindow** cmdlet sets the backup window for a System Center 2016 - Data Protection Manager (DPM) protection group when you create or modify a protection group.
The backup window of a protection group defines the time window during which scheduled backup jobs run.

This cmdlet works on modifiable protection groups.

## EXAMPLES

### Example 1: Set a backup window
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02" | Where {$_.FriendlyName -like "*ContosoPG02*"}
PS C:\> $MPGroup = Get-ModifiableProtectionGroup $PGroup
PS C:\> Set-DPMBackupWindow -ProtectionGroup $MPGroup -StartTime 16:00 -DurationInHours 12
```

The first command gets protection groups on the DPM server named DPMServer02.
This command passes the results to the **Where-Object** cmdlet.
That cmdlet drops all groups except ones that match the specified friendly name.
For more information, type `Get-Help Where-Object`.
The command stores the protection group in the $PGroup variable.

The second command gets the protection group from the $PGroup in a modifiable form, and then stores it in the $MPGroup variable.

The final command sets a backup window for the group in $MPGroup.
The window lasts 12 hours.
It starts at 4 PM.
The command does not specify days on which backup windows occur.
Therefore, they occur on every day.

### Example 2: Modify the backup window of an existing group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02" | Where {$_.FriendlyName -like "*ContosoPG02*"}
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $ProtectionGroup
PS C:\> $Schedule = Get-DPMPolicySchedule -PGroup $ModifiableProtectionGroup -ShortTerm | Where { $_.JobType -eq ""FullReplicationForApplication"" }
PS C:\> Set-DPMBackupWindow -ProtectionGroup $MPGroup -StartTime 16:00 -DurationInHours 12
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $MPGroup -DaysOfWeek $Schedule.WeekDays -TimesOfDay $Schedule.TimesOfDay -Schedule $Schedule
PS C:\> Set-DPMConsistencyCheckWindow -ProtectionGroup $MPGroup -StartTime 00:00 -DurationInHours 24
PS C:\> Set-DPMProtectionJobStartTime -ProtectionGroup $MPGroup -JobType ConsistencyCheck -StartTime 02:00 -MaximumDurationInHours 3
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $ModifiableProtectionGroup
```

This example modifies an existing protection group.
It sets a backup window and consistency check window.
For more information about this detailed example, see the related cmdlets that it includes.

The first command gets protection groups on the DPM server named DPMServer02.
This command passes the results to the **Where-Object** cmdlet.
The command stores the protection group in the $PGroup variable.

The second command gets the protection group from $PGroup in a modifiable form, and then stores it in the $MPGroup variable.

The third command gets the schedules for protection jobs, and then passes the results to **Where-Object**.
That cmdlet drops all schedules except ones that match the specified job type.
The command stores the schedules in the $Schedule variable.

The fourth command sets a backup window for the protection group in $MPGroup.

The fifth command sets a policy schedule for $MPGroup based on the value stored in $Schedule.

The sixth command sets the consistency check window for $MPGroup to start at midnight and last 24 hours.

The seventh command configures DPM consistency jobs to start at 2 AM and last up to three hours.

The final command saves all your changes to the protection group.

### Example 3: Create a protection group and specify a backup window
```
PS C:\>$PGroup = New-DPMProtectionGroup -DPMServerName "DPMServer02" -Name 'SQL protection group'
PS C:\> $PServer = Get-DPMProductionServer -DPMServerName "DPMCentral01"
PS C:\> $PObject = Get-DPMDatasource -ProductionServer $ProductionServer -Inquire | Where {$_.DatasourceName -eq 'db1'}
PS C:\> Add-DPMChildDatasource -ProtectionGroup $PGroup -ChildDatasource $PObject
PS C:\> Set-DPMProtectionType -ProtectionGroup $PGroup -ShortTerm disk
PS C:\> Set-DPMDatasourceDiskAllocation -Datasource $PObject -ProtectionGroup $PGroup
PS C:\> Set-DPMReplicaCreationMethod -ProtectionGroup $PGroup -Manual
PS C:\> $Schedule = Get-DPMPolicySchedule -ProtectionGroup $PGroup -ShortTerm | Where { $_.JobType -eq "FullReplicationForApplication" }
PS C:\> Set-DPMBackupWindow -ProtectionGroup $PGroup -DaysOfWeek @("Su", "Mo", "Tu", "Fr", "Sa") -StartTime 20:00 -DurationInHours 10
PS C:\> Set-DPMPolicySchedule -ProtectionGroup $PGroup -Schedule $sched -DaysOfWeek @("Su", "Mo", "Tu", "We", "Th", "Fr", "Sa") -TimesOfDay @('00:00', '04:00', '08:00', '12:00', '16:00', '20:00')
PS C:\> Set-DPMDatasourceProtectionOption -ProtectionGroup $PGroup -AutoConsistencyCheck $False
PS C:\> Set-DPMConsistencyCheckWindow -ProtectionGroup $PGroup -StartTime 22:00 -DurationInHours 12
PS C:\> Set-DPMProtectionJobStartTime -ProtectionGroup $PGroup -JobType ConsistencyCheck -StartTime 10:00 -MaximumDurationInHours 12
PS C:\> Set-DPMPolicyObjective -ProtectionGroup $PGroup -ColocateDatasources $False
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $PGroup
```

This example creates a protection group, and configures its backup window.
The ninth command sets the backup window that starts at 10 P.M.
The window lasts 10 hours.
The command specifies several days of the week in which the backup window falls.
For more information about this detailed example, see the related cmdlets that it includes.

## PARAMETERS

### -DaysOfWeek
Specifies an array of days of the week.

The acceptable values for this parameter are:

- Su
- Mo
- Tu
- We
- Th
- Fr
- Sa

The default value is all days.

```yaml
Type: WeekDayType[]
Parameter Sets: (All)
Aliases: 
Accepted values: Su, Mo, Tu, We, Th, Fr, Sa

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DurationInHours
Specifies the duration for which the backup window applies.
The window applies from the value of the *StartTime* parameter.
If the start time is 8 PM and the duration is 10 hours, the backup window for that day starts at 8 PM.
The window finishes at 6 AM the next day.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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
Specifies a protection group for which this cmdlet sets a backup window.
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

### -StartTime
Specifies the time of the day when the backup window for that day starts.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

[Add-DPMChildDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMChildDatasource.md)

[Get-DPMBackupWindow](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMBackupWindow.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMPolicySchedule](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMPolicySchedule.md)

[Get-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[New-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md)

[Set-DPMConsistencyCheckWindow](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMConsistencyCheckWindow.md)

[Set-DPMDatasourceDiskAllocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDiskAllocation.md)

[Set-DPMDatasourceProtectionOption](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceProtectionOption.md)

[Set-DPMPolicyObjective](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMPolicyObjective.md)

[Set-DPMPolicySchedule](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMPolicySchedule.md)

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

[Set-DPMProtectionJobStartTime](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionJobStartTime.md)

[Set-DPMProtectionType](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionType.md)

[Set-DPMReplicaCreationMethod](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMReplicaCreationMethod.md)

