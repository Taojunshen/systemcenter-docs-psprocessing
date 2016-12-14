---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMMaintenanceJobStartTime.md
schema: 2.0.0
ms.assetid: 3BE6112C-27FC-4087-81F4-306CC52C0471
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMMaintenanceJobStartTime.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMMaintenanceJobStartTime.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMMaintenanceJobStartTime.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMMaintenanceJobStartTime

## SYNOPSIS
Gets the start times of DPM maintenance jobs.

## SYNTAX

```
Get-DPMMaintenanceJobStartTime [[-DPMServerName] <String>] [-MaintenanceJob] <HouseKeepingJobs>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMMaintenanceJobStartTime** cmdlet returns the start times of maintenance jobs for System Center 2016 - Data Protection Manager (DPM).
Maintenance jobs include catalog pruning and detailed inventory.

## EXAMPLES

### Example 1: Get start time for catalog pruning
```
PS C:\>Get-DPMMaintenanceJobStartTime -DPMServerName "TestServer" -MaintenanceJob CatalogPruning
```

This command returns the time when catalog pruning is scheduled to run on the DPM server named TestServer.

## PARAMETERS

### -DPMServerName
Specifies the name of the DPM server.
This cmdlet gets maintenance jobs for the server that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaintenanceJob
Specifies a maintenance job that this cmdlet performs on the replica.

The acceptable values for this parameter are:

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DateTime

## NOTES

## RELATED LINKS

[Set-DPMMaintenanceJobStartTime](xref:SystemCenter2016/DataProtectionManager/v1.0/Set-DPMMaintenanceJobStartTime.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/v1.0/DataProtectionManager.md)

