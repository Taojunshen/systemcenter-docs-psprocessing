---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCApplicationProfile.md
schema: 2.0.0
ms.assetid: B602F946-1AEC-461F-8B3E-473A55D88BC3
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCScriptCommandSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCScriptCommandSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCScriptCommandSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCScriptCommandSetting

## SYNOPSIS
Gets the settings for a script command.

## SYNTAX

```
Get-SCScriptCommandSetting -ScriptCommand <SCScriptCommand> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCScriptCommandSetting** cmdlet gets the settings that have been configured on a script command.

## EXAMPLES

### Example 1: Get the script command settings for a specific script command
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $ScriptCommand = Get-SCScriptCommand -ApplicationProfile $AppProfile | Where {$_.Name -eq "PostInstall"}
PS C:\> Get-SCScriptCommandSetting -ScriptCommand $ScriptCommand
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the script command object named PostInstall and stores the object in the $ScriptCommand variable.

The last command gets the script command settings for the script command stored in $ScriptCommand and displays the settings for the user.

## PARAMETERS

### -ScriptCommand
Specifies a script command object.

```yaml
Type: SCScriptCommand
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCApplicationProfile.md)

[Get-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCScriptCommand.md)

[New-SCScriptCommandSetting](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCScriptCommandSetting.md)

[Set-SCScriptCommandSetting](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCScriptCommandSetting.md)

