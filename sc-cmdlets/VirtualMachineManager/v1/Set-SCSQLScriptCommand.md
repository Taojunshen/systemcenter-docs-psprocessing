---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCSQLScriptCommand.md
schema: 2.0.0
ms.assetid: B1637C30-6110-4781-B716-DCEA10609CE0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCSQLScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCSQLScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCSQLScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSQLScriptCommand

## SYNOPSIS
Modifies the properties of a SQL Server script.

## SYNTAX

```
Set-SCSQLScriptCommand [-SQLScriptType <SQLScriptCommandType>] [-DeploymentOrder <Int32>]
 [-LoginTimeoutSeconds <Int32>] [-ExecutionTimeoutSeconds <Int32>] [-RunAsAccount <VMMCredential>]
 [-SQLAuthenticationType <String>] [-SQLScriptCommand] <SCSQLScriptCommand> [-SQLScript <Script>]
 [-CommandParameters <String>] [-OutputFilePath <String>] [-EncryptConnection <Boolean>]
 [-DatabaseName <String>] [-WarnAndContinueOnError <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSQLScriptCommand** cmdlet modifies the properties of a SQL Server script associated with an application deployment.

## EXAMPLES

### Example 1: Modify a SQL Server script command
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile -Name "SQLDataTierApp01"
PS C:\> $SQLScript = Get-SCSQLScriptCommand -ApplicationDeployment $AppDeployment | where {$_.DeploymentOrder -eq "1" -and $_.SQLScriptType -eq "PreInstall"}
PS C:\> Set-SCSQLScriptCommand -SQLScriptCommand $SQLScript -DatabaseName "MSOrders"
```

The first command gets the application profile object named SvcWebAppProfile01, and then stores it in the $AppProfile variable.

The second command gets the application deployment object named SQLDataTierApp01 for the application profile stored in $ApplicationProfile, and then stores that object in the $AppDeployment variable.

The third command gets the first PreInstall SQL Server script object associated with the application deployment stored in $AppDeployment, and then stores the object in the $SQLScript variable.
The cmdlet selects the correct object by specifying a deployment order of 1 and a script type of PreInstall.

The last command modifies the database against which the SQL Server script stored $SQLScript will run.

## PARAMETERS

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

Required: False
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLScriptCommand
Specifies a SQL Server script command object.

```yaml
Type: SCSQLScriptCommand
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

Required: False
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

[Add-SCSQLScriptCommand](xref:VirtualMachineManager/v1/Add-SCSQLScriptCommand.md)

[Get-SCApplicationDeployment](xref:VirtualMachineManager/v1/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:VirtualMachineManager/v1/Get-SCApplicationProfile.md)

[Get-SCSQLScriptCommand](xref:VirtualMachineManager/v1/Get-SCSQLScriptCommand.md)

[Remove-SCSQLScriptCommand](xref:VirtualMachineManager/v1/Remove-SCSQLScriptCommand.md)

