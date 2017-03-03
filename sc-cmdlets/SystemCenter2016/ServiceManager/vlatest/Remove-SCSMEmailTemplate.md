---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7396795C-8809-4F64-BF27-46C2B72AE5DB
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMEmailTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMEmailTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMEmailTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCSMEmailTemplate

## SYNOPSIS
Removes an email template from Service Manager.

## SYNTAX

```
Remove-SCSMEmailTemplate [-EmailTemplate] <EmailTemplate[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMEmailTemplate** cmdlet removes an email template from Service Manager.

## EXAMPLES

### Example 1: Remove all email templates that match a display name string
```
PS C:\>Get-SCSMEmailTemplate | Where-Object { $_.displayname -match "custom" } | Remove-SCSMEmailTemplate
```

This command removes all email templates where the **DisplayName** property matches the string custom.
The command gets all email templates by using the Get-SCSMEmailTemplate cmdlet.
The command passes the results to the Where-Object cmdlet by using the pipeline operator.
That cmdlet passes on only the results that match the display name to the current cmdlet.
That cmdlet deletes each template.

### Example 2: Remove all email templates that match a description string
```
PS C:\>$Templates = Get-SCSMEmailTemplate | Where-Object {$_.Description -match "notification"}
PS C:\> Remove-SCSMEmailTemplate -EmailTemplate $Templates
```

The first command uses **Get-SCSMEmailTemplate** to get all email templates, and passes them to **Where-Object**.
The command stores all the objects that match the **Description** property as specified in the $Templates variable.

The second command remove all templates in $Templates.

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

### -EmailTemplate
Specifies an object that represents the email template to be removed.

```yaml
Type: EmailTemplate[]
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Notifications.EmailTemplate
You can pipe an email template to the *EmailTemplate* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplate.md)

[Get-SCSMEmailTemplateContent](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplateContent.md)

[New-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMEmailTemplate.md)

[Update-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMEmailTemplate.md)

