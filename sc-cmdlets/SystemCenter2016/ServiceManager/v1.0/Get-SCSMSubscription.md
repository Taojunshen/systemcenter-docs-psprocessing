---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225333
schema: 2.0.0
ms.assetid: 66D37A6B-7E06-416B-8132-04523893AF2B
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMSubscription

## SYNOPSIS
Retrieves subscriptions that are configured in Service Manager.

## SYNTAX

```
Get-SCSMSubscription [-Description <String>] [[-DisplayName] <String>] [-ManagementPack <ManagementPack>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMSubscription** cmdlet retrieves subscriptions that are configured in Service Manager.

## EXAMPLES

### Example 1: Get all available subscriptions
```
PS C:\>Get-SCSMSubscription | Format-List
TargetClass          : System.WorkItem.Incident
ManagementPack       : [Microsoft.EnterpriseManagement.ServiceManager.Default] 
Groups               : {}
Condition            : Updated
Enabled              : False
DisplayName          : Subscription1
Description          : 
Template             : 
Microsoft.EnterpriseManagement.ServiceManager.Sdk.Notifications.EmailTemplate
RecipientUsers       : {Contoso.administrator}
SubscriptionCriteria : 
ManagementPackName   : Microsoft.EnterpriseManagement.ServiceManager.Default
```

This command retrieves available subscriptions, and displays them as a list by using the Format-List cmdlet.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

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

### -Description
Specifies the description of the subscription to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the name of the subscription to retrieve.
You can specify a regular expression.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementPack
Specifies the management pack in which the subscription to retrieve is defined.

```yaml
Type: ManagementPack
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an object that represents the session to a Service Manager management server.

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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Notifications.Subscriptions.Subscription
This cmdlet retrieves subscriptions that are configured in Service Manager.

## NOTES

## RELATED LINKS

[New-SCSMSubscription](xref:SystemCenter2016/ServiceManager/v1.0/New-SCSMSubscription.md)

[Remove-SCSMSubscription](xref:SystemCenter2016/ServiceManager/v1.0/Remove-SCSMSubscription.md)

[Update-SCSMSubscription](xref:SystemCenter2016/ServiceManager/v1.0/Update-SCSMSubscription.md)

