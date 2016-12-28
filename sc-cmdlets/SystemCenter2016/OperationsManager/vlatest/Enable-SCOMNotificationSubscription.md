---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9C35E04C-3C7E-4228-84A8-F642E5273271
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Enable-SCOMNotificationSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Enable-SCOMNotificationSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Enable-SCOMNotificationSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCOMNotificationSubscription

## SYNOPSIS
Enables a notification subscription.

## SYNTAX

```
Enable-SCOMNotificationSubscription [-Subscription] <NotificationSubscription[]> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCOMNotificationSubscription** cmdlet enables a notification subscription in System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Enable all notification subscriptions
```
PS C:\>Get-SCOMNotificationSubscription | where-object{$_.Enabled -eq $false} | Enable-SCOMNotificationSubscription
```

This command enables all disabled notifications.

### Example 2: Enable notification subscriptions for a specific user
```
PS C:\>Get-SCOMNotificationSubscription | where-object{$_.ToRecipients -contains "Contoso\SarahJones"} | Enable-SCOMNotificationSubscription
```

This command enables all notifications where the TO line includes a specific user.

## PARAMETERS

### -Subscription
Specifies an array of subscriptions to enable.
To obtain a notification subscription object, use the **Get-SCOMNotificationSubscription** cmdlet.

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

[Add-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMNotificationSubscription.md)

[Disable-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Disable-SCOMNotificationSubscription.md)

[Get-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMNotificationSubscription.md)

[Remove-SCOMNotificationSubscription](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMNotificationSubscription.md)

