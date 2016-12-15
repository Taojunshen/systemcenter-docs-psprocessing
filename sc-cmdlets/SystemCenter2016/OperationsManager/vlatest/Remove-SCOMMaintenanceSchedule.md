---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: c853d66b-7c64-4ca8-bb00-5b4b921ca6a9
schema: 2.0.0
ms.assetid: 85C6F919-4C96-466F-A1EB-16D3C91C5153
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMMaintenanceSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMMaintenanceSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMMaintenanceSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMMaintenanceSchedule

## SYNOPSIS
Removes an existing maintenance schedule.

## SYNTAX

```
Remove-SCOMMaintenanceSchedule [-IDs] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMMaintenanceSchedule** removes an existing maintenance schedule.
If the existing schedule is active, this cmdlet will return an error.

When a resource is in maintenance mode, Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.
A maintenance schedule can be used to schedule a set of resources to go into maintenance mode.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be active on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the Get-Credential cmdlet.
For more information, type `Get-Help Get-Credential`.If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IDs
Specifies the GUID of the schedule to be removed.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.

```yaml
Type: Connection[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Disable-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Disable-SCOMMaintenanceSchedule.md)

[Edit-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Edit-SCOMMaintenanceSchedule.md)

[Enable-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Enable-SCOMMaintenanceSchedule.md)

[Get-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceSchedule.md)

[New-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMMaintenanceSchedule.md)

[Stop-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Stop-SCOMMaintenanceSchedule.md)

[Update-SCOMMaintenanceSchedule](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMMaintenanceSchedule.md)

