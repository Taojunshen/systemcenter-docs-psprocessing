---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCApplicationDeployment.md
schema: 2.0.0
ms.assetid: 112DC4B2-D252-43EE-BC14-63A678E97218
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCApplicationDeployment

## SYNOPSIS
Adds an application to an application profile.

## SYNTAX

### SQLDac
```
Add-SCApplicationDeployment -SQLDeploymentRunAsAccount <VMMCredential> [-TimeoutSeconds <Int32>]
 [-VMMServer <ServerConnection>] -ApplicationProfile <ApplicationProfile>
 [-ApplicationPackage <ApplicationPackage>] -Name <String> [-SQLDac] [-SQLInstanceName <String>]
 [-DACInstanceName <String>] [-SQLAuthenticationType <String>] [-SkipPolicyValidation <Boolean>]
 [-BlockOnChanges <Boolean>] [-IgnoreDataLoss <Boolean>] [-RollbackOnFailure <Boolean>]
 [-UninstallMode <String>] [-FailDeploymentIfDBExists <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### Script
```
Add-SCApplicationDeployment [-TimeoutSeconds <Int32>] [-RunAsAccount <VMMCredential>]
 [-VMMServer <ServerConnection>] -ApplicationProfile <ApplicationProfile>
 [-ApplicationPackage <ApplicationPackage>] -Name <String> [-Script] [-Executable <String>]
 [-CommandParameters <String>] [-Scriptblock <String>] [-ScriptCommandSetting <SCScriptCommandSetting>]
 [-StandardInput <String>] [-LibraryResource <CustomResource>] [-EnvironmentVariables <Hashtable>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### WebDeploy
```
Add-SCApplicationDeployment [-TimeoutSeconds <Int32>] [-VMMServer <ServerConnection>]
 -ApplicationProfile <ApplicationProfile> [-ApplicationPackage <ApplicationPackage>] -Name <String>
 [-WebDeploy] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCApplicationDeployment** cmdlet adds an application to an application profile.

## EXAMPLES

### Example 1: Add a web application to an application deployment
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppPackage = Get-SCApplicationPackage -Name "WebApp01.zip"
PS C:\> $AppDeployment = Add-SCApplicationDeployment -ApplicationProfile $AppProfile -WebDeploy -Name "SvcWebDeployment01" -ApplicationPackage $AppPackage
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the application package object named WebApp01.zip from the VMM library and stores the object in the $AppPackage variable.

The last command adds the application package stored in $AppPackage to the application profile stored in $AppProfile, and names the application deployment SvcWebDepAD.

## PARAMETERS

### -ApplicationPackage
Specifies an application package object.

```yaml
Type: ApplicationPackage
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockOnChanges
Indicates whether the SQL DAC update is blocked if the database schema is different than that defined in the previous DAC.

```yaml
Type: Boolean
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandParameters
Specifies the parameters for a script or executable program.

```yaml
Type: String
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DACInstanceName
Specifies the name of a data-tier application (DAC) instance.

```yaml
Type: String
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentVariables
Specifies a hash table that contains the environment variables for the application.

```yaml
Type: Hashtable
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Executable
Specifies the name of an executable program.

```yaml
Type: String
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailDeploymentIfDBExists
Indicates whether to proceed with deployment if a database with the same name already exists.

```yaml
Type: Boolean
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreDataLoss
Indicates whether data loss which may occur when updating the SQL Server database is ignored.

```yaml
Type: Boolean
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -LibraryResource
Specifies a resource stored in the Virtual Machine Manager (VMM) library.

```yaml
Type: CustomResource
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

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

### -RollbackOnFailure
Indicates whether to roll back any changes if the SQL Server database update fails.

```yaml
Type: Boolean
Parameter Sets: SQLDac
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
Parameter Sets: Script
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
Valid values are: 

- SQLServerAuthentication
- WindowsAuthentication

```yaml
Type: String
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLDac
Indicates that the application is a SQL Server data-tier application (DAC).

```yaml
Type: SwitchParameter
Parameter Sets: SQLDac
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLDeploymentRunAsAccount
Specifies a Run As account to use to communicate with a SQL Server deployment.

```yaml
Type: VMMCredential
Parameter Sets: SQLDac
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLInstanceName
Specifies the name of a SQL Server instance.

```yaml
Type: String
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Script
Specifies a VMM script object.

```yaml
Type: SwitchParameter
Parameter Sets: Script
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptCommandSetting
Specifies a script command setting object.

```yaml
Type: SCScriptCommandSetting
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scriptblock
Specifies a script block, as a string, for a script application.

```yaml
Type: String
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPolicyValidation
Indicates whether policy validation against the SQL Server database should occur.

```yaml
Type: Boolean
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StandardInput
Specifies a path to a file that contains standard input information to use with the script command.

```yaml
Type: String
Parameter Sets: Script
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds
Specifies the amount of time, in seconds, that a process waits before timing out.

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

### -UninstallMode
Specifies the uninstall mode.
Valid values are: 

- MakeUnmanaged
- DetachDatabase
- DropDatabase

```yaml
Type: String
Parameter Sets: SQLDac
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebDeploy
Indicates that the application is a web application.

```yaml
Type: SwitchParameter
Parameter Sets: WebDeploy
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

## OUTPUTS

### ApplicationDeployment
This cmdlet returns an **ApplicationDeployment** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationDeployment.md)

[Get-SCApplicationPackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationPackage.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Remove-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCApplicationDeployment.md)

[Set-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationDeployment.md)

