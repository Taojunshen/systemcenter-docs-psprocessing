---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C1A612B6-FC11-48E7-8C1A-B5A33FF9C231
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMEmailTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMEmailTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMEmailTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Update-SCSMEmailTemplate

## SYNOPSIS
Updates properties of an email template.

## SYNTAX

```
Update-SCSMEmailTemplate [-EmailTemplate] <EmailTemplate[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMEmailtemplate** cmdlet updates properties of an email template.

## EXAMPLES

### Example 1: Update the subject of an email template
```
PS C:\>$Template = Get-SCSMEmailTemplate -DisplayName "Template01"
PS C:\> $Template.Subject = "This is a changed subject for an email template"
PS C:\> Update-SCSMEmailTemplate -EmailTemplate $Template
```

The first command gets an email template that has the specified display name by using the Get-SCSMEmailTemplate cmdlet.
The command stores that template in the $Template variable.

The second command assigns a new value to the **Subject** property of $Template.

The final command updates the email template to match the current value of $Template.

### Example 2: Add a German entry to an email template
```
PS C:\>$Template = Get-SCSMEmailTemplate -DisplayName "Template02"
PS C:\> $Template.TemplateCollection += @{
>> Body = @'
>> Der Windows-Computer wurde aktualisiert
>> ($Context/Property[Type='System!System.Entity']/DisplayName$ 
>> '@
>> Encoding = [Text.Encoding]::Ascii
>> Language = [globalization.cultureinfo]"de-DE"
>> }
PS C:\> Update-SCSMEmailTemplate -EmailTemplate $Template
```

The first command gets an email template that has the specified display name, and then stores that template in the $Template variable.

The second command assigns a new value to the **TemplateCollection** property of $Template.
The command adds a German email entry to the current template.

The final command updates the email template to match the current value of $Template.

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
Specifies the email template that this cmdlet updates.

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

### -PassThru
Indicates that this cmdlet returns the email template that it updates.
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

[Remove-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMEmailTemplate.md)

