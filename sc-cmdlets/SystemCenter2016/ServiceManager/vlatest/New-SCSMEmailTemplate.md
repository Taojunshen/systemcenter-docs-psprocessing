---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B601585F-5291-46D4-8555-54E2DCBB0AD4
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMEmailTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMEmailTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMEmailTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSMEmailTemplate

## SYNOPSIS
Creates an email template for Service Manager.

## SYNTAX

```
New-SCSMEmailTemplate [-Body <String>] [-Subject <String>] [-Language <CultureInfo>]
 [-TemplateCollection <Hashtable[]>] [-Encoding <Encoding>] -Class <ManagementPackClass>
 [-Description <String>] [-ManagementPack <ManagementPack>] -DisplayName <String> [-SendAsHtml]
 [-Urgency <EmailTemplateUrgency>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMEmailTemplate** cmdlet creates an email template for Service Manager.

## EXAMPLES

### Example 1: Create an email template for a change to a printer
```
PS C:\>$PrinterClass = Get-SCSMClass -Name "Microsoft.AD.Printer"
PS C:\> $Message = 'Printer $Context/Property[''Type=Windows!Microsoft.AD.Printer'']/PrinterName$ has been updated'
PS C:\> $ManagementPack = Get-SCSMManagementPack -Name "ServiceManager.ConfigurationManagement.Configuration"
PS C:\> $Language = [System.Globalization.CultureInfo]"EN"
PS C:\> $Encoding = [System.Text.Encoding]::ASCII
PS C:\> New-SCSMEmailTemplate -Class $PrinterClass -DisplayName "Printer Email Template" -Body $Message -Description "A template for printer notifications" -Encoding $Encoding -Language $Language -ManagementPack $ManagementPack -Subject $Message
```

The first command gets a class named Microsoft.AD.Printer by using the Get-SCSMClass cmdlet, and then stores it in the $PrinterClass variable.

The second command creates a message for the email, and stores it in the $Message variable.
This example uses the same string as the subject and the body of the email.

The third command gets a management pack in which to save this template by using the Get-SCSMManagementPack cmdlet, and then stores it in the $ManagementPack variable.

The fourth and fifth commands store values for language and encoding in the $Language and $Encoding variables.

The final command creates an email template that applies when a change occurs to a printer.
The command uses values that were created in the first five commands.

### Example 2: Create two templates that use different languages
```
PS C:\$BodyEng = @'
>> A change has occurred to the following configuration item: 
>> $Context/Property[Type='System!System.Entity']/DisplayName$ 
>> which is owned by: 
>> $Context/Path[Relationship='System!System.ComputerPrimaryUser'   TypeConstraint='Windows!Microsoft.AD.UserBase']/Property[Type='Windows!Microsoft.AD.UserBase']/DistinguishedName$
>> Please investigate
>> Thank you
>> '@
PS C:\> $BodyGer = @'
>>  Eine Konfigurations ¤nderung erfolgte in
>>  $Context/Property[Type='System!System.Entity']/DisplayName$ 
>>  der im Registrierungscontainer
>>  $Context/Path[Relationship='System!System.ComputerPrimaryUser' TypeConstraint='Windows!Microsoft.AD.UserBase']/Property[Type='Windows!Microsoft.AD.UserBase']/DistinguishedName$
>>  gespeichert ist.
>>  Pr ¼fen Sie bitte nach.
>>  Vielen Dank 
>>  '@
PS C:\> $Templates = @{ Body = $BodyEng; Subject = "Change notification"; Language = [globalization.cultureinfo]"en-us" },@{ Body = $BodyGer; Subject = "Benachrichtigungs-Email"; Language = [globalization.cultureinfo]"de-de" }
PS C:\> $ComputerClass = Get-SCSMClass -Name "Microsoft.Windows.Computer"
PS C:\> New-SCSMEmailTemplate -Class $ComputerClass -DisplayName â€œWindowsChangeEmailTemplateâ€ -TemplateCollection $Templates
```

The first command stores text for the body of the email for the English template in the $BodyEng variable.

The second command stores text for the body of the email for the German template in the $BodyGer variable.

The third command creates templates as hash tables that include $BodyEng and $BodyGer, and additional content.
The two templates have different values for the **Language** property.

The fourth command gets a class named Microsoft.Windows.Computer by using **Get-SCSMClass**, and then stores it in the $ComputerClass variable.

The final command creates two email templates, one in English and one in German.
They are triggered when a change occurs to a computer that runs the Windows operating system.

## PARAMETERS

### -Body
Specifies the message body, which can include insertion strings.

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

### -Class
Specifies the name of the class that the email template targets.

```yaml
Type: ManagementPackClass
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Specifies a description for the email template.

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
Specifies the name of the email template.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding
Specifies the encoding to be used in the message.

```yaml
Type: Encoding
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Unicode (UTF-8)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Language
Specifies the language for the message.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: English (United States)
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementPack
Specifies the name of the management pack in which this cmdlet stores the email template.

```yaml
Type: ManagementPack
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: The default management pack
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the email template that it creates.
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

### -SendAsHtml
Specifies that this cmdlet causes the email to be sent as HTML.

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

### -Subject
Specifies the subject for the email message.

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

### -TemplateCollection
Specifies a collection of hash tables which represent the email template.
The hash table must have the following keys: 

- Body.
This is a string which represents the body of the template. 
- Subject.
This is a string which represents the subject of the email. 
- Language.
This must be of type **CultureInfo**.
It represents the language for the message.
If you specify multiple hash tables, you cannot use the same value for Language.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Urgency
Specifies the urgency of the email message.
Valid values are: 

- High 
- Medium 
- Low

```yaml
Type: EmailTemplateUrgency
Parameter Sets: (All)
Aliases: 
Accepted values: Low, Medium, High

Required: False
Position: Named
Default value: Medium
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplate.md)

[Get-SCSMEmailTemplateContent](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplateContent.md)

[Remove-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMEmailTemplate.md)

[Update-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMEmailTemplate.md)

