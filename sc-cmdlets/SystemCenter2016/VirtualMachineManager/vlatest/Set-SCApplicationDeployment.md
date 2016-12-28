---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DDFF727B-56BC-4F40-AF7B-DF63467E5B12
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCApplicationDeployment

## SYNOPSIS
Modifies an application deployment.

## SYNTAX

```
Set-SCApplicationDeployment [-SQLInstanceName <String>] [-SQLDeploymentRunAsAccount <VMMCredential>]
 [-Executable <String>] [-CommandParameters <String>] [-Scriptblock <String>]
 [-ScriptCommandSetting <SCScriptCommandSetting>] [-TimeoutSeconds <Int32>] [-StandardInput <String>]
 [-LibraryResource <CustomResource>] [-EnvironmentVariables <Hashtable>] [-RunAsAccount <VMMCredential>]
 [-VMMServer <ServerConnection>] [-ApplicationDeployment] <ApplicationDeployment>
 [-ApplicationPackage <ApplicationPackage>] [-Name <String>] [-DACInstanceName <String>]
 [-SQLAuthenticationType <String>] [-SkipPolicyValidation <Boolean>] [-BlockOnChanges <Boolean>]
 [-IgnoreDataLoss <Boolean>] [-RollbackOnFailure <Boolean>] [-UninstallMode <String>]
 [-FailDeploymentIfDBExists <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCApplicationDeployment** cmdlet modifies an application deployment.

## EXAMPLES

### Example 1: Update the application package for a web application deployment
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -Name "SvcWebDeployment01" -ApplicationProfile $AppProfile 
PS C:\> $AppPackage = Get-SCApplicationPackage -Name "WebApp02.zip"
PS C:\> Set-SCApplicationDeployment -ApplicationDeployment $AppDeployment -ApplicationPackage $AppPackage
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the application deployment object named SvcWebDeployment01 for the application profile stored in $AppProfile, and then stores the object in the $AppDeployment variable.

The third command gets the application package object named WebApp02.zip from the VMM library and stores the object in the $AppPackage variable.

The last command updates the application deployment stored in $AppDeployment by replacing the previous application package with the one stored in $AppPackage.

## PARAMETERS

### -ApplicationDeployment
Specifies an application deployment object.

```yaml
Type: ApplicationDeployment
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -BlockOnChanges
Indicates whether the SQL DAC update is blocked if the database schema is different than that defined in the previous DAC.

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

### -DACInstanceName
Specifies the name of a data-tier application (DAC) instance.

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

### -EnvironmentVariables
Specifies a hashtable that contains the environment variables for the application.

```yaml
Type: Hashtable
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailDeploymentIfDBExists


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

### -IgnoreDataLoss
Indicates whether data loss which may occur when updating the SQL Server database is ignored.

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
Parameter Sets: (All)
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

### -RollbackOnFailure
Rolls back any changes made if the SQL Server database update fails.

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
The acceptable values for this parameter are:

- SQLServerAuthentication
- WindowsAuthentication

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

### -SQLDeploymentRunAsAccount
Specifies a Run As account to use to communicate with a SQL Server deployment.

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

### -SQLInstanceName
Specifies the name of a SQL Server instance.

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

### -ScriptCommandSetting
Specifies a script command setting object.

```yaml
Type: SCScriptCommandSetting
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
The acceptable values for this parameter are:

- MakeUnmanaged
- DetachDatabase
- DropDatabase

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ApplicationDeployment
This cmdlet returns an **ApplicationDeployment** object.

## NOTES

## RELATED LINKS

[Add-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationDeployment.md)

[Get-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationDeployment.md)

[Get-SCApplicationPackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationPackage.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Remove-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCApplicationDeployment.md)

