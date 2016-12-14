---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=231755
schema: 2.0.0
ms.assetid: 8DB7C81B-45C3-499A-BC77-AAFB06E2205B
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Set-SCOMMaintenanceMode.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Set-SCOMMaintenanceMode.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Set-SCOMMaintenanceMode.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMMaintenanceMode

## SYNOPSIS
Updates active maintenance mode entries.

## SYNTAX

```
Set-SCOMMaintenanceMode [-MaintenanceModeEntry] <MaintenanceWindow[]> [-PassThru] [-EndTime] <DateTime>
 [[-Comment] <String>] [[-Reason] <MaintenanceModeReason>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMMaintenanceMode** cmdlet updates active maintenance mode entries.
You can use this cmdlet to update only active entries.

When a resource is in maintenance mode, System Center 2016 - Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.

You can change the comment or reason for the maintenance mode.
Use the **Get-SCOMMaintenanceMode** cmdlet to get a maintenance mode entry to update.
Specify an end for the maintenance window.

## EXAMPLES

### Example 1: Update active maintenance mode entries for resources in a domain
```
PS C:\>$NewEndTime = (Get-Date).addDays(1)
PS C:\> Get-SCOMClassInstance -Name "*.Contoso.com" | Get-SCOMMaintenanceMode | Set-SCOMMaintenanceMode -EndTime $NewEndTime -Comment "Updating end time."
```

This example updates all active maintenance mode entries for a specified domain.
The first command creates a **DateTime** object for one day in the future and then stores it in the $NewEndTime variable.

The second command gets all class instances in the Contoso.com domain and uses the pipeline operator (|) to pass the class instance objects to the **Get-SCOMMaintenanceMode** cmdlet, which gets maintenance mode entry objects.
The command uses the pipeline operator to pass these objects to the **Set-SCOMMaintenanceMode** cmdlet.
This cmdlet updates the end time for each object to the **DateTime** object stored in the $NewEndTime variable.
The command also includes a comment for each updated maintenance mode entry.

### Example 2: Update maintenance mode entry for a specified resource
```
PS C:\>$Instance = Get-SCOMClassInstance -Name "Server01.Contoso.com"
PS C:\> $MMEntry = Get-SCOMMaintenanceMode -Instance $Instance
PS C:\> $NewEndTime = (Get-Date).addMinutes(30)
PS C:\> Set-SCOMMaintenanceMode -MaintenanceModeEntry $MMEntry -EndTime $NewEndTime -Comment "Adding 30 minutes to the end time."
```

This example extends maintenance mode for a specified server.
The first command gets the class instance named Server01.Contoso.com and then stores it in the $Instance variable.

The second command gets the maintenance mode entry for the class instance stored in the $Instance variable and stores the entry in the $MMEntry variable.

The third command creates a **DateTime** object for 30 minutes in the future and then stores it in the $NewEndTime variable.

The fourth command updates the maintenance mode session for the maintenance mode entry stored in the $MMEntry variable to the **DateTime** object stored in the $NewEndTime variable and adds a comment.

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
Specifies when maintenance mode ends as a **DateTime** object.
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

### -MaintenanceModeEntry
Specifies an array of **MaintenanceWindow** objects.
To obtain a **MaintenanceWindow** object, use the **Get-SCOMMaintenanceMode** cmdlet.

```yaml
Type: MaintenanceWindow[]
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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMClassInstance.md)

[Get-SCOMMaintenanceMode](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMMaintenanceMode.md)

[Start-SCOMMaintenanceMode](xref:SystemCenter2016/OperationsManager/v1/Start-SCOMMaintenanceMode.md)

