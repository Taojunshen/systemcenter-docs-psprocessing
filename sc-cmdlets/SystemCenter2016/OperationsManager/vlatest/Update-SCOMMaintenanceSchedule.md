---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 03126C6C-9E5F-402C-A980-2673E6DE277A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Update-SCOMMaintenanceSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Update-SCOMMaintenanceSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Update-SCOMMaintenanceSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCOMMaintenanceSchedule

## SYNOPSIS
Updates the end time of an active maintenance schedule.

## SYNTAX

```
Update-SCOMMaintenanceSchedule [-ID] <Guid> [-ScheduledEndTime] <DateTime> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCOMMaintenanceSchedule** updates the end time of an active maintenance schedule.
The cmdlet will return an error if the existing schedule is not active.
The update will only impact the current instance of the run and will not impact the future runs of the schedule.

When a resource is in maintenance mode, Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.
A maintenance schedule can be used to schedule a set of resources to go into maintenance mode.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### 1:
```

```

## PARAMETERS

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

### -ID
The System Center Data Access service must be active on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

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

### -ScheduledEndTime
```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

[Disable-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Disable-SCOMMaintenanceSchedule.md)

[Edit-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Edit-SCOMMaintenanceSchedule.md)

[Enable-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Enable-SCOMMaintenanceSchedule.md)

[Get-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceSchedule.md)

[New-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMMaintenanceSchedule.md)

[Remove-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMMaintenanceSchedule.md)

[Stop-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Stop-SCOMMaintenanceSchedule.md)

