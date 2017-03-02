---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5E8BF1D3-3FF0-47D9-BA82-06FFE31C4F51
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMManualReplicaCreation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMManualReplicaCreation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMManualReplicaCreation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Start-DPMManualReplicaCreation

## SYNOPSIS
Prepares a replica VHD for manual data copy.

## SYNTAX

```
Start-DPMManualReplicaCreation [-Datasource] <Datasource> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMManualReplicaCreation** cmdlet prepares a replica virtual hard disk (VHD) for manual data load on a System Center 2016 - Data Protection Manager (DPM) server.
If a data source is protected with manual replica creation method, this cmdlet mounts the replica VHD and exposes the replica volume so that the DPM administrator can manually copy the data source data on the replica volume.

After the manual copy is complete, use the Stop-DPMManualReplicaCreation cmdlet to unmount the replica VHD.
To start the scheduled backups, a consistency check needs to be triggered for the current data source.

## EXAMPLES

### Example 1: Start manual replica creation of a protected data source
```
PS C:\>$pg = Get-DPMProtectionGroup -DPMServerName "TestingServer"
PS C:\> $ds = Get-DPMDatasource -ProtectionGroup $pg
PS C:\> Start-DPMManualReplicaCreation -Datasource $ds
```

The first command uses the Get-DPMProtectionGroup cmdlet to get the protection groups on the DPM server named TestingServer.
It stores them in the $pg variable.

The second command uses the Get-DPMDatasource cmdlet to get the data sources protected in the protection group $pg (assuming there is only one protection group).
It stores them in the $ds variable.

The third command mounts the replica VHD for this data source and enables the DPM administrator to manually copy the data source data to the replica volume.

## PARAMETERS

### -Datasource
Specifies the data source for which to perform manual data copy.

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

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Stop-DPMManualReplicaCreation](xref:SystemCenter2016/DataProtectionManager/vlatest/Stop-DPMManualReplicaCreation.md)

