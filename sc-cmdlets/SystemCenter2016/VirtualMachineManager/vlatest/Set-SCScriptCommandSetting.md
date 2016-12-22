---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B9F3B33E-F456-4596-A32C-15DEB55E1DA6
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScriptCommandSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScriptCommandSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScriptCommandSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCScriptCommandSetting

## SYNOPSIS
Configures a script command setting.

## SYNTAX

```
Set-SCScriptCommandSetting [-ScriptCommandSetting] <SCScriptCommandSetting> [-AlwaysReboot <Boolean>]
 [-FailOnMatch] [-WarnAndContinueOnMatch] [-MatchExitCode <String>] [-MatchStandardError <String>]
 [-MatchStandardOutput <String>] [-PersistStandardErrorPath <String>] [-PersistStandardOutputPath <String>]
 [-MatchRebootExitCode <String>] [-RestartScriptOnExitCodeReboot <Boolean>] [-WorkingDirectory <String>]
 [-CommandMayReboot] [-RestartOnRetry <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCScriptCommandSetting** cmdlet configures a script command setting.

## EXAMPLES

### Example 1: Update the working directory associated with script command
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $ScriptCommand = Get-SCScriptCommand -ApplicationProfile $AppProfile | where {$_.Name -eq "PreInstall"}
PS C:\> $ScriptCmdSetting = Get-SCScriptCommandSetting -ScriptCommand $ScriptCommand
PS C:\> Set-SCScriptCommandSetting -ScriptCommandSetting $ScriptCmdSetting -WorkingDirectory "Working_Folder_03"
PS C:\> Set-SCScriptCommand -ScriptCommand $ScriptCommand -ScriptCommandSetting $ScriptCmdSetting
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the script command named PreInstall for the application profile stored in $AppProfile, and then stores the object in the $ScriptCommand variable.

The third command gets the script command setting object for the script command stored in $ScriptCommand and stores the object in the $ScriptCmdSetting variable.

The fourth command sets the working directory setting to Working_Folder_03.

The last command updates the script command stored in $ScriptCommand with the settings stored in $ScriptCmdSetting.

## PARAMETERS

### -AlwaysReboot
Indicates whether a computer or virtual machine should always restart after the script has finished running.

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

### -CommandMayReboot
Indicates that the script command may reboot the computer or virtual machine.

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

### -FailOnMatch
Indicates that the action taken when a failure policy is matched is to fail.

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

### -MatchExitCode
Specifies the failure policy exit code.

Example format: `-MatchExitCode "[1-9][0-9]*"`

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

### -MatchRebootExitCode
Specifies the restart policy match exit code.

Example format: `-MatchRebootExitCode "{1641}|{3010}|{3011}"`

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

### -MatchStandardError
Specifies the failure policy standard error.

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

### -MatchStandardOutput
Specifies the failure policy standard output.

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

### -PersistStandardErrorPath
Specifies the file path to store the standard error.

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

### -PersistStandardOutputPath
Specifies the file path to store the standard output.

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

### -RestartOnRetry
Indicates whether a script is restarted upon VMM job restart if the previous job failure was due to a script failure when used in conjunction with **New-SCScriptCommandSetting** or **Set-SCScriptCommandSetting**.

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

### -RestartScriptOnExitCodeReboot
Indicates whether the script restarts after the computer or virtual machine is restarted when an exit code is matched.

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

### -ScriptCommandSetting
Specifies a script command setting object.

```yaml
Type: SCScriptCommandSetting
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WarnAndContinueOnMatch
Indicates that the action taken when a failure policy is matched is to warn the user and continue the operation.

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

### -WorkingDirectory
Specifies a working directory for a script command.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ScriptCommandSetting
This cmdlet returns a **ScriptCommandSetting** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Get-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScriptCommand.md)

[Get-SCScriptCommandSetting](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScriptCommandSetting.md)

[New-SCScriptCommandSetting](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCScriptCommandSetting.md)

[Set-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScriptCommand.md)

