---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F95BC5AC-518B-486F-AF98-C83564E6F03D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCSQLScriptCommand

## SYNOPSIS
Adds a SQL Server script to a SQL Server application deployment.

## SYNTAX

```
Add-SCSQLScriptCommand [-LoginTimeoutSeconds <Int32>] [-ExecutionTimeoutSeconds <Int32>]
 [-RunAsAccount <VMMCredential>] -ApplicationDeployment <ApplicationDeployment>
 -SQLScriptType <SQLScriptCommandType> -SQLScript <Script> -DeploymentOrder <Int32>
 [-CommandParameters <String>] [-OutputFilePath <String>] [-EncryptConnection <Boolean>]
 [-DatabaseName <String>] [-SQLAuthenticationType <String>] [-WarnAndContinueOnError <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCSQLScriptCommand** cmdlet adds a Microsoft SQL Server script to a SQL Server application deployment.

## EXAMPLES

### Example 1: Add a SQL Server script to an application deployment
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile -Name "SQLDataTierApp01"
PS C:\> $SQLScript = Get-SCScript -Name "ConfigDB.sql" -Release "1.0"
PS C:\> Add-SCSQLScriptCommand -ApplicationDeployment $AppDeployment -SQLScriptType "PreInstall" -DeploymentOrder 1 -DatabaseName "MSSQLSERVER" -SQLScript $SQLScript
```

The first command gets the application profile object named SvcWebAppProfile01, and then stores that object in the $AppProfile variable.

The second command gets the application deployment object named SQLDataTierApp01 for the SvcWebAppProfile01 application profile, and then stores that object in the $AppDeployment variable.

The third command gets the SQL Server script object named ConfigureDB.sql, release 1.0, from the Virtual Machine Manager (VMM) library, and then stores that object in the $Script variable.

The last command adds the SQL Server script stored in $Script to the application deployment stored in $AppDeployment and sets the script type, deployment order, and database against which the script will run.

## PARAMETERS

### -ApplicationDeployment
Specifies an application deployment object.

```yaml
Type: ApplicationDeployment
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CommandParameters
Specifies the parameters for a script or executable program.

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

### -DatabaseName
Specifies the name of a database for a SQL Server script.

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

### -DeploymentOrder
Specifies the order in which a computer tier, application host, or application is deployed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptConnection
Indicates whether the SQL Server connection is encrypted.

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

### -ExecutionTimeoutSeconds
Specifies the amount of time, in seconds, that the SQL Server script command waits before it times out.

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

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -LoginTimeoutSeconds
Specifies the amount of time, in seconds, that a SQL Server login waits before it times out.

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

### -OutputFilePath
Specifies a file path to store output data from a SQL Server script.

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

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -SQLAuthenticationType
Specifies the SQL Server authentication type.
Valid values are: SQLServerAuthentication and WindowsAuthentication.

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

### -SQLScript
Specifies a SQL Server script.

```yaml
Type: Script
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLScriptType
Specifies a SQL Server script type.
The acceptable values for this parameter are:

- PreInstall
- PostInstall
- PreService
- PostService
- PreUninstall
- PostUninstall

```yaml
Type: SQLScriptCommandType
Parameter Sets: (All)
Aliases: 
Accepted values: PreInstall, PostInstall, PreService, PostService, PreUninstall, PostUninstall

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WarnAndContinueOnError
Indicates whether the script warns the user and continues if the SQL Server script encounters an error while it runs.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SQLScriptCommand
This cmdlet returns a **SQLScriptCommand** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Get-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScript.md)

[Get-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLScriptCommand.md)

[Remove-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSQLScriptCommand.md)

[Set-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLScriptCommand.md)

