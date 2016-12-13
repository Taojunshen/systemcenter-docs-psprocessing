---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServicingWindow.md
schema: 2.0.0
ms.assetid: B81BA043-0A80-4B14-9A85-FEF91DAD27BA
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCServicingWindow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCServicingWindow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCServicingWindow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCServicingWindow

## SYNOPSIS
Modifies the properties of a servicing window.

## SYNTAX

### NoFrequencyUpdate (Default)
```
Set-SCServicingWindow [-ServicingWindow] <ServicingWindow> [-Name <String>] [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] [-MinutesDuration <Int32>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### WeeklyFrequency
```
Set-SCServicingWindow [-ServicingWindow] <ServicingWindow> [-Name <String>] [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -WeeklyScheduleDayOfWeek <String> [-WeeksToRecur <Int32>]
 [-MinutesDuration <Int32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### MonthlyRelativeFrequency
```
Set-SCServicingWindow [-ServicingWindow] <ServicingWindow> [-Name <String>] [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -MonthlyScheduleDayOfWeek <DayOfWeek> -WeekOfMonth <WeekOfMonthType>
 [-MonthsToRecur <Int32>] [-MinutesDuration <Int32>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### MonthlyFrequency
```
Set-SCServicingWindow [-ServicingWindow] <ServicingWindow> [-Name <String>] [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -DayOfMonth <DayOfMonthType> [-MonthsToRecur <Int32>] [-MinutesDuration <Int32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### DailyFrequency
```
Set-SCServicingWindow [-ServicingWindow] <ServicingWindow> [-Name <String>] [-Description <String>]
 [-Category <String>] [-Owner <String>] [-TimeZone <Int32>] [-StartDate <DateTime>]
 [-StartTimeOfDay <DateTime>] -DaysToRecur <Int32> [-MinutesDuration <Int32>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCServicingWindow** cmdlet modifies the properties of a servicing window, including the schedule for the servicing window.

## EXAMPLES

### Example 1: Change the start time of a servicing window
```
PS C:\>$SvcWindow = Get-SCServicingWindow -Name "Backup Staging A" 
PS C:\> Set-SCServicingWindow -ServicingWindow $SvcWindow -StartTimeOfDay "13:00" -TimeZone 085
```

The first command gets the servicing window object named Backup Staging A and stores the object in the $SvcWindow variable.

The second command changes the start time of the servicing window stored in $SvcWindow (Backup Staging A) to 1:00 PM in the GMT Standard time zone.

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

Valid integer values: 1 - 31 

Valid string values:  First, Last

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
The default value is the minimum of one (1).
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
The default value is the minimum value of one (1).
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -ServicingWindow
Specifies a servicing window object.

```yaml
Type: ServicingWindow
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StartDate
Specifies the date to start a service window.
The default value is the current date.
You can type a new date in the short date format for your locale, or, you can pass a **DateTime** object from Get-Date.

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
For a list of time zone indexes, see Microsoft Time Zone Index Valueshttp://go.microsoft.com/fwlink/?LinkId=120935  at http://go.microsoft.com/fwlink/?LinkId=120935.
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

Valid values to specify an individual day by using a string: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday.

Valid values to specify a set of days in a week: Any set of two or more days separated by commas.

Valid values to specify an individual day by using an integer: 1, 2, 3, 4, 5, 6, 7

Requirement: Use with *StartTimeOfDay*.

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

[Get-SCServicingWindow](xref:VirtualMachineManager/v1/Get-SCServicingWindow.md)

[New-SCServicingWindow](xref:VirtualMachineManager/v1/New-SCServicingWindow.md)

[Remove-SCServicingWindow](xref:VirtualMachineManager/v1/Remove-SCServicingWindow.md)

