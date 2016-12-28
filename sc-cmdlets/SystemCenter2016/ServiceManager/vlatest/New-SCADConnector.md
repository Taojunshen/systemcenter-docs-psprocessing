---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FA35EF48-C9A9-426A-8890-5A6806FBEEA9
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCADConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCADConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCADConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCADConnector

## SYNOPSIS
Creates a Service Manager Active Directory connector.

## SYNTAX

```
New-SCADConnector [[-Description] <String>] [-Enable <Boolean>] [-DisplayName] <String> [[-QueryRoot] <String>]
 [-PassThru] [-ComputerFilter <String>] [-UserFilter <String>] [-PrinterFilter <String>]
 -ADCredential <PSCredential> [[-RunAsAccount] <ManagementPackSecureReference>] [-ScheduleDay <DaySchedule>]
 [-ScheduleHour <Int32>] [-SyncNow] [-ExpandGroups] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCADConnector** cmdlet creates a Service Manager Active Directory connector.

The following parameters are only available if you have applied Service Manager 2012 R2 Update Rollup 6 or later versions. 

- *ScheduleDay*
- *ScheduleHour*

## EXAMPLES

### Example 1: Create a connector to the local domain
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -DisplayName "Workflow Account"
PS C:\> $Credential = Get-Credential
PS C:\> New-SCADConnector -DisplayName "Contoso AD Connector" -Description "Contoso AD Connector" -QueryRoot "LDAP://DC=Contoso,DC=com" -RunAsAccount $RunAsAccount -ADCredential $Credential -Enable $False -ScheduleDay Sunday -ScheduleHour 3
```

The first command gets a Run As account for Workflow Account by using the Get-SCSMRunAsAccount cmdlet.
The command stores the result in the $RunAsAccount variable.

The second command prompts you for credentials by using the Get-Credential cmdlet, and then stores the credentials in the $Credential variable.

The final command creates an Active Directory connector to the local domain, which retrieves all computers, printers, users, and user groups.
The connector is configured to synchronize every Sunday at 3:00 A.M.

### Example 2: Create a connector to the local domain that includes a user filter
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -DisplayName "Workflow Account"
PS C:\> $Credential = Get-Credential
PS C:\> New-SCADConnector -DisplayName "Contoso AD Connector" -Description "Contoso users starting with E" -QueryRoot "LDAP://DC=Contoso,DC=com" -RunAsAccount $RunAsAccount -ADCredential $Credential -Enable $False -UserFilter "(givenname=E*)"
```

The first command gets a Run As account for Workflow Account, and then stores it in the $RunAsAccount variable.

The second command prompts you for credentials by using the Get-Credential cmdlet, and then stores the credentials in the $Credential variable.

The final command creates an Active Directory connector to the local domain which retrieves only the user accounts that start with the letter E.

## PARAMETERS

### -ADCredential
Specifies the credential to use when this cmdlet connects to the domain controller.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerFilter
Specifies a filter that selects the computers that the connector synchronizes.
The filter must be specified as an Active Directory filter.
For example, the following filter includes all computers which begin with `win` in the synchronization:

`(name=win*)`

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
Specifies a description for the connector.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name property of the connector.

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

### -Enable
Indicates whether this cmdlet enables or disables the connector.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpandGroups
Specifies that this cmdlet recursively includes members of the groups that are specified by the *UserFilter* parameter.

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

### -PassThru
Indicates that this cmdlet returns the Active Directory connector that it creates.
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

### -PrinterFilter
Specifies a filter that this cmdlet uses to select the printers that the connector synchronizes.

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

### -QueryRoot
Specifies the Active Directory folder from which this cmdlet queries objects, such as LDAP://DC=scsm,DC=stbtest,DC=microsoft,DC=com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount
Specifies the RunAs account to use when using this connector.

```yaml
Type: ManagementPackSecureReference
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: Daily
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

### -ScheduleDay
Specifies the day of the week on which the connector synchronizes.
Valid values are: 

- Daily 
- Sunday 
- Monday 
- Tuesday 
- Wednesday 
- Thursday 
- Friday 
- Saturday

```yaml
Type: DaySchedule
Parameter Sets: (All)
Aliases: 
Accepted values: Daily, Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: Daily
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleHour
Specifies the hour at which the connector starts synchronization.
The value must be a number from zero (0) to 23.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncNow
Causes the Active Directory connector to start a synchronization cycle.

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

### -UserFilter
Specifies the filter that is used to select the users to by synchronized by the connector.
You must specify the value in the form of an Active Directory filter.
For example, the following value for this parameter includes in the synchronization users whose **givenName** starts with `a`:

`(givenname=a*)`

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

[New-SCCMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md)

[New-SCOMAlertConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md)

[New-SCOMConfigurationItemConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md)

[New-SCOrchestratorConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOrchestratorConnector.md)

[New-SCVMMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md)

