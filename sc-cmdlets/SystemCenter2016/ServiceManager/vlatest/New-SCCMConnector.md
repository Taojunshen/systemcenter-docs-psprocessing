---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225350
schema: 2.0.0
ms.assetid: 056B2223-C4B6-4DDD-BDAD-84FD4A3E15AF
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCCMConnector

## SYNOPSIS
Creates a Configuration Manager connector in Service Manager.

## SYNTAX

```
New-SCCMConnector -SCCMCredential <PSCredential> [-Collections <String[]>] -DatabaseName <String>
 -DatabaseServer <String> [[-Description] <String>] [-Enable <Boolean>] [-DisplayName] <String> [-PassThru]
 [-RunAsAccount <ManagementPackSecureReference>] [-ScheduleDay <DaySchedule>] [-ScheduleHour <Int32>]
 [-SolutionManagementPack <ManagementPack[]>] [-SyncNow] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCCMConnector** cmdlet creates a Configuration Manager connector in Service Manager.

## EXAMPLES

### Example 1: Create a connector
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -DisplayName "Workflow Account"
PS C:\> New-SCCMConnector -DisplayName "WOODGROVE CM CONNECTOR" -Description "Woodgrove Configuration Manager connection" -DatabaseName "SMS_DFD" -DatabaseServer "CMServer" -Collections "SCCMDF" -Enable $False -RunAsAccount $RunAsAccount -ScheduleDay Sunday -ScheduleHour 3
```

The first command gets a Run As account for Workflow Account by using the Get-SCSMRunAsAccount cmdlet.
The command stores the result in the $RunAsAccount variable.

The second command creates a Configuration Manager connector to the database server CMServer.
The new connector is configured to synchronize every Sunday at 3:00 A.M.

## PARAMETERS

### -Collections
Specifies the name of the Configuration Manager collections to synchronize.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: All Collections
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

### -DatabaseName
Specifies the name of the Configuration Manager database.

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

### -DatabaseServer
Specifies the name of the Configuration Manager database server.

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

### -PassThru
Indicates that this cmdlet returns the Configuration Manager connector that it creates.
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
Specifies the Run As account that the connector uses when it runs.

```yaml
Type: ManagementPackSecureReference
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Operational System Account
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCCMCredential
Specifies the credential to use when you connect to the Configuration Manager server to validate the collections that the connector synchronizes.

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
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleHour
Specifies the hour at which the connector starts synchronization.
The value must be a number between 0-23.

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

### -SolutionManagementPack
Specifies the solution name.

```yaml
Type: ManagementPack[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncNow
Indicates that this cmdlet starts a Connection Manager connector synchronization.

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

[New-SCOMAlertConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md)

[New-SCOMConfigurationItemConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md)

[New-SCOrchestratorConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOrchestratorConnector.md)

[New-SCVMMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md)

