---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1124E5F0-C93D-473D-81F0-C3ACBBDC4C30
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Start-SCOMMaintenanceMode.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Start-SCOMMaintenanceMode.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Start-SCOMMaintenanceMode.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Start-SCOMMaintenanceMode

## SYNOPSIS
Puts an object into maintenance mode and creates an active maintenance mode entry.

## SYNTAX

```
Start-SCOMMaintenanceMode [-Instance] <MonitoringObject[]> [-EndTime] <DateTime> [[-Comment] <String>]
 [[-Reason] <MaintenanceModeReason>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCOMMaintenanceMode** cmdlet puts a monitored object, such as a computer or distributed application, into maintenance mode and creates an active maintenance mode entry.
When a resource is in maintenance mode, System Center 2016 - Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.

Specify a class instance to put into maintenance mode and an end time for the maintenance window.
You can also include a comment and a reason for the maintenance mode.
You can use the **Set-SCOMMainenanceMode** cmdlet to update an active maintenance mode entry and use the **Get-SCOMMainenanceMode** cmdlet to get both active and inactive entries.

## EXAMPLES

### Example 1: Put a resource into maintenance mode
```
PS C:\>$Instance = Get-SCOMClassInstance -Name "Server01.Contoso.com"
PS C:\> $Time = ((Get-Date).AddMinutes(10))
PS C:\> Start-SCOMMaintenanceMode -Instance $Instance -EndTime $Time -Comment "Applying software update." -Reason "SecurityIssue"
```

This example puts a resource into maintenance mode for ten minutes.
The first command gets the class instance named Server01.Contoso.com by using the **Get-SCOMClassInstance** cmdlet.

The second command creates a **DateTime** object for ten minutes in the future and then stores it in the $Time variable.

The third command puts the resource defined by the object stored in the $Instance variable into maintenance mode.
Maintenance mode ends at the time stored in the $Time variable.
The command includes a reason for maintenance mode and a comment.

## PARAMETERS

### -Comment
Specifies a comment for the maintenance mode entry.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies when maintenance mode ends, as a **DateTime** object.
A resource cannot be in maintenance mode for fewer than five minutes.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance
Specifies an array of monitoring objects that represent instances.
To obtain monitoring objects, use the **Get-SCOMClassInstance** cmdlet.

This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: MonitoringObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Reason
Specifies a reason for maintenance mode.
The acceptable values for this parameter are:

- PlannedOther
- UnplannedOther
- PlannedHardwareMaintenance
- UnplannedHardwareMaintenance
- PlannedHardwareInstallation
- UnplannedHardwareInstallation
- PlannedOperatingSystemReconfiguration
- UnplannedOperatingSystemReconfiguration
- PlannedApplicationMaintenance
- ApplicationInstallation
- ApplicationUnresponsive
- ApplicationUnstable
- SecurityIssue
- LossOfNetworkConnectivity

```yaml
Type: MaintenanceModeReason
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCOMMaintenanceMode](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceMode.md)

[Set-SCOMMaintenanceMode](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMMaintenanceMode.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

