---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 55D9169D-5B87-4D86-B42F-811E6AEF1E7A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Edit-SCOMMaintenanceSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Edit-SCOMMaintenanceSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Edit-SCOMMaintenanceSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Edit-SCOMMaintenanceSchedule

## SYNOPSIS
Edits an existing maintenance schedule.

## SYNTAX

```
Edit-SCOMMaintenanceSchedule [-ScheduleId] <Guid> [[-Name] <String>] [[-Recursive] <Boolean>]
 [[-Enabled] <Boolean>] [[-MonitoringObjects] <Guid[]>] [[-ActiveStartTime] <DateTime>]
 [[-ActiveEndDate] <DateTime>] [[-Duration] <Int32>] [[-ReasonCode] <MaintenanceModeReason>]
 [[-Comments] <String>] [[-FreqType] <Int32>] [[-FreqInterval] <Int32>] [[-FreqRecurrenceFactor] <Int32>]
 [[-FreqRelativeInterval] <Int32>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Edit-SCOMMaintenanceSchedule** cmdlet edits an existing maintenance schedule.
However, you cannot edit a schedule that is currently active.

When a resource is in maintenance mode, Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.
A maintenance schedule can be used to schedule a set of resources to go into maintenance mode.

You can use this cmdlet to edit schedules to run once, daily, weekly or monthly on a particular day or a day of the week.
You must pass the **ScheduleId** of an existing schedule that you want to edit.
All other parameters are optional; the specified parameters are overwritten.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ActiveEndDate
Specifies the end date and the end time when the schedule will stop.
If you don't specify this parameter, the schedule will continue to run until it is deleted or disabled.

For instance, if you want to create a schedule that should end on 1st May 2016 at 9:00 AM, you must specify "01-05-2016 09:00:00" as the ActiveEndDate.
You can pass a string specifying the time you want in your local time.
However, if you want to specify a UTC time, you need to specify a **DateTime** object with the DateTimeKind set to UTC.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveStartTime
Specifies the start date and the time when the schedule must go active.
For example, if you want a schedule that should begin from 1st May 2016 and must run at 9:00 AM, you must specify "01-05-2016 09:00:00" as the ActiveStartTime.
You can pass a string specifying the time you want in your local time.
However, if you want to specify a UTC time, you need to specify a **DateTime** object with the DateTimeKind.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comments
Specifies any human readable comments for a maintenance schedule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).The System Center Data Access service must be active on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

```yaml
Type: String[]
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

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a *PSCredential* object, use the Get-Credential cmdlet.
For more information, type `Get-Help Get-Credential`.If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Duration
Specifies the duration of the maintenance schedule.
The duration of a maintenance schedule is the time for which the maintenance schedule will last each time.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether the schedule will be enabled or disabled upon edit.
If you set this to false, the schedule will be disabled.
You can also use the Enable-SCOMMaintenanceSchedule and Disable-SCOMMaintenanceSchedule to do this.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqInterval
Specifies the day that the job is run.
This is mandatory if the schedule is anything other than OnceRecurrence schedule.
The value depends on the value of *FreqType* as indicated in the following list:

- 1 (once). Frequency interval is unused.
- 4 (daily). Every frequency interval days. 
- 8 (weekly). The *FreqInterval* parameter is one or more of the following (combined with an OR logical operator): 

---- 1 = Sunday
---- 2 = Monday
---- 4 = Tuesday
---- 8 = Wednesday
---- 16 = Thursday
---- 32 = Friday
---- 64 = Saturday

- 16 (monthly). On the frequency interval day of the month. 
- 32 (monthly relative). The *FreqInterval* parameter is one of the following values: 

---- 1 = Sunday
---- 2 = Monday
---- 3 = Tuesday
---- 4 = Wednesday
---- 5 = Thursday
---- 6 = Friday
---- 7 = Saturday
---- 8 = Day
---- 9 = Weekday
---- 10 = Weekend day

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqRecurrenceFactor
Number of weeks or months between the scheduled run of the job.
*FreqRecurrenceFactor* is used only if the *FreqType* paramter is set to 8, 16, or 32.
The *FreqRecurrenceFactor* parameter is an integer, with a default value of 0.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 12
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqRelativeInterval
Specifies the schedule when the *FreqType* parameter is set to 32 (monthly relative).
This parameter can be one of the following values: 

- 1 (First)
- 2 (Second)
- 4 (Third)
- 8 (Fourth)
- 16 (Last)

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 13
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqType
Specifies when the job is to be executed.
This parameter can be one of the following values:

- 1 (once) 
- 4 (daily) 
- 8 (weekly) 
- 16 (monthly) 
- 32 (Monthly, relative to parameter *FreqInterval*).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringObjects
Specifies an array of GUIDs representing monitoring objects that this cmdlet places into maintenance mode.
Specifies an array of monitoring objects GUIDS that is placed into maintenance mode.
To specify a monitoring object that the schedule places into maintenance mode, you must pass the ID attribute of the monitoring object.
If you want to retain some of the existing members, those also must be specified.

You can specify one or more monitoring objects for a schedule.
However, you cannot edit a schedule that does not have any monitoring object.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the schedule.

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

### -ReasonCode
Specifies the reason code for a maintenance schedule that specifies the reason for the maintenance window.

```yaml
Type: MaintenanceModeReason
Parameter Sets: (All)
Aliases: 
Accepted values: PlannedOther, UnplannedOther, PlannedHardwareMaintenance, UnplannedHardwareMaintenance, PlannedHardwareInstallation, UnplannedHardwareInstallation, PlannedOperatingSystemReconfiguration, UnplannedOperatingSystemReconfiguration, PlannedApplicationMaintenance, UnplannedApplicationMaintenance, ApplicationInstallation, ApplicationUnresponsive, ApplicationUnstable, SecurityIssue, LossOfNetworkConnectivity

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recursive
Indicates that the schedule is applicable to the top level resource or to all the contained resources as well.
If you set this parameter to false, only the specified resource will go into maintenance mode when the schedule is run.
If this is set to true, the specified resource and all resources that have a containment relationship with this resource will also go into maintenance mode.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.

```yaml
Type: Connection[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleId
Specifies the GUID of the schedule that this cmdlet edits.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
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

[Disable-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Disable-SCOMMaintenanceSchedule.md)

[Enable-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Enable-SCOMMaintenanceSchedule.md)

[Get-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceSchedule.md)

[New-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMMaintenanceSchedule.md)

[Remove-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMMaintenanceSchedule.md)

[Stop-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Stop-SCOMMaintenanceSchedule.md)

[Update-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMMaintenanceSchedule.md)

