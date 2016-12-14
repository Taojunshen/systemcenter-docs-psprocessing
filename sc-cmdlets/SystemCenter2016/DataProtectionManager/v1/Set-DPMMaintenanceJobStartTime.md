---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMMaintenanceJobStartTime.md
schema: 2.0.0
ms.assetid: 61D976F7-143B-4A66-AD94-DFA8BE56C272
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMMaintenanceJobStartTime.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMMaintenanceJobStartTime.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMMaintenanceJobStartTime.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMMaintenanceJobStartTime

## SYNOPSIS
Sets the start time of a maintenance job or stops such a job from running.

## SYNTAX

### Reset (Default)
```
Set-DPMMaintenanceJobStartTime [[-DPMServerName] <String>] [-MaintenanceJob] <HouseKeepingJobs>
 [[-StartTime] <DateTime>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Remove
```
Set-DPMMaintenanceJobStartTime [[-DPMServerName] <String>] [-MaintenanceJob] <HouseKeepingJobs> [-Remove]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMMaintenanceJobStartTime** cmdlet sets the start time of a maintenance job or stops such a job if it is running in System Center 2016 - Data Protection Manager (DPM).

You can reschedule Catalog Pruning and Detailed Inventory jobs by using this cmdlet.

## EXAMPLES

### Example 1: Set the start time for a job
```
PS C:\>Set-DPMMaintenanceJobStartTime -DPMServerName "DPMServer07" -MaintenanceJob CatalogPruning -StartTime 02:00
```

This command schedules the CatalogPruning maintenance job to run on the DPM server named DPMServer07 at 2 AM.

### Example 2: Stop a running job
```
PS C:\>Set-DPMMaintenanceJobStartTime -DPMServerName "DPMServer07" -MaintenanceJob LibraryInventory -Remove
```

This command stops the LibraryInventory job from running on the DPM server named DPMServer07.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet sets a maintenance job.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaintenanceJob
Specifies the maintenance job that the cmdlet performs on the replica.
Valid values are: 

- CatalogPruning.
Removes index entries for expired tapes.
- DetailedInventory.
Identifies new tapes and recognizes tapes DPM has seen before by reading the on-media identifier (OMID) on each tape.

```yaml
Type: HouseKeepingJobs
Parameter Sets: (All)
Aliases: 
Accepted values: CatalogPruning, LibraryInventory

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Indicates that the cmdlet stops the job that is currently running.

```yaml
Type: SwitchParameter
Parameter Sets: Remove
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the time when the operation starts as a **DateTime** object.

```yaml
Type: DateTime
Parameter Sets: Reset
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-DPMMaintenanceJobStartTime](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMMaintenanceJobStartTime.md)

