---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FD2D96C6-9244-4DCB-8D44-F1F7D126C146
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMSubscription

## SYNOPSIS
Removes a subscription from Service Manager.

## SYNTAX

```
Remove-SCSMSubscription [-Subscription] <Subscription[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMSubscription** cmdlet removes a subscription from Service Manager.

## EXAMPLES

### Example 1: Delete subscriptions by using the display name
```
PS C:\>Get-SCSMSubscription -DisplayName "custom*" | Remove-SCSMSubscription
```

This command gets subscriptions that have display names that contain the string custom by using the Get-SCSMSubscription cmdlet.
The command passes these subscriptions to the current cmdlet by using the pipeline operator.
That cmdlet deletes each subscription.

## PARAMETERS

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

### -Subscription
Specifies the object that represents the subscription that this cmldet removes.

```yaml
Type: Subscription[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Notifications.Subscriptions.Subscription
You can pipe a subscription to the *Subscription* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMSubscription](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMSubscription.md)

[New-SCSMSubscription](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMSubscription.md)

[Update-SCSMSubscription](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMSubscription.md)

