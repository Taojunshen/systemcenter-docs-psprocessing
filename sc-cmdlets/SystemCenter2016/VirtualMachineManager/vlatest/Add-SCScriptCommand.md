---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 03D1FB64-DF68-491F-BCFD-B978D9EE009C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCScriptCommand

## SYNOPSIS
Adds a script command to an application profile, application deployment, or host profile.

## SYNTAX

### ApplicationProfile
```
Add-SCScriptCommand -ApplicationProfile <ApplicationProfile> [-Executable <String>]
 [-CommandParameters <String>] [-ScriptCommandSetting <SCScriptCommandSetting>] -ScriptType <ScriptCommandType>
 [-TimeoutSeconds <Int32>] [-StandardInput <String>] [-LibraryResource <CustomResource>]
 [-RunAsAccount <VMMCredential>] [-VMMServer <ServerConnection>] [-DeploymentOrder <Int32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### ApplicationDeployment
```
Add-SCScriptCommand -ApplicationDeployment <ApplicationDeployment> [-Executable <String>]
 [-CommandParameters <String>] [-ScriptCommandSetting <SCScriptCommandSetting>] -ScriptType <ScriptCommandType>
 [-TimeoutSeconds <Int32>] [-StandardInput <String>] [-LibraryResource <CustomResource>]
 [-RunAsAccount <VMMCredential>] [-VMMServer <ServerConnection>] [-DeploymentOrder <Int32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### PhysicalComputerProfile
```
Add-SCScriptCommand -PhysicalComputerProfile <PhysicalComputerProfile> [-Executable <String>]
 [-CommandParameters <String>] [-ScriptCommandSetting <SCScriptCommandSetting>] -ScriptType <ScriptCommandType>
 [-TimeoutSeconds <Int32>] [-StandardInput <String>] [-LibraryResource <CustomResource>]
 [-RunAsAccount <VMMCredential>] [-VMMServer <ServerConnection>] [-JobGroup <Guid>] [-DeploymentOrder <Int32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### JobGroup
```
Add-SCScriptCommand [-Executable <String>] [-CommandParameters <String>]
 [-ScriptCommandSetting <SCScriptCommandSetting>] -ScriptType <ScriptCommandType> [-TimeoutSeconds <Int32>]
 [-StandardInput <String>] [-LibraryResource <CustomResource>] [-RunAsAccount <VMMCredential>]
 [-VMMServer <ServerConnection>] [-JobGroup <Guid>] [-DeploymentOrder <Int32>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCScriptCommand** cmdlet adds a script command to an application profile, application deployment, or host profile.
A script command allows an Administrator to run code during deployment and servicing operations.

## EXAMPLES

### Example 1: Add a script command to an application profile
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $ScriptSetting = New-SCScriptCommandSetting -WorkingDirectory "Working_Folder_01"
PS C:\> Add-SCScriptCommand -ApplicationProfile $AppProfile -Executable "Startup.ps1" -ScriptType "PreInstall" -ScriptCommandSetting $ScriptSetting -TimeoutSeconds 120
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command creates a script command setting object that sets the working directory to Payload, and then stores the object in the $ScriptSetting variable.

The last command adds a preinstall script command to the application profile stored in $AppProfile.

## PARAMETERS

### -ApplicationDeployment
Specifies an application deployment object.

```yaml
Type: ApplicationDeployment
Parameter Sets: ApplicationDeployment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: ApplicationProfile
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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: PhysicalComputerProfile, JobGroup
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

### -PhysicalComputerProfile
Specifies a profile that is used to deploy an operating system to a computer.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: PhysicalComputerProfile
Aliases: VMHostProfile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -ScriptType
Specifies a script type.
The acceptable values for this parameter are:

- PreInstall
- PostInstall
- SaveState
- RestoreState
- PreService
- PostService
- PreUninstall
- PostUninstall
- OrderedCommand
- BareMetalPostWinPERegistration
- OnProvisionFirst
- OnProvisionRest
- OnDeleteLast
- OnDeleteRest
- Install
- BareMetalPostDeployment

```yaml
Type: ScriptCommandType
Parameter Sets: (All)
Aliases: 
Accepted values: PreService, PostService, SaveState, RestoreState, PreInstall, PostInstall, PreUninstall, PostUninstall, OrderedCommand, BareMetalPostWinPERegistration, OnProvisionFirst, OnProvisionRest, OnDeleteLast, OnDeleteRest, Install, BareMetalPostConfiguration, BareMetalPostUnattend

Required: True
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

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

```yaml
Type: ServerConnection
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

### ScriptCommand
This cmdlet returns a **ScriptCommand** object.

## NOTES

## RELATED LINKS

[Get-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScriptCommand.md)

[Invoke-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCScriptCommand.md)

[Remove-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCScriptCommand.md)

[Set-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScriptCommand.md)

