---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 318EAD8D-A317-42C6-B39D-04D5C9E7FE7C
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWJobSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWJobSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWJobSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCDWJobSchedule

## SYNOPSIS
Sets the schedule for a data warehouse job.

## SYNTAX

```
Set-SCDWJobSchedule [-JobName] <String> [-DailyFrequency <TimeSpan>] [-DailyStart <DateTime>]
 [-WeeklyStart <DateTime>] [-ScheduleType <ScheduleTypeEnum>]
 [-WeeklyFrequency <System.Collections.Generic.List`1[System.String]>] [-ComputerName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCDWJobSchedule** cmdlet configures the schedule for data warehouse jobs.
You can configure the schedule on a daily basis or on a weekly basis.

For a daily schedule, you must specify the time interval at which the job recurs (**DailyFrequency**) and the time of day at which this recurrence starts (**DailyStart**).

For a weekly schedule, you must specify the time of day (**WeeklyStart**) at which the job should run and the list of days for which this start time is effective (**WeeklyFrequency**).

## EXAMPLES

### Example 1: Schedule a job to run every 30 minutes
```
PS C:\>Set-SCDWJobSchedule -ComputerName "serverDW72" -JobName "Transform.Common" -DailyFrequency 00:30 -DailyStart 00:00
```

This command sets the schedule for the `Transform.Common` job, to run every 30 minutes starting at midnight.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
You can omit this parameter only if the System Center Data Access Service is running on the same computer that has Service Manager installed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DailyFrequency
Specifies the recurrence frequency of the scheduled job for a daily schedule.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DailyStart
Specifies the time at which the scheduled job will start for a daily schedule.
Specify the start time in the hh:mm format.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Specifies the Data Warehouse job for which the schedule is being configured.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleType
Specifies the schedule as Daily or Weekly.
The default value is Daily.

```yaml
Type: ScheduleTypeEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeklyFrequency
Specifies the days on which the job will run for a weekly schedule.
The job will start according to the time that is specified by the **WeeklyStart** parameter.
Use a comma to separate multiple days (for example: Tuesday, Thursday).

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeklyStart
Specifies the time of day at which the job will start for a weekly schedule (for example: 8:00, 16:00).
The job will begin at this time on the days that are specified by the **WeeklyFrequency** parameter.
Specify the start time in the hh:mm format.

```yaml
Type: DateTime
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES
* Valid schedule parameter combinations are as follows:

  **-DailyFrequency**`HH:MM`**â€"DailyStart**`HH:MM`**-ScheduleType Daily**

  **-WeeklyFrequency**`Day(s)`**â€"WeeklyStart**`HH:MM`, **-ScheduleType Weekly**

  For the weekly frequency, specify the day of the week such as `Monday`.
For multiple days, separate with commas such as `Monday, Tuesday, Wednesday`.
You cannot configure a job with both a weekly schedule and a daily schedule.

## RELATED LINKS

[Disable-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobSchedule.md)

[Enable-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobSchedule.md)

[Get-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobSchedule.md)

