---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPROMonitorState.md
schema: 2.0.0
ms.assetid: 5FC7CA24-2588-4200-AE05-DB58132DB21B
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Reset-SCPROMonitorState.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Reset-SCPROMonitorState.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Reset-SCPROMonitorState.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Reset-SCPROMonitorState

## SYNOPSIS
Resets the state of a specified PRO monitor.

## SYNTAX

```
Reset-SCPROMonitorState [-VMMServer <ServerConnection>] -PROMonitorState <PROMonitorState> [<CommonParameters>]
```

## DESCRIPTION
The **Reset-SCPROMonitorState** cmdlet resets the state of a specified Performance and Resource Optimization (PRO) monitor.

## EXAMPLES

### Example 1: Reset a PRO monitor state
```
PS C:\>$VMHost = Get-SCVMHost "VMHost01.Contoso.com"
PS C:\> $PROMonitorState = @(Get-SCPROMonitorState -VMHost $VMHost)
PS C:\> Reset-SCProMonitorState -PROMonitorState $PROMonitorState[0]
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second comand gets all PRO monitor state objects on VMHost01 and stores the objects in the $PROMonitorState object array.
This example assumes that there are multiple PRO monitors on VMHost01.

The last command resets the first PRO monitor state object stored in $PROMonitorState.

## PARAMETERS

### -PROMonitorState
Specifies a PRO monitor state object.

```yaml
Type: PROMonitorState
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

### PROMonitorState
This cmdlet returns a **PROMonitorState** object.

## NOTES

## RELATED LINKS

[Get-SCPROMonitorState](xref:VirtualMachineManager/v1/Get-SCPROMonitorState.md)

[Get-SCVMHost](xref:VirtualMachineManager/v1/Get-SCVMHost.md)

