---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1F088602-941D-4753-90FF-DB1427E3676C
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCOMNotificationSubscription

## SYNOPSIS
Adds a notification subscription.

## SYNTAX

```
Add-SCOMNotificationSubscription [-Name] <String> [-DisplayName <String>] [-Description <String>]
 [[-Criteria] <String>] [-OnlyOnResolutionChange] [-PollingInterval <TimeSpan>] [-Delay <TimeSpan>]
 -Subscriber <NotificationRecipient[]> [-CcSubscriber <NotificationRecipient[]>]
 [-BccSubscriber <NotificationRecipient[]>] -Channel <Object[]> [-Disabled] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMNotificationSubscription** cmdlet adds a notification subscription in System Center 2016 - Operations Manager.

In this release there is no cmdlet support for scoping subscriptions based on a criteria, but you can achieve this result through Windows PowerShell by accessing the SCOM SDK directly.

## EXAMPLES

### Example 1: Add a notification subscription
```
PS C:\>$Subscriber = Get-SCOMNotificationSubscriber -Name "John Smith","Sarah Jones"
PS C:\> $Channel = Get-SCOMNotificationChannel -DisplayName "EmailChannel"
PS C:\> Add-SCOMNotificationSubscription -Name "NewSubscription1" -Subscriber $Subscriber -Channel $Channel
```

This example adds a new notification subscription for all alerts.

The first command uses the **Get-SCOMNotificationSubscriber** cmdlet to get subscribers and stores the result in the $Subscriber variable.

The second command uses the **Get-SCOMNotificationChannel** cmdlet to get the notification channel, and stores the result in the $Channel variable.

The third command uses the **Add-SCOMNotificationSubscription** cmdlet with the *Name*, *Subscriber*, and *Channel* parameters.

### Example 2: Add a notification subscription with conditions
```
PS C:\>$Subscriber = Get-SCOMNotificationSubscriber -Name "John Smith","Sarah Jones"
PS C:\> $Channel = Get-SCOMNotificationChannel -DisplayName "EmailChannel"
PS C:\> Add-SCOMNotificationSubscription -Name "NewSubscription2" -Subscriber $Subscriber -Channel $Channel -Delay "1:00:00" -Disabled
```

This example adds a new notification subscription for all alerts, but only notifies if conditions remain unchanged for 1 hour.
The example creates the subscription in the disabled state.

The first command uses the **Get-SCOMNotificationSubscriber** cmdlet to get subscribers and stores the result in the $Subscriber variable.

The second command uses the **Get-SCOMNotificationChannel** cmdlet to get the notification channel, and stores the result in the $Channel variable.

The third command uses the **Add-SCOMNotificationSubscription** cmdlet with the *Name*, *Subscriber*, and *Channel* parameters.

### Example 3: Add a new subscription for instances of a specific class
```
PS C:\>$Subscriber = Get-SCOMNotificationSubscriber -Name "John Smith","Sarah Jones"
PS C:\> $Channel = Get-SCOMNotificationChannel -DisplayName "EmailChannel"
PS C:\> $Subscription = Add-SCOMNotificationSubscription -Name "NewSubscription3" -Subscriber $Subscriber -Channel $Channel
PS C:\> $HealthService = Get-SCOMClass -Name "Microsoft.SystemCenter.HealthService"
PS C:\> $Subscription.Configuration.MonitoringClassIds.Add( $HealthService.Id )
PS C:\> $Subscription.Update()
```

This example adds a new notification subscription for all alerts, then uses the Operations Manager SDK to scope the subscription to alerts raised by instances of the HealthService class.

The first command uses the **Get-SCOMNotificationSubscriber** cmdlet to get subscribers and stores the result in the $Subscriber variable.

The second command uses the **Get-SCOMNotificationChannel** cmdlet to get the notification channel, and stores the result in the $Channel variable.

The third command uses the **Add-SCOMNotificationSubscription** cmdlet with the *Name*, *Subscriber*, and *Channel* parameters.
The cmdlet stores the result in the $Subscription variable.

The fourth command uses the **Get-SCOMClass** cmdlet and stores the result in the $HealthService variable.

The fifth command uses the Add method with the ID of the $HealthService variable.

The sixth command uses the Update method.

### Example 4: Add a notification subscription by using the SDK
```
PS C:\>$Subscriber = Get-SCOMNotificationSubscriber -Name "John Smith","Sarah Jones"
PS C:\> $Channel = Get-SCOMNotificationChannel -DisplayName "EmailChannel"
PS C:\> $Subscription = Add-SCOMNotificationSubscription -Name "NewSubscription4" -Subscriber $Subscriber -Channel $Channel
PS C:\> $WindowsComputers = Get-SCOMGroup -DisplayName "All Windows Computers"
PS C:\> $Subscription.Configuration.MonitoringObjectGroupIds.Add( $WindowsComputers.Id )
PS C:\> $Subscription.Update()
```

This example adds a new notification subscription for all alerts, and then uses the Operations Manager SDK to scope the subscription to alerts raised by instances in the All Windows Computers group.

The first command uses the **Get-SCOMNotificationSubscriber** cmdlet to get subscribers and stores the result in the $Subscriber variable.

The second command uses the **Get-SCOMNotificationChannel** cmdlet to get the notification channel, and stores the result in the $Channel variable.

The third command uses the **Add-SCOMNotificationSubscription** cmdlet with the *Name*, *Subscriber*, and *Channel* parameters.
The cmdlet stores the result in the $Subscription variable.

The fourth command uses the **Get-SCOMGroup** cmdlet to get the All Windows Computers group, and stores the result in the $WindowsComputers variable.

The fifth command uses the Add method with the Id of the $WindowsComputers variable.

The sixth command uses the Update method.

### Example 5: Add a notification subscription for a specific monitor
```
PS C:\>$Subscriber = Get-SCOMNotificationSubscriber -Name "John Smith","Sarah Jones"
PS C:\> $Channel = Get-SCOMNotificationChannel -DisplayName "EmailChannel"
PS C:\> $Monitor = Get-SCOMMonitor -DisplayName "ContosoMonitor"
PS C:\> $Criteria = @"
>><And xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
>><Expression>
>><SimpleExpression>
>><ValueExpression>
>><Property>ProblemId</Property>
>></ValueExpression>
>><Operator>Equal</Operator>
>><ValueExpression>
>><Value>$($monitor.Id)</Value>
>></ValueExpression>
>></SimpleExpression>
>></Expression>
>><Expression>
>><SimpleExpression>
>><ValueExpression>
>><Property>Severity</Property>
>></ValueExpression>
>><Operator>Equal</Operator>
>><ValueExpression>
>><Value>2</Value>
>></ValueExpression>
>></SimpleExpression>
>></Expression>
>>"@
PS C:\> Add-SCOMNotificationSubscription -Name "Subscription03" -Subscriber $Subscriber -Channel $Channel -Criteria $Criteria
```

This example adds a new notification subscription for all critical alerts raised by the monitor that has the display name ContosoMonitor.

The first command uses the **Get-SCOMNotificationSubscriber** cmdlet to get subscribers and stores the result in the $Subscriber variable.

The second command uses the **Get-SCOMNotificationChannel** cmdlet to get the notification channel, and stores the result in the $Channel variable.

The third command uses the **Get-SCOMMonitor** cmdlet and stores the result in the $Monitor variable.

The fourth command stores the XML criteria in the $Criteria variable.

The fifth command uses the **Add-SCOMNotificationSubscription** cmdlet with the *Name*, *Subscriber*, *Channel*, and *Criteria* parameters.

## PARAMETERS

### -BccSubscriber
Specifies an array of subscribers to blind carbon copy (BCC) on a message for a subscription.

```yaml
Type: NotificationRecipient[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CcSubscriber
Specifies an array of subscribers to carbon copy (CC) on a message for a subscription.

```yaml
Type: NotificationRecipient[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Channel
Specifies an array of notification channels.
To obtain a notification channel object, use the **Get-SCOMNotificationChannel** cmdlet.

```yaml
Type: Object[]
Parameter Sets: (All)
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

### -Criteria
Specifies the criteria xml that indicates how to filter alerts for this subscription.
Criteria can filter on particular rules or monitors, or properties of the alert, but cannot filter on classes or groups.

You can manually copy the criteria xml from an existing subscription.
To obtain the criteria xml from an existing subscription, use this model: ` $subscription = Get-SCOMNotificationSubscription | Select-Object -First 1 $criteria = $subscription.Configuration.Criteria`.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Delay
Specifies a delay, in HH:MM:SS, for sending notifications if conditions remain unchanged for this period of time.
By default, Operations Manager sends notifications immediately.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description for the notification subscription.
If you do not specify a description, the parameter defaults to the value of the *DisplayName* parameter.

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

### -Disabled
Indicates that the cmdlet creates a subscription but leaves it in a disabled state.

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

### -DisplayName
Specifies a display name for the subscription.
If you do not specify a description, the parameter defaults to the value of the *Name* parameter.

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

### -Name
Specifies a name for the subscription.

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

### -OnlyOnResolutionChange
Indicates that the notification occurs only when the resolution state of the alert changes.

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

### -PollingInterval
Specifies a polling interval for alerts.
If you do not specify this parameter, the interval defaults to 1 minute.

```yaml
Type: TimeSpan
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

### -Subscriber
Specifies an array of subscribers for this subscription.
To obtain a notification subscriber object, use the **Get-SCOMNotificationSubscriber** cmdlet.

```yaml
Type: NotificationRecipient[]
Parameter Sets: (All)
Aliases: 

Required: True
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

[Disable-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Disable-SCOMNotificationSubscription.md)

[Enable-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Enable-SCOMNotificationSubscription.md)

[Get-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationSubscription.md)

[Remove-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMNotificationSubscription.md)

