---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 61CB0E83-27CE-4F9E-BF21-22AEF4C2B9CB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSQLScriptCommand

## SYNOPSIS
Gets a SQL Server script for an application deployment.

## SYNTAX

```
Get-SCSQLScriptCommand [-VMMServer <ServerConnection>] -ApplicationDeployment <ApplicationDeployment>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSQLScriptCommand** cmdlet gets a Microsoft SQL Server script for an application deployment.

## EXAMPLES

### Example 1: Get a specified SQL Server script command for an application deployments
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile -Name "SQLDataTierApp01"
PS C:\> Get-SCSQLScriptCommand -ApplicationDeployment $AppDeployment | where {$_.DeploymentOrder -eq "1" -and $_.SQLScriptType -eq "PreInstall"}
```

The first command gets the application profile object named SvcWebAppProfile01, and then stores that object in the $AppProfile variable.

The second command gets the application deployment object named SQLDataTierApp01 for the application profile stored in $AppProfile, and then stores that object in the $AppDeployment variable.

The last command gets the first PreInstall SQL Server script associated with the application deployment stored in $AppDeployment.
The cmdlet selects the correct object by specifying a deployment order of 1 and a script type of PreInstall.

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

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### SQLScriptCommand
This cmdlet returns a **SQLScriptCommand** object.

## NOTES

## RELATED LINKS

[Add-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLScriptCommand.md)

[Get-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Remove-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSQLScriptCommand.md)

[Set-SCSQLScriptCommand](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLScriptCommand.md)

