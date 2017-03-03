---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CCC04257-C12D-4A94-BA2D-7AC29B013757
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscriber.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscriber.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscriber.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCOMNotificationSubscriber

## SYNOPSIS
Adds a notification subscriber in Operations Manager.

## SYNTAX

### DeviceName (Default)
```
Add-SCOMNotificationSubscriber [-Name] <String> [-DeviceList] <String[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DeviceTable
```
Add-SCOMNotificationSubscriber [-Name] <String> [-DeviceTable] <Hashtable> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMNotificationSubscriber** cmdlet adds a notification subscriber in System Center 2016 - Operations Manager.

Notification subscribers receive notifications from Operations Manager.

## EXAMPLES

### Example 1: Add a notification subscriber
```
PS C:\>Add-SCOMNotificationSubscriber -Name "Sarah Jones" -DeviceList "SarahJones@contoso.com", "sms:2065551212", "sip:SarahJ"
```

This command adds a new notification subscriber with email, SMS, and IM addresses.

### Example 2: Add a notification subscriber with a command channel
```
PS C:\>$CommandChannel = Get-SCOMNotificationChannel -DisplayName "OnNotify.exe"
PS C:\> Add-SCOMNotificationSubscriber -Name "Sarah Jones" -DeviceTable @{"Cell"= 'sms:206555213'; "Command" = $CommandChannel.Name }
```

This example adds a new notification subscriber with an SMS address and a command address.

The first command uses the **Get-SCOMNotificationChannel** cmdlet to get the notification channel that has the display name OnNotify.exe, and stores the result in the $CommandChannel variable.

The second command adds a notification subscriber by using the *Name* parameter.

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

### -DeviceList
Specifies an array of notification addresses.
Use username@domain.com form for email addresses, SMS:\<address\> for SMS addresses, and SIP:\<address\> for IM addresses.
Specify the name of a channel for a command channel.

```yaml
Type: String[]
Parameter Sets: DeviceName
Aliases: Email, IM, SMS, MobileNumber, Number

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeviceTable
Specifies a table of named addresses.
Use username@domain.com form for email addresses, SMS:\<address\> for SMS addresses, and SIP:\<address\> for IM addresses.
Specify the name of a channel for a command channel.

```yaml
Type: Hashtable
Parameter Sets: DeviceTable
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a notification subscriber.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Get-SCOMNotificationSubscriber](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationSubscriber.md)

[Remove-SCOMNotificationSubscriber](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMNotificationSubscriber.md)

