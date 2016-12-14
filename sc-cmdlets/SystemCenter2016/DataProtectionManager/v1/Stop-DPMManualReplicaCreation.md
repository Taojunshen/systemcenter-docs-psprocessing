---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMDatasource.md
schema: 2.0.0
ms.assetid: 693ECA4D-2792-46E1-B1B0-6F32519BD3EE
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Stop-DPMManualReplicaCreation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Stop-DPMManualReplicaCreation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Stop-DPMManualReplicaCreation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Stop-DPMManualReplicaCreation

## SYNOPSIS
Unmounts a replica VHD after manual data copy.

## SYNTAX

```
Stop-DPMManualReplicaCreation [-Datasource] <Datasource> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-DPMManualReplicaCreation** cmdlet signals that manual data copy on a replica virtual hard disk (VHD) is complete.
It unmounts the replica VHD.
To start the scheduled backups, a consistency check needs to be triggered for the current data source.

## EXAMPLES

### Example 1: Complete manual replica creation of a protected data source
```
PS C:\>$pg = Get-DPMProtectionGroup -DPMServerName "TestingServer"
PS C:\> $ds = Get-DPMDatasource -ProtectionGroup $pg
PS C:\> Stop-DPMManualReplicaCreation -Datasource $ds
```

The first command uses the Get-DPMProtectionGroup cmdlet to get the protection groups on the System Center 2016 - Data Protection Manager (DPM) server named TestingServer.
It stores them in the $pg variable.

The second command uses the Get-DPMDatasource cmdlet to get the data sources protected in the protection group $pg, assuming there is only one protection group.
It stores them in the $ds variable.

The third command unmounts the replica VHD for this data source.
The DPM administrator has to manually trigger a consistency check job on the data source to enable scheduled backup jobs to start.

## PARAMETERS

### -Datasource
Specifies the data source for which manual data copy is complete.

```yaml
Type: Datasource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMProtectionGroup.md)

