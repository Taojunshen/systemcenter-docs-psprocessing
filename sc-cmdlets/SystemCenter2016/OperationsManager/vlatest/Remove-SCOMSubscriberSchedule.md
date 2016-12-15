---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239492
schema: 2.0.0
ms.assetid: 1E93E657-55D6-4028-BA45-B514DB008B94
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMSubscriberSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMSubscriberSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMSubscriberSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMSubscriberSchedule

## SYNOPSIS
Removes entries from a notification subscriber schedule.

## SYNTAX

```
Remove-SCOMSubscriberSchedule [-Subscriber] <NotificationRecipient>
 [-Entry] <NotificationRecipientScheduleEntry> [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMSubscriberSchedule** cmdlet removes entries from a notification subscriber schedule.
Notification subscribers are users who receive notifications when System Center 2016 - Operations Manager raises an alert on a monitored system.

## EXAMPLES

### Example 1: Remove a schedule entry from a subscriber
```
PS C:\>$Subscriber = Get-SCOMNotificationSubscriber "Katarina"
PS C:\> $Subscriber.ScheduleEntries | Select-Object -Last 1 | Remove-ScomSubscriberSchedule -Subscriber $Subscriber
```

This example removes the last schedule entry from a subscriber.

The first command gets the notification subscriber object named Katarina and stores the object in the $Subscriber variable.

The second command selects the last schedule entry for the subscriber that is stored in the $Subscriber variable.
For more information, type "`Get-Help Select-Object`".
The command passes the subscriber object to the **Remove-SCOMSubscriberSchedule** cmdlet by using the pipeline operator.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

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
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
This account must have access to the server that is specified in the *ComputerName* parameter if that parameter is used.
For more information about credential objects, type "`Get-Help Get-Credential`".

If you do not specify this parameter, the default is the account for the current user.

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

### -Entry
Specifies the schedule entry that the cmdlet removes.

```yaml
Type: NotificationRecipientScheduleEntry
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, use the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter is not specified, the cmdlet uses the active persistent connection to a management group.
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

### -Subscriber
Specifies the notification subscriber for whom the cmdlet removes schedule entries.

```yaml
Type: NotificationRecipient
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Add-SCOMSubscriberSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMSubscriberSchedule.md)

[Clear-SCOMSubscriberSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Clear-SCOMSubscriberSchedule.md)

