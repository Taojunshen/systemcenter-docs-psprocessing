---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCScriptCommand.md
schema: 2.0.0
ms.assetid: 2301046C-E339-498D-B78D-6824CBEAB7DE
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCScriptCommand

## SYNOPSIS
Configures a script command.

## SYNTAX

```
Set-SCScriptCommand [-ScriptCommand] <SCScriptCommand> [-Executable <String>] [-CommandParameters <String>]
 [-ScriptCommandSetting <SCScriptCommandSetting>] [-ScriptType <ScriptCommandType>] [-TimeoutSeconds <Int32>]
 [-StandardInput <String>] [-LibraryResource <CustomResource>] [-RunAsAccount <VMMCredential>]
 [-JobGroup <Guid>] [-DeploymentOrder <Int32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCScriptCommand** cmdlet configures a script command.

## EXAMPLES

### Example 1: Add a custom resource to a script command
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $ScriptCommand = Get-SCScriptCommand -ApplicationProfile $AppProfile | where {$_.Name -eq "PreInstall"}
PS C:\> $Resource = Get-SCCustomResource -Name "CustomResource.cr"
PS C:\> Set-SCScriptCommand -ScriptCommand $ScriptCommand -LibraryResource $Resource
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the script command object named PreInstall and stores the object in the $ScriptCommand variable.

The third command gets the resource object named CustomResource and stores the object in the $Resource variable.

The last command adds the resource object stored in $Resource to the script command object stored in $ScriptCommand.

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
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

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
Specifies a resource stored in the VMM library.

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

### -ScriptCommand
Specifies a script command object.

```yaml
Type: SCScriptCommand
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

```yaml
Type: ScriptCommandType
Parameter Sets: (All)
Aliases: 
Accepted values: PreService, PostService, SaveState, RestoreState, PreInstall, PostInstall, PreUninstall, PostUninstall, OrderedCommand, BareMetalPostWinPERegistration, OnProvisionFirst, OnProvisionRest, OnDeleteLast, OnDeleteRest, Install, BareMetalPostConfiguration, BareMetalPostUnattend

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ScriptCommand
This cmdlet returns a **ScriptCommand** object.

## NOTES

## RELATED LINKS

[Add-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCScriptCommand.md)

[Get-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCScriptCommand.md)

[Invoke-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1.0/Invoke-SCScriptCommand.md)

[Remove-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCScriptCommand.md)

