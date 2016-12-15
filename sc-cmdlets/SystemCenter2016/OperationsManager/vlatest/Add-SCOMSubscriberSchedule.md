---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239464
schema: 2.0.0
ms.assetid: 314FF694-2F7E-4C5E-B4D7-A13477B31A5D
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMSubscriberSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMSubscriberSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMSubscriberSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCOMSubscriberSchedule

## SYNOPSIS
Adds a new schedule entry for a notification subscriber.

## SYNTAX

### StartAndEnd
```
Add-SCOMSubscriberSchedule -Subscriber <NotificationRecipient> [-Exclude] [-StartDate <DateTime>]
 [-EndDate <DateTime>] [[-DayOfWeek] <NotificationRecipientScheduleEntryDaysOfWeek>] [-StartTime] <DateTime>
 [-EndTime] <DateTime> [-TimeZone <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllDay
```
Add-SCOMSubscriberSchedule -Subscriber <NotificationRecipient> [-Exclude] [-StartDate <DateTime>]
 [-EndDate <DateTime>] [[-DayOfWeek] <NotificationRecipientScheduleEntryDaysOfWeek>] [-TimeZone <String>]
 [-PassThru] [-AllDay] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMSubscriberSchedule** cmdlet adds a new schedule entry for a notification subscriber.
Notification subscribers are users who receive notifications when System Center 2016 - Operations Manager raises an alert on a monitored system.

If you do not add entries to a subscriber's existing schedule, the subscriber continues to receive notifications.

## EXAMPLES

### Example 1: Add a schedule for a notification subscriber
```
PS C:\>Get-SCOMNotificationSubscriber "Katarina" | Add-SCOMSubscriberSchedule -StartTime "9:00 AM" -EndTime "5:00 PM" -DayOfWeek Monday, Wednesday, Friday
```

This command adds a schedule window from 9 A.M.
to 5 P.M.
on Mondays, Wednesdays, and Fridays in all date ranges for a notification subscriber named Katarina.
The command uses the **Get-SCOMNotificationSubscriber** cmdlet to get the specified subscriber and passes that subscriber to the **Add-SCOMSubscriberSchedule** cmdlet by using the pipeline operator.

### Example 2: Add multiple schedule entries for a notification subscriber
```
PS C:\>Get-SCOMNotificationSubscriber "Cesar" | Add-SCOMSubscriberSchedule -StartTime "7:00 AM" -EndTime "4:00 PM" -DayOfWeek Monday, Wednesday, Friday -TimeZone "*UTC-06:00*" -PassThru | Add-SCOMSubscriberSchedule -StartDate '2012/1/1' -EndDate '2012/1/15' -TimeZone "*UTC-06:00*" -Exclude
```

This command adds two schedule entries to the notification subscriber named Cesar in the USA Central time zone.
The command uses the **Get-SCOMNotificationSubscriber** cmdlet to get the specified subscriber and passes that subscriber to the **Add-SCOMSubscriberSchedule** cmdlet by using the pipeline operator.
The command adds the entry with the specified values.
The command specifies the *PassThru* parameter in order to pass the user to another instance of the **Add-SCOMSubscriberSchedule** cmdlet by using the pipeline operator.
The command adds a second schedule entry with the specified values.

## PARAMETERS

### -AllDay
Indicates that the schedule entry applies to the whole day.

```yaml
Type: SwitchParameter
Parameter Sets: AllDay
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, specify the computer name, localhost, or a dot (.).

The computer must run the System Center Data Access service.

If you do not specify this parameter, the default is the computer for the current management group connection.

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

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type "`Get-Help Get-Credential`".

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
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

### -DayOfWeek
Specifies the days of the week that the schedule entry is valid. 
By default, the entry applies to all days of the week.

```yaml
Type: NotificationRecipientScheduleEntryDaysOfWeek
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndDate
Specifies the date at which the schedule entry ends.
If this command does not specify  *StartDate* and *EndDate* parameters, the schedule entry applies to all dates.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Specifies the time at which the schedule entry ends.

```yaml
Type: DateTime
Parameter Sets: StartAndEnd
Aliases: To, Until

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exclude
Indicates that the command excludes the specified times and dates from the schedule.
If this parameter does not appear, the schedule includes only the specified times.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter does not appear, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type "`Get-Help about_OpsMgr_Connections`".

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

### -StartDate
Specifies the date at which the schedule entry starts.
If this command does not specify *StartDate* and *EndDate* parameters, the schedule entry applies to all dates.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the start time for the schedule entry.

```yaml
Type: DateTime
Parameter Sets: StartAndEnd
Aliases: From

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subscriber
Specifies the notification subscriber.
To obtain a notification subscriber object, use the **Get-SCOMNotificationSubscriber** cmdlet, or create a new object by using the **Add-SCOMNotificationSubscriber** cmdlet.

```yaml
Type: NotificationRecipient
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TimeZone
Specifies the time zone for the schedule entry.
If you specify wildcards as part of the time zone, the cmdlet performs wildcard matching against the display names for time zones.
If this parameter does not appear, the cmdlet defaults to the current user time zone.

Examples of valid values for this parameter are:

- *UTC+05:00*.
United States Eastern time.
- *Pacific Time*.
United States Pacific time.
- *Amsterdam*.
Amsterdam, Berlin, Bern, Rome, Stockholm time.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Add-SCOMNotificationSubscriber](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscriber.md)

[Clear-SCOMSubscriberSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Clear-SCOMSubscriberSchedule.md)

[Get-SCOMNotificationSubscriber](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationSubscriber.md)

[Remove-SCOMSubscriberSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMSubscriberSchedule.md)

