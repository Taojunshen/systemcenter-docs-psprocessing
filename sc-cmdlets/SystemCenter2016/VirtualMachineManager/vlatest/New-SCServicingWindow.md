---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D013B8FC-B7AE-4CC6-AB38-BB7F946B1F83
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCServicingWindow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCServicingWindow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCServicingWindow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCServicingWindow

## SYNOPSIS
Creates a servicing window and the schedule for the servicing window.

## SYNTAX

### WeeklyFrequency
```
New-SCServicingWindow [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -WeeklyScheduleDayOfWeek <String> [-WeeksToRecur <Int32>]
 [-MinutesDuration <Int32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### MonthlyRelativeFrequency
```
New-SCServicingWindow [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -MonthlyScheduleDayOfWeek <DayOfWeek> -WeekOfMonth <WeekOfMonthType>
 [-MonthsToRecur <Int32>] [-MinutesDuration <Int32>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### MonthlyFrequency
```
New-SCServicingWindow [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -DayOfMonth <DayOfMonthType> [-MonthsToRecur <Int32>] [-MinutesDuration <Int32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### DailyFrequency
```
New-SCServicingWindow [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -DaysToRecur <Int32> [-MinutesDuration <Int32>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCServicingWindow** cmdlet creates a servicing window and the schedule for the servicing window.
A servicing window is a scheduled timeframe during which maintenance work can be done on a virtual machine, a host, or a service.

## EXAMPLES

### Example 1: Schedule a daily servicing window
```
PS C:\> $Date = (Get-Date).AddDays(2)
PS C:\> New-SCServicingWindow -Name "Backup Staging A" -Category "Non Essential" -StartDate $Date -StartTimeOfDay "13:30" -TimeZone 085 -DaysToRecur 3
```

The first command gets the current date and adds two days, then stores the result in the $Date variable.

The second command creates a servicing window named Backup Staging A  that occurs every third day at 1:30 PM in the GMT Standard time zone.
The start date of the servicing window is set to the date stored in $Date, which is in two days.

### Example 2: Schedule a servicing window that occurs one day a week
```
PS C:\> $Date = (Get-Date).AddDays(7)
PS C:\> New-SCServicingWindow -Name "Test Servers Group 3" -Category "Test Group" -StartDate $Date -StartTimeOfDay "11:00" -TimeZone 035 -WeeklyScheduleDayOfWeek "Saturday" -WeeksToRecur 1 -MinutesDuration 180
```

The first command gets the current date and adds seven days (one week), then stores the result in the $Date variable.

The second command creates a servicing window named Test Servers Group 3 that occurs weekly on Saturday starting at 11:00 AM in the Eastern time zone and and lasts for 3 hours (180 minutes).
The start date of the servicing window is set to the date stored in $Date, which is in seven days (one week).

### Example 3: Schedule a biweekly service window
```
PS C:\> New-SCServicingWindow -Name "Staging Group C" -StartTimeOfDay "22:30" -TimeZone 035 -WeeklyScheduleDayOfWeek "Saturday, Sunday" -WeeksToRecur 2
```

This command creates a servicing window named Staging Group C that occurs every other week (biweekly) on Saturday and Sunday starting at 10:30 PM in the Eastern time zone.
Because no start date is specified, by default the servicing window becomes effective today.

### Example 4: Schedule a bimonthly servicing window
```
PS C:\> New-SCServicingWindow -Name "Production Servers A" -Category "Emergency" -StartTimeOfDay "23:30" -TimeZone 085 -MonthlyScheduleDayOfWeek "Tuesday" -WeekOfMonth "Second" -MonthsToRecur 2
```

This command creates a servicing window named Production Servers A that occurs every other month (bimonthly) on the second Tuesday of the month, starting at 11:30 PM in the Eastern time zone.
Because no start date is specified, by default the servicing window becomes effective today.

## PARAMETERS

### -Category
Specifies a category for a servicing window.

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

### -DayOfMonth
Specifies the ordinal day of the month on which the schedule starts.
For example, 4 indicates the fourth day of the month.
Last indicates the last day of the month.

The default value is the integer that corresponds to the same day as specified in the *StartDate* parameter.

- Valid integer values: 1 - 31 
- Valid string values:  First, Last

```yaml
Type: DayOfMonthType
Parameter Sets: MonthlyFrequency
Aliases: 
Accepted values: First, DayTwo, DayThree, DayFour, DayFive, DaySix, DaySeven, DayEight, DayNine, DayTen, DayEleven, DayTweleve, DayThirteen, DayFourteen, DayFifteen, DaySixteen, DaySeventeen, DayEighteen, DayNineteen, DayTwenty, DayTwentyOne, DayTwentyTwo, DayTwentyThree, DayTwentyFour, DayTwentyFive, DayTwentySix, DayTwentySeven, DayTwentyEight, DayTwentyNine, DayThirty, DayThirtyOne, Last

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysToRecur
Specifies the amount of time, in days, between scheduled jobs.
The default value is the minimum value of one (1).
The maximum value is 999.

```yaml
Type: Int32
Parameter Sets: DailyFrequency
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the servicing window.

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

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -MinutesDuration
Specifies a period of time in minutes.
Use this parameter to specify the amount of time for which to put a server or service into maintenance mode.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthlyScheduleDayOfWeek
Specifies the day of the week to run a job that occurs on a monthly schedule.
You can specify only one day of the week.
The default value is the current day (if today is Tuesday, Tuesday is the default).
The acceptable values for this parameter are:

- Monday
- Tuesday
- Wednesday
- Thursday
- Friday
- Saturday
- Sunday

Requirement: Use with the *WeekOfMonth* parameter.

```yaml
Type: DayOfWeek
Parameter Sets: MonthlyRelativeFrequency
Aliases: 
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthsToRecur
Specifies the amount of time, in months, between scheduled service windows.
The default value is the minimum value of 1.
There is no maximum value.

```yaml
Type: Int32
Parameter Sets: MonthlyRelativeFrequency, MonthlyFrequency
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.

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

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -StartDate
Specifies the date to start a service window.
The default value is the current date.
You can type a new date in the short date format for your locale, or, you can pass a **DateTime** object from **Get-Date**.

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

### -StartTimeOfDay
Specifies the time of day, or a time-span during a 24-hour period, to start a job or other operation.
The default value is the current time.

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

### -TimeZone
Specifies a number (an index) that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see [Microsoft Time Zone Index Values](http://go.microsoft.com/fwlink/?LinkId=120935) at `http://go.microsoft.com/fwlink/?LinkId=120935`.
If no time zone is specified, the default time zone used for a virtual machine is the same time zone setting that is on the virtual machine host.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WeekOfMonth
Specifies a week relative to the first day of the month, such as first, second, third, fourth, or last.

```yaml
Type: WeekOfMonthType
Parameter Sets: MonthlyRelativeFrequency
Aliases: 
Accepted values: First, Second, Third, Fourth, Last

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeklyScheduleDayOfWeek
Specifies one or more days of the week to run a job.
The default value is the current day of the week.

- Valid values to specify an individual day by using a string: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday.
- Valid values to specify a set of days in a week: Any set of two or more days separated by commas.
- Valid values to specify an individual day by using an integer: 1, 2, 3, 4, 5, 6, 7

```yaml
Type: String
Parameter Sets: WeeklyFrequency
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksToRecur
Specifies the amount of time, in weeks, between scheduled jobs.
The default value is the minimum value of one (1).
There is no maximum value.

```yaml
Type: Int32
Parameter Sets: WeeklyFrequency
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ServicingWindow
This cmdlet returns a **ServicingWindow** object.

## NOTES

## RELATED LINKS

[Get-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindow.md)

[Remove-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServicingWindow.md)

[Set-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCServicingWindow.md)

