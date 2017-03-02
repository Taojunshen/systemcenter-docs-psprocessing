---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0242D950-E3CF-4C0A-AA05-7262F91770B5
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlertHistory.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlertHistory.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlertHistory.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOMAlertHistory

## SYNOPSIS
Gets history entries for alerts.

## SYNTAX

```
Get-SCOMAlertHistory [-Alert] <MonitoringAlert[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMAlertHistory** cmdlet gets history entries for one or many alerts.

## EXAMPLES

### Example 1: Get the history of alerts
```
PS C:\>Get-SCOMAlert -Name "*heartbeat*" | Get-SCOMAlertHistory | Format-Table, ResolutionState, Owner, ModifiedBy, Comments
```

This command gets all alerts with heartbeat in their name and passes the alerts to the **Get-SCOMAlertHistory** cmdlet by using the pipe operator.
The **Get-SCOMAlertHistory** cmdlet returns the history for each alert.
The **Format-Table** cmdlet displays the values for the **ResolutionState**, **Owner**, **ModifiedBy**, and **Comments** properties for each alert.

## PARAMETERS

### -Alert
Specifies an array of **MonitoringAlert** objects.
To obtain a **MonitoringAlert** object, use the **Get-SCOMAlert** cmdlet.

```yaml
Type: MonitoringAlert[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMAlert](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlert.md)

