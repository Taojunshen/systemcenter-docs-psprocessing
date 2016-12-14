---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225388
schema: 2.0.0
ms.assetid: D2E04CF6-7EC6-49DD-AC98-93B174E3491F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Update-SCSMSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Update-SCSMSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Update-SCSMSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCSMSubscription

## SYNOPSIS
Updates subscription properties in Service Manager.

## SYNTAX

```
Update-SCSMSubscription [-Subscription] <Subscription[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMSubscription** cmdlet updates subscription properties in Service Manager.

## EXAMPLES

### Example 1: Update the email template for a subscription
```
PS C:\>Get-SCSMsubscription -DisplayName "Subscription01"
displayname    description                           ManagementPack Enabled TimeAdded            LastModified
-----------    -----------                           -------------- ------- ---------            ------------
Subscription01 Just a description for a subscription subscriptionMP true    7/21/2010 9:10:29 PM 7/21/2010 9:10:29 PM

The second command gets the subscription that has the specified display name, and then stores it in the $Subscription variable. The third command gets the user class by using the Get-SCSMClass cmdlet, and then stores it in the $Class variable. The forth command gets an instance of the class in $Class by using the Get-SCSMClassInstance cmdlet. The command stores the instance in the $User variable. The fifth command adds a value to the **RecipientUsers** property of $Subscription. The final command updates the subscription to match the current value of $Subscription.
PS C:\>$Subscription = Get-SCSMsubscription -DisplayName "Subscription01"
PS C:\> $Subscription.Template = Get-SCSMEmailTemplate "Template2"
PS C:\> $Class = Get-SCCMClass -Name "System.Domain.User"
PS C:\> $User = Get-SCClassInstance -Class $Class -Filter "UserName -eq user"
PS C:\> $Subscription.RecipientUsers += $User.EnterpriseManagementObject
PS C:\> Update-SCSMSubscription -Subscription $Subscription
```

This example updates the email template which is used with the subscription named Subscription01, and adds the woodgrove administrator to the recipient list.
The first command displays the subscription that is being updated by using **Get-SCSMsubscription**.

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

### -PassThru
Indicates that this cmdlet returns the subscription that it updates.
You can pass this object to other cmdlets.

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

### -Subscription
Specifies the subscription that this cmdlet updates.
To obtain a subscription, use the Get-SCSMSubscription cmdlet.

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

[Get-SCSMSetting](xref:SystemCenter2016/ServiceManager/Get-SCSMSetting.md)

[New-SCSMSubscription](xref:SystemCenter2016/ServiceManager/New-SCSMSubscription.md)

[Remove-SCSMSubscription](xref:SystemCenter2016/ServiceManager/Remove-SCSMSubscription.md)

