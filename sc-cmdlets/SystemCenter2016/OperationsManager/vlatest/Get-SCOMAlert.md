---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0354B1F4-09A7-4957-BD49-DA9A5AEAD955
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlert.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlert.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlert.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMAlert

## SYNOPSIS
Gets Operations Manager alerts.

## SYNTAX

### Empty (Default)
```
Get-SCOMAlert [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromAlertId
```
Get-SCOMAlert [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromAlertDefault
```
Get-SCOMAlert [[-Instance] <EnterpriseManagementObject[]>] [[-LastModifiedBy] <String[]>] [[-Name] <String[]>]
 [[-Owner] <String[]>] [[-ResolutionState] <Int32[]>] [[-ResolvedBy] <String[]>] [[-HealthState] <String[]>]
 [[-Priority] <String[]>] [[-Severity] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromCriteria
```
Get-SCOMAlert [[-Criteria] <String>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMAlert** cmdlet gets one or more alerts.
An alert is an indication of a significant event that requires your attention.
Rules and monitors can generate alerts.

## EXAMPLES

### Example 1: Get all new alerts
```
PS C:\>Get-SCOMAlert -ResolutionState 0
```

This command gets all alerts that have a resolution state of zero (new alerts).

### Example 2: Get alerts by using a custom field
```
PS C:\>Get-SCOMAlert | where {$_.CustomField1 -eq "TestServer"}
```

This command gets all alerts that have a value of TestServer in the **CustomField1** property.

### Example 3: Get alerts and suppress error messages
```
PS C:\>$OriginalErrorAction = $ErrorActionPreference
PS C:\> $ErrorActionPreference = "SilentlyContinue"
PS C:\> Get-SCOMClass -Name "*health*" | Get-SCOMClassInstance | Get-SCOMAlert -ResolutionState (5..200)
PS C:\> $ErrorActionPreference = $OriginalErrorAction
```

This example gets alerts and suppresses error messages for the class instances that do not match the criteria of the command.

The first command stores the value of the $ErrorActionPreference variable in the $OrigionalErrorAction variable.

The second command sets the value of the $ErrorActionPreference variable to SilentlyContinue.
By setting the value of the $ErrorActionPreference variable to SilentlyContinue, class instances that do not have matching task results continue to run and not show an error.

The third command gets all classes with health in their name and passes the class objects to the **Get-SCOMClassInstance** cmdlet by using the pipeline operator.
The **Get-SCOMClassInstance** gets the class instances for each class object and passes each of the class instance objects to the **Get-SCOMAlert** cmdlet.
The **Get-SCOMAlert** cmdlet returns the alerts that have a resolution state from 5 through 200, inclusive, for each class instance.

The fourth command sets the value for the $ErrorActionPreference variable back to the value stored in the $OrigionalErrorAction variable.

### Example 4: Get an alert by using the ID
```
PS C:\>Get-SCOMAlert -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the alert that has the ID 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be running on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

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
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

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

### -Id
Specifies an array of GUIDs of alert objects.
To get the Id of an alert, type "`Get-SCOMAlert | Format-Table Name, Id`".

```yaml
Type: Guid[]
Parameter Sets: FromAlertId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an array of class instance objects.
This parameter also accepts group objects.
To obtain a class instance object, use the **Get-SCOMClassInstance** cmdlet.
For more information, type `Get-Help Get-SCOMClassInstance`.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LastModifiedBy
Specifies an array of user names.
The cmdlet get the alerts if the last user that edited the alert matches a user name that you specify.

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name
Specifies an array of alert names.
The cmdlet get the alerts that match the alert names that you specify.

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Owner
Specifies an array of user names.
The cmdlet gets an alert if the owner of an alert matches a user name that you specify.

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResolutionState
Specifies an array of resolution state IDs.

When an alert is generated, its resolution state is New.
Operators can change the resolution state for a new alert to Closed or to a custom resolution state that an administrator has created for the management group.
The ID for New is 0 and the ID for Closed is 255.
You can assign custom resolution states any value from 2 through 254.

```yaml
Type: Int32[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResolvedBy
Specifies an array of user names.
The cmdlet get the alerts if the user that resolved the alert matches a user name that you specify.

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

A connection object represents a connection to a management server.
The default is the current management group connection.

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

### -Criteria
Specifies the criteria XML that indicates how to filter alerts.
Criteria can filter on particular rules or monitors, or properties of the alert, but cannot filter on classes or groups.

```yaml
Type: String
Parameter Sets: FromCriteria
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthState
Specifies an array of health states.
Valid values are: critical (red), warning (yellow), healthy (green).

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies an array of alert prioirty levels.
Valid values are: 
- Low
- Medium
- High

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Severity
Specifies an array of severity values of alerts.
Valid values are:
- Information
- Warning
- Critical

```yaml
Type: String[]
Parameter Sets: FromAlertDefault
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Set-SCOMAlert](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMAlert.md)

[Resolve-SCOMAlert](xref:SystemCenter2016/OperationsManager/vlatest/Resolve-SCOMAlert.md)

