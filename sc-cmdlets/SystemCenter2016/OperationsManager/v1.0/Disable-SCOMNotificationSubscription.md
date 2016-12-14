---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187722
schema: 2.0.0
ms.assetid: 4ECAEC1F-A5F5-4093-A8C3-06AD2535D127
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Disable-SCOMNotificationSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Disable-SCOMNotificationSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Disable-SCOMNotificationSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCOMNotificationSubscription

## SYNOPSIS
Disables a notification subscription.

## SYNTAX

```
Disable-SCOMNotificationSubscription [-Subscription] <NotificationSubscription[]> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCOMNotificationSubscription** cmdlet disables a notification in System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Disable all enabled notifications
```
PS C:\>Get-SCOMNotificationSubscription | where-object{$_.Enabled} | Disable-SCOMNotificationSubscription
```

This command disables all enabled notifications.

### Example 2: Disable notifications to a notification subscriber
```
PS C:\>Get-SCOMNotificationSubscription | where-object{$_.ToRecipients -contains "CONTOSO\SarahJones"} | Disable-SCOMNotificationSubscription
```

This command disables all notifications where the TO line of the message includes the user account CONTOSO\SarahJones.

## PARAMETERS

### -Subscription
Specifies an array of subscriptions to disable.

```yaml
Type: NotificationSubscription[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[Add-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/v1.0/Add-SCOMNotificationSubscription.md)

[Enable-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/v1.0/Enable-SCOMNotificationSubscription.md)

[Get-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMNotificationSubscription.md)

[Remove-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/v1.0/Remove-SCOMNotificationSubscription.md)

