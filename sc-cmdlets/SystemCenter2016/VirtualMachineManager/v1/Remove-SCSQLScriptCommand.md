---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCSQLScriptCommand.md
schema: 2.0.0
ms.assetid: 423E287C-924D-459D-B4BC-B72C7C41AF93
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCSQLScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCSQLScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCSQLScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSQLScriptCommand

## SYNOPSIS
Removes a SQL Server script from an application deployment.

## SYNTAX

```
Remove-SCSQLScriptCommand [-SQLScriptCommand] <SCSQLScriptCommand> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSQLScriptCommand** cmdlet removes a SQL Server script from an application deployment.

## EXAMPLES

### Example 1: Remove a SQL Script script from an application deployment
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile -Name "SQLDataTierApp01"
PS C:\> $SQLScript = Get-SCSQLScriptCommand -ApplicationDeployment $AppDeployment | where {$_.DeploymentOrder -eq "1" -and $_.SQLScriptType -eq "PreInstall"}
PS C:\> Remove-SCSQLScriptCommand -SQLScriptCommand $SQLScript
```

The first command gets the application profile object named SvcWebAppProfile01, and then stores that object in the $AppProfile variable.

The second command gets the application deployment object named SQLDataTierApp01 for the application profile stored in $ApplicationProfile, and then stores that object in the $AppDeployment variable.

The third command gets the first PreInstall SQL script associated with the application deployment stored in $AppDeployment.
The cmdlet selects the correct object by specifying a deployment order of 1 and a script type of PreInstall.

The last command removes the SQL Server script stored in $SQLScript.

## PARAMETERS

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCSQLScriptCommand.md)

[Get-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCApplicationProfile.md)

[Get-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCSQLScriptCommand.md)

[Set-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCSQLScriptCommand.md)

