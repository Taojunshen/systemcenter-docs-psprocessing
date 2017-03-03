---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 89CDFA1B-76F2-4C50-A1ED-FBB0A54572E7
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Clear-SCOMSubscriberSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Clear-SCOMSubscriberSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Clear-SCOMSubscriberSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Clear-SCOMSubscriberSchedule

## SYNOPSIS
Removes all entries from a notification subscriber's schedule.

## SYNTAX

```
Clear-SCOMSubscriberSchedule [-Subscriber] <NotificationRecipient> [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-SCOMSubscriberSchedule** cmdlet removes all entries from a notification subscriber's schedule.
Notification subscribers are users who receive notifications when System Center 2016 - Operations Manager raises an alert on a monitored system.
A clear schedule indicates an always on subscription that can notify at any time.

## EXAMPLES

### Example 1: Clear all subscriber schedules
```
PS C:\>Get-SCOMNotficationSubscriber | Clear-SCOMSubscriberSchedule
```

This command resets the schedules of all subscribers.
The command uses the **Get-SCOMNotficationSubscriber** cmdlet to get all notification subscribers and then passes them to the **Clear-SCOMSubscriberSchedule** cmdlet by using the pipeline operator.

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

### -Subscriber
Specifies the notification subscriber.
To get a notification subscriber object, use the **Get-SCOMNotificationSubscriber** cmdlet, or create a new object by using the **Add-SCOMNotificationSubscriber** cmdlet.

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

[Add-SCOMNotificationSubscriber](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscriber.md)

[Add-SCOMSubscriberSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMSubscriberSchedule.md)

[Get-SCOMNotificationSubscriber](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationSubscriber.md)

[Remove-SCOMSubscriberSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMSubscriberSchedule.md)

