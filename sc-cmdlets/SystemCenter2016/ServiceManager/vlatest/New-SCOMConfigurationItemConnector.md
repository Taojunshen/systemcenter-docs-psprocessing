---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B468B61B-84AD-4C9E-B663-96CFE1106D76
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCOMConfigurationItemConnector

## SYNOPSIS
Creates an Operations Manager configuration item connector in Service Manager.

## SYNTAX

```
New-SCOMConfigurationItemConnector [[-Description] <String>] [-Enable <Boolean>] [-ManagementPack <String[]>]
 [-DisplayName] <String> -OperationsManagerServer <String> [-PassThru]
 [-RunAsAccount <ManagementPackSecureReference>] [-ScheduleDay <DaySchedule>] [-ScheduleHour <Int32>]
 [-SyncNow] -SCOMCredential <PSCredential> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCOMConfigurationItemConnector** cmdlet creates an Operations Manager configuration item connector in Service Manager.

## EXAMPLES

### Example 1: Create a configuration item connector
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -DisplayName "Workflow"
PS C:\> New-SCOMConfigurationItemConnector -DisplayName "WOODGROVE OpsMgr CI CONNECTOR" -Description "Woodgrove Operations Manager CI connection" -OperationsManagerServer "OpsMgrServer" -Enable $True -ManagementPack "Microsoft.Windows.Server.2003","Microsoft.Windows.Library" -RunAsAccount $RunAsAccount -ScheduleHour 1
```

The first command gets a Run As account for Workflow Account by using the Get-SCSMRunAsAccount cmdlet.
The command stores the result in the $RunAsAccount variable.

The second command creates an Operations Manager configuration item connector to the database server named OpsMgrServer.
This connector is configured to synchronize every day at 1:00 am.

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
Specifies the name of the connector.

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

### -ManagementPack
Specifies the management pack in which to store the Operations Manager configuration item connector.
You cannot specify a sealed management pack.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: The default management pack
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationsManagerServer
Specifies the name of the Operations Manager server.

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

### -PassThru
Indicates that this cmdlet returns the Operations Manager configuration item connector that it creates.
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

### -RunAsAccount
Specifies the Run As account to use during the synchronization of the connector.

```yaml
Type: ManagementPackSecureReference
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: WorkFlow RunAsAccount
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCOMCredential
Specifies the credential to use when you connect to the Operations Manager server.

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

### -SCSession
Specifies an object that represents a session to a Service Manager management server.

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
Specifies the day of the week in which to synchronize the connector.
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncNow
Initiates synchronization of the Operations Manager configuration item connector.

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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[New-SCADConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCADConnector.md)

[New-SCCMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md)

[New-SCOMAlertConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md)

[New-SCOrchestratorConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOrchestratorConnector.md)

[New-SCVMMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md)

