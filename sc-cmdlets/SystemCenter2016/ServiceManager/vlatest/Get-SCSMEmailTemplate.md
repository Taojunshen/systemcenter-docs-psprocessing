---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C15CE2B9-C4F8-4E67-A5C5-A5E59C298880
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMEmailTemplate

## SYNOPSIS
Retrieves email templates that are defined in Service Manager.

## SYNTAX

```
Get-SCSMEmailTemplate [-Description <String>] [[-DisplayName] <String>] [-ManagementPack <ManagementPack>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMEmailTemplate** cmdlet retrieves email templates that are defined in Service Manager.
The type of the returned object is **ManagementPackObjectTemplate**.
This cmdlet returns only objects of the class **SMTP**.

## EXAMPLES

### Example 1: Get all templates
```
C:\PS>Get-SCSMEmailTemplate
DisplayName          Description          ManagementPack       TimeAdded            LastModified
-----------          -----------          --------------       ---------            ------------
Assigned To User Not Use for notification Service Manager Inci 12/2/2010 12:22:15 A 12/3/2010 12:56:15 A
ification Template   s sent to the user w dent Management Conf M                    M

                     ho is assigned the i iguration Library
                     ncident
End User Notificatio Use for notification Service Manager Inci 12/2/2010 12:22:15 A 12/3/2010 12:01:50 A
n Template           s sent to end users  dent Management Conf M                    M
                                          iguration Library
Assigned To User Not Use for notification Service Manager Chan 12/2/2010 12:21:55 A 12/2/2010 12:21:55 A
ification Template   s sent to the user w ge Management Config M                    M
                     ho is assigned the c uration Library
                     hange request
Escalation Notificat Use for notification Service Manager Inci 12/2/2010 12:22:15 A 12/3/2010 12:01:50 A
ion Template         s sent when an incid dent Management Conf M                    M
                     ent is escalated     iguration Library
```

This command retrieves all email templates from Service Manager.

### Example 2: Display names and targeted classes
```
C:\PS>Get-SCSMEmailTemplate | Format-Table -Property DisplayName,TargetClass -AutoScale
DisplayName                            TargetClass
-----------                            -----------
Assigned To User Notification Template System.WorkItem.Incident
End User Notification Template         System.WorkItem.Incident
Assigned To User Notification Template System.WorkItem.ChangeRequest
Escalation Notification Template       System.WorkItem.Incident
Printer Email Template                 Microsoft.AD.Printer
```

This command retrieves the email templates, and passes them to the Format-Table cmdlet.
That cmdlet displays the display name and the targeted class for the templates.
The results could be passed to the New-SCSMSubscription cmdlet.

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
Specifies the description of the email template to retrieve.

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
Specifies the display name of the email template to retrieve.

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
Specifies the management packs in which email templates to retrieve are defined.

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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Notifications.EmailTemplate
This cmdlet returns email template objects.

## NOTES

## RELATED LINKS

[Get-SCSMEmailTemplateContent](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplateContent.md)

[New-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMEmailTemplate.md)

[New-SCSMSubscription](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMSubscription.md)

[Remove-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMEmailTemplate.md)

[Update-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMEmailTemplate.md)

