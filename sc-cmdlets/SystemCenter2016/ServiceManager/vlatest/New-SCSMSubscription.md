---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 017CFDB6-FCF3-41B5-8440-AADA696A88F7
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCSMSubscription

## SYNOPSIS
Creates a subscription in Service Manager.

## SYNTAX

```
New-SCSMSubscription -Class <ManagementPackClass> [-Condition <Condition>] [-Description <String>]
 [-Criteria <String>] [-GroupQueue <String[]>] [-ManagementPack <ManagementPack>] -DisplayName <String>
 -Recipient <EnterpriseManagementObject[]> -Template <EmailTemplate> [-PassThru] [-Enable <Boolean>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMSubscription** cmdlet creates a subscription in Service Manager.

## EXAMPLES

### Example 1: Create a subscription
```
PS C:\>$PrinterClass = Get-SCSMClass -Name "Microsoft.AD.Printer"
PS C:\> $Message = 'Printer $Context/Property[''Type=Windows!Microsoft.AD.Printer'']/PrinterName$ has been updated'
PS C:\> $ManagementPack = Get-SCSMManagementPack -Name "ServiceManager.ConfigurationManagement.Configuration"
PS C:\> $Language = [System.Globalization.CultureInfo]"EN"
PS C:\> $Encoding = [System.Text.Encoding]::ASCII
PS C:\> New-SCSMEmailTemplate -Class $PrinterClass -DisplayName "Printer Email Template" -Body $Message -Description "A template for printer notifications" -Encoding $Encoding -Language $Language -ManagementPack $ManagementPack -Subject $Message
PS C:\> $PrinterTemplate = Get-SCSMEmailTemplate -DisplayName "Printer Email Template"
PS C:\> $UserClass = Get-SCSMClass -Name "Microsoft.AD.User"
PS C:\> $Recipient = Get-SCSMClassInstance -Class $UserClass -Filter 'UserName -like "%Administrator"'
PS C:\> New-SCSMSubscription -Class $PrinterClass -DisplayName "Printer update subscription" -Recipient $Recipient -Template $PrinterTemplate -Condition Updated
```

The first command gets a class named Microsoft.AD.Printer by using the Get-SCSMClass cmdlet, and then stores it in the $PrinterClass variable.

The second command creates a message for the email, and stores it in the $Message variable.
This example uses the same string as the subject and the body of the email.

The third command gets a management pack in which to save this template by using the Get-SCSMManagementPack cmdlet, and then stores it in the $ManagementPack variable.

The fourth and fifth commands store values for language and encoding in the $Language and $Encoding variables.

The sixth command creates an email template that applies when a change occurs to a printer.
The command uses values that were created in the first five commands.

The seventh command gets the email template named Printer Email Template by using the Get-SCSMEmailTemplate cmdlet, and then stores it in the $PrinterTemplate variable.

The eighth command gets the class named Microsoft.AD.User by using **Get-SCSMClass**, and then stores it in the $UserClass variable.

The ninth command gets an instance of the class in $UserClass that has a name that matches a specified filter by using the Get-SCSMClassInstance cmdlet.
The command stores that instance in the $Recipient variable.

The final command creates a subscription that uses the email template, created earlier in the example, which sends an email to the administrator whenever a printer is updated.

### Example 2: Create an email notification subscription
```
PS C:\>$Criteria = @'
>>  <Criteria>
>>  <Expression>
>>  <SimpleExpression>
>>  <ValueExpression>
>>  <Property State="Pre">$Context/Property[Type='Windows!Microsoft.AD.Printer']/Location$</Property>
>>     </ValueExpression>
>>    <Operator>NotEqual</Operator>
>>    <ValueExpression>
>>      <Property State="Post">$Context/Property[Type='Windows!Microsoft.AD.Printer']/Location$</Property>
>>     </ValueExpression>
>>    </SimpleExpression>
>>   </Expression>
>>  </Criteria>
>>  @'
PS C:\> $Recipient = Get-SCSMClassInstance -DisplayName "System.User" -Filter "Name -like 'domain admins'"
PS C:\> $Class = Get-SCSMClass -Displayname "Microsoft.AD.Printer"
PS C:\> $Template = Get-SCSMEmailTemplate -Displayname "StandardEmailTemplate"
PS C:\> New-SCSMSubscription -Class <ManagementPackClass> -DisplayName "A printer subscription" -Recipient $Recipient -Template $Template -Condition Updated -Criteria $Criteria -Description "Changes in the printer location will cause email to be sent"
```

The first command creates a criteria for the subscription, and stores it in the $Criteria variable.

The second command gets a class instance for the class named **System.User** that has a name that matches a specified filter by using the Get-SCSMClassInstance cmdlet.
The command stores that instance in the $Recipient variable.

The third command gets the class named Microsoft.AD.Printer by using **Get-SCSMClass**, and then stores it in the $Class variable.

The fourth command gets the email template named StandardEmailTemplate by using **Get-SCSMEmailTemplate**, and then stores it in the $Template variable.

The final command creates an email notification subscription that is configured to send email to the domain administrators.
The subscription is based on changes in the **Printer** class, where the location has changed.

## PARAMETERS

### -Class
Specifies the name of the class that the subscription targets.
The specified name must reference the same class that is referenced by the specified email template.

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

### -Condition
Specifies the condition under which the subscription runs.
Valid values are: 

- Created 
- Updated 
- Deleted

```yaml
Type: Condition
Parameter Sets: (All)
Aliases: 
Accepted values: Created, Updated

Required: False
Position: Named
Default value: Updated
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

### -Criteria
Specifies the XML criteria which the subscription uses.
If both the *Filter* parameter and the *Criteria* parameter are specified, this cmdlet uses only *Criteria*.

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

### -Description
Describes the subscription.

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
Specifies the display name of the subscription.

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

### -Enable
Indicates whether this cmdlet enables the subscription.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupQueue
Specifies a group or a queue to set a limit on the number of objects that the subscription tracks.

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

### -ManagementPack
Specifies the name of the management pack in which this cmdlet stores the subscription.

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
Indicates that this cmdlet returns the subscription that it creates.
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

### -Recipient
Specifies the list of users to whom this subscription sends email.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: (All)
Aliases: 

Required: True
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

### -Template
Specifies the name of an email template.

```yaml
Type: EmailTemplate
Parameter Sets: (All)
Aliases: 

Required: True
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMEmailTemplate.md)

[Get-SCSMSetting](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMSetting.md)

[New-SCSMEmailTemplate](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMEmailTemplate.md)

[Remove-SCSMSubscription](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMSubscription.md)

[Update-SCSMSubscription](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMSubscription.md)

