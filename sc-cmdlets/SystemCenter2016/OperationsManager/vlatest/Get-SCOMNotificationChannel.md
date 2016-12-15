---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239480
schema: 2.0.0
ms.assetid: 25FC95D2-7CEC-4545-81FB-27D1F57FB812
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationChannel.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationChannel.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationChannel.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMNotificationChannel

## SYNOPSIS
Retrieves notification channels for the management group.

## SYNTAX

### Empty (Default)
```
Get-SCOMNotificationChannel [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromDisplayName
```
Get-SCOMNotificationChannel [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMNotificationChannel** cmdlet retrieves the notification channels for the management group.
Notification channels inform administrators of an alert, or they run automation in response to an alert.
A notification channel uses a delivery mechanism in System Center 2016 - Operations Manager, such as email, instant message, Short Message Service, or command, to deliver notifications.

## EXAMPLES

### Example 1: Get all notification channels
```
PS C:\>Get-SCOMNotificationChannel
```

This command gets all notification channels.

### Example 2: Get notification channels by using a display name
```
PS C:\>Get-SCOMNotificationChannel -DisplayName "Email channel"
```

This command gets the notification channel named Email channel.

### Example 3:Get notification channels by using a name
```
PS C:\>Get-SCOMNotificationChannel -DisplayName "MyCustomChannel"
```

This command gets the notification channel named MyCustomChannel.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

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

### -DisplayName
Specifies the display name of a channel.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCOMNotificationChannel](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationChannel.md)

[Remove-SCOMNotificationChannel](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMNotificationChannel.md)

