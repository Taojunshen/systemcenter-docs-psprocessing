---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: c853d66b-7c64-4ca8-bb00-5b4b921ca6a9
schema: 2.0.0
ms.assetid: F4BB1889-D2BF-4C7A-8609-561430DE600A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/New-SCOMMaintenanceSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/New-SCOMMaintenanceSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/New-SCOMMaintenanceSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCOMMaintenanceSchedule

## SYNOPSIS
Creates a maintenance schedule.

## SYNTAX

```
New-SCOMMaintenanceSchedule [-Name] <String> [-Recursive] [-Enabled] [-MonitoringObjects] <Guid[]>
 [-ActiveStartTime] <DateTime> [[-ActiveEndDate] <DateTime>] [-Duration] <Int32>
 [-ReasonCode] <MaintenanceModeReason> [[-Comments] <String>] [-FreqType] <Int32> [[-FreqInterval] <Int32>]
 [[-FreqRecurrenceFactor] <Int32>] [[-FreqRelativeInterval] <Int32>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCOMMaintenanceSchedule** cmdlet creates a maintenance schedule.

When a resource is in maintenance mode, Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.
A maintenance schedule can be used to schedule a set of resources to go into maintenance mode.

You could use this cmdlet to create schedules that run once, daily, weekly or monthly on a particular day or a day of the week.
This cmdlet will return the GUID of the created schedule.

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
Specifies the end date and the end time when the schedule should stop executing.
If this parameter is not specified, the schedule will continue to run for ever (or until it is deleted or disabled).

For instance, if you want to create a schedule that should end on 1st May 2016 at 9:00 AM, you must specify "01-05-2016 09:00:00" as the ActiveEndDate.
You can pass a string specifying the time you want in your local time.
However, if you want to specify a UTC time, you should specify a **DateTime** object with the DateTimeKind set to UTC.

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

### -ActiveStartTime
Specifies the start date and the time when the schedule must go active.
For instance, if you want to create a schedule that should begin from 1st May 2016 and must run at 9:00 AM, you must specify "01-05-2016 09:00:00" as the ActiveStartTime.
You can pass a string specifying the time you want in your local time.
However, if you want to specify a UTC time, you need to specify a **DateTime** object with the DateTimeKind set to UTC.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be active on the computer.
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
The duration of a maintenance schedule is the time for which the maintenance schedule will last.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: DurationInMinutes

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether the schedule will be enabled or disabled upon creation.
If you set this to false, the schedule will be created but it will be disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqInterval
Specifies when the job is to be executed.
This parameter can be one of the following values:

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
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqRecurrenceFactor
Number of weeks or months between the scheduled execution of the job.
*FreqRecurrenceFactor* is used only if the *FreqType* paramter is set to 8, 16, or 32.
The *FreqRecurrenceFactor* parameter is an integer, with a default value of 0.

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

### -FreqRelativeInterval
Day that the job is executed.
This is mandatory if the schedule is anything other than **OnceRecurrence** schedule.
The value depends on the value of **FreqType**. 

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
Position: 12
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreqType
Specifies when the job is to be executed.
The acceptable values for this parameter are:

- 1 (once) 
- 4 (daily) 
- 8 (weekly) 
- 16 (monthly) 
- 32 (Monthly, relative to parameter *FreqInterval*)

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringObjects
Specifies an array of monitoring objects GUIDS which will be put to maintenance mode.
To specify a monitoring object which the created schedule will put into maintenance mode, you must pass the ID attribute of the monitoring object.

You can specify one or more monitoring objects for a schedule.
However, you cannot create a schedule without any monitoring object.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies name of the schedule that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReasonCode
Specifies the reason code for a maintenance schedule that specifies the reason for the maintenance window.

The acceptable values for this parameter are:

- PlannedOther
- UnplannedOther
- PlannedHardwareMaintenance
- UnplannedHardwareMaintenance
- PlannedHardwareInstallation
- UnplannedHardwareInstallation
- PlannedOperatingSystemReconfiguration
- UnplannedOperatingSystemReconfiguration
- PlannedApplicationMaintenance
- UnplannedApplicationMaintenance
- ApplicationInstallation
- ApplicationUnresponsive
- ApplicationUnstable
- SecurityIssue
- LossOfNetworkConnectivity

```yaml
Type: MaintenanceModeReason
Parameter Sets: (All)
Aliases: 
Accepted values: PlannedOther, UnplannedOther, PlannedHardwareMaintenance, UnplannedHardwareMaintenance, PlannedHardwareInstallation, UnplannedHardwareInstallation, PlannedOperatingSystemReconfiguration, UnplannedOperatingSystemReconfiguration, PlannedApplicationMaintenance, UnplannedApplicationMaintenance, ApplicationInstallation, ApplicationUnresponsive, ApplicationUnstable, SecurityIssue, LossOfNetworkConnectivity

Required: True
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recursive
Indicates whether the schedule is applicable to the top level resource or to all the contained resources.
If the recursive parameter is set to false, only the specified resource will go into maintenance mode when the schedule is run.
If this is set to true, the specified resource and all resources that have a containment relationship with this resource will also go into maintenance mode.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

[Disable-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Disable-SCOMMaintenanceSchedule.md)

[Edit-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Edit-SCOMMaintenanceSchedule.md)

[Enable-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Enable-SCOMMaintenanceSchedule.md)

[Get-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Get-SCOMMaintenanceSchedule.md)

[Remove-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Remove-SCOMMaintenanceSchedule.md)

[Stop-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Stop-SCOMMaintenanceSchedule.md)

[Update-SCOMMaintenanceSchedule](xref:OperationsManager/v1/Update-SCOMMaintenanceSchedule.md)

[Get-SCOMManagementGroup](xref:OperationsManager/v1/Get-SCOMManagementGroup.md)

