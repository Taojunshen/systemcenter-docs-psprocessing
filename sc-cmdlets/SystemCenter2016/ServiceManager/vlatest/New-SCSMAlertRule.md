---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CD297D71-7E1B-4364-89CA-E42BC7EE384E
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMAlertRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMAlertRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMAlertRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSMAlertRule

## SYNOPSIS
Creates an alert rule to be used with an Operations Manager Alert connector in Service Manager.

## SYNTAX

### Class (Default)
```
New-SCSMAlertRule -Class <String> -Operator <CompareOperator> [-Name] <String> [-Priority <Priority>]
 [-Severity <Severity>] -Template <ManagementPackObjectTemplate> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ManagementPack
```
New-SCSMAlertRule -Operator <CompareOperator> -ManagementPack <String> [-Name] <String> [-Priority <Priority>]
 [-Severity <Severity>] -Template <ManagementPackObjectTemplate> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Custom
```
New-SCSMAlertRule [-CustomField1 <String>] [-CustomOperator1 <CompareOperator>] [-CustomField2 <String>]
 [-CustomOperator2 <CompareOperator>] [-CustomField3 <String>] [-CustomOperator3 <CompareOperator>]
 [-CustomField4 <String>] [-CustomOperator4 <CompareOperator>] [-CustomField5 <String>]
 [-CustomOperator5 <CompareOperator>] [-CustomField6 <String>] [-CustomOperator6 <CompareOperator>]
 [-CustomField7 <String>] [-CustomOperator7 <CompareOperator>] [-CustomField8 <String>]
 [-CustomOperator8 <CompareOperator>] [-CustomField9 <String>] [-CustomOperator9 <CompareOperator>]
 [-CustomField10 <String>] [-CustomOperator10 <CompareOperator>] [-Name] <String> [-Priority <Priority>]
 [-Severity <Severity>] -Template <ManagementPackObjectTemplate> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Computer
```
New-SCSMAlertRule -Group <String> [-Name] <String> [-Priority <Priority>] [-Severity <Severity>]
 -Template <ManagementPackObjectTemplate> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### NoCriteria
```
New-SCSMAlertRule [-NoCriteria] [-Name] <String> [-Priority <Priority>] [-Severity <Severity>]
 -Template <ManagementPackObjectTemplate> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMAlertRule** cmdlet creates an alert rule to use with an Operations Manager Alert connector in Service Manager.

## EXAMPLES

### Example 1: Create an alert rule for an Operations Manager Alert connector
```
PS C:\>$Template = Get-SCSMObjectTemplate -Name ".*IncidentTemplate.*" 
PS C:\> $ManagementPack = Get-SCManagementPack -Name "System.Library"
PS C:\> $Rule = New-SCSMAlertRule -Name "AlertRule22" -ManagementPack -Template $Template
```

The first command gets a template that matches the specified string by using the Get-SCSMObjectTemplate cmdlet.
The command stores the result in the $Template variable.

The second command gets a management pack named System.Library by using the Get-SCSMManagementPack cmdlet.
The command stores the result in the $ManagementPack variable.

The final command creates an alert rule for an Operations Manager Alert connector.

## PARAMETERS

### -Class
Specifies an instance of the monitoring class for which the alert was raised.

```yaml
Type: String
Parameter Sets: Class
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
Default value: None
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

### -CustomField1
Specifies the value for **CustomField1**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator1* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField10
Specifies the value for **CustomField10**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator10* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField2
Specifies the value for **CustomField2**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator2* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField3
Specifies the value for **CustomField3**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator3* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField4
Specifies the value for **CustomField4**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator4* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField5
Specifies the value for **CustomField5**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator5* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField6
Specifies the value for **CustomField6**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator6* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField7
Specifies the value for **CustomField7**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator7* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField8
Specifies the value for **CustomField8**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator8* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomField9
Specifies the value for **CustomField9**.
If you specify a value for this parameter, you must also specify a value for the *CustomOperator9* parameter.

```yaml
Type: String
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator1
Specifies the operator to apply to **CustomField1**.
If you specify this parameter, you must also specify a value in the *CustomField1* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator10
Specifies the operator to apply to **CustomField10**.
If you specify this parameter, you must also specify a value in the *CustomField10* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator2
Specifies the operator to apply to **CustomField2**.
If you specify this parameter, you must also specify the *CustomField2* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator3
Specifies the operator to apply to **CustomField3**.
If you specify this parameter, you must also specify the *CustomField3* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator4
Specifies the operator to apply to **CustomField4**.
If you specify this parameter, you must also specify the *CustomField4* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator5
Specifies the operator to apply to **CustomField5**.
If you specify this parameter, you must also specify the *CustomField5* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator6
Specifies the operator to apply to **CustomField6**.
If you specify this parameter, you must also specify the *CustomField6* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator7
Specifies the operator to apply to **CustomField7**.
If you specify this parameter, you must also specify the *CustomField7* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator8
Specifies the operator to apply to **CustomField8**.
If you specify this parameter, you must also specify the *CustomField8* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomOperator9
Specifies the operator to apply to **CustomField9**.
If you specify this parameter, you must also specify the *CustomField9* parameter.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Custom
Aliases: 
Accepted values: Equals, Contains

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies the name of the group that contains the computers to be associated with the alert rule.

```yaml
Type: String
Parameter Sets: Computer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementPack
Specifies the list of management packs.

```yaml
Type: String
Parameter Sets: ManagementPack
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the alert rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCriteria
Indicates that this cmdlet configures the alert rule to have no criteria.

```yaml
Type: SwitchParameter
Parameter Sets: NoCriteria
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operator
Specifies the comparison operator to use in the alert rule.
Valid values are: 

- Equals 
- Contains

```yaml
Type: CompareOperator
Parameter Sets: Class, ManagementPack
Aliases: 
Accepted values: Equals, Contains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies the priority of the alert rule.
Valid values are: 

- Low 
- Medium 
- High

```yaml
Type: Priority
Parameter Sets: (All)
Aliases: 
Accepted values: Unspecified, Low, Medium, High

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

### -Severity
Specifies the severity of the alert rule.
Valid values are: 

- Low 
- Medium 
- High

```yaml
Type: Severity
Parameter Sets: (All)
Aliases: 
Accepted values: Unspecified, Information, Warning, Error

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Template
Specifies the template to apply to the rule.

```yaml
Type: ManagementPackObjectTemplate
Parameter Sets: (All)
Aliases: 

Required: True
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

### None.

## NOTES
*

* This cmdlet does not generate any output.

## RELATED LINKS

