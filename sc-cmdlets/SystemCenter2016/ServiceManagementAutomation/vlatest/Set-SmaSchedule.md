---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=306476
schema: 2.0.0
ms.assetid: 9A491678-83AC-428A-A101-54CDB27D8239
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SmaSchedule

## SYNOPSIS
Creates or modifies a schedule in SMA.

## SYNTAX

```
Set-SmaSchedule -Name <String> [-Description <String>] -ScheduleType <String> -StartTime <DateTime>
 -ExpiryTime <DateTime> -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmaSchedule** cmdlet creates or modifies a schedule in Service Management Automation (SMA).
Specify the name and type of the schedule, and the start and end times.

You can modify only the description when you run this cmdlet against an existing schedule.
Start time, expiry time, and day interval can only be set when creating a schedule with this cmdlet.

## EXAMPLES

### Example 1: Create a schedule
```
PS C:\> $StartDate = Get-Date 
PS C:\> $EndDate = Get-Date -Day 12 -Month 6 -Year 2023
PS C:\> Set-SmaSchedule -StartTime $StartDate -ExpiryTime $EndDate -Name "Schedule01" -ScheduleType "DailySchedule" -WebServiceEndpoint "https://contoso.com/app01"
```

The first command creates a date object by using the **Get-Date** cmdlet, and then stores the object in the $StartDate variable.
This object reflects the current time.

The second command creates a date object by using the **Get-Date** cmdlet, and then stores the object in the $EndDate variable.
The command specifies a future time.
For more information, type `Get-Help Get-Date`.

The last command sets the schedule named Schedule01 to begin at the time stored in $StartDate and end at the time stored in $EndDate

## PARAMETERS

### -AuthenticationType
Specifies the authentication type.
Valid values are: 

- Basic
- Windows

The default value for this parameter is Windows.
If you use Basic authentication, you must provide credentials by using the *Credential* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Basic, Windows

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
Specifies a **PSCredential** object for the connection to the SMA web service.
To obtain a credential object, use the Get-Credential cmdlet.
For more information, type `Get-Help Get-Credential`.

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

### -Description
Provides a description for the schedule.

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

### -ExpiryTime
Specifies when, as a **DateTime** object, the schedule ends.
To obtain a **DateTime** object, use the Get-Date cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a schedule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the port number of the SMA web service.

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

### -ScheduleType
Specifies the type of schedule.
Valid values for this parameter are: 

- OneTimeSchedule
- DailySchedule

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: OneTimeSchedule, DailySchedule

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies when, as a **DateTime** object, the schedule starts.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebServiceEndpoint
Specifies the endpoint, as a URL, of the SMA web service.
You must include the protocol, for example, http:// or https://.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-SmaSchedule](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaSchedule.md)

[Remove-SmaSchedule](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Remove-SmaSchedule.md)

