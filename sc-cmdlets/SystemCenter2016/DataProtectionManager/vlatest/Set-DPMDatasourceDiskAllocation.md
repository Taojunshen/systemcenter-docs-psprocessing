---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 7B7BA0B5-E99B-4099-879C-AAD8BB9023E6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDiskAllocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDiskAllocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDiskAllocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMDatasourceDiskAllocation

## SYNOPSIS
Changes disk allocation for protected data.

## SYNTAX

### Default (Default)
```
Set-DPMDatasourceDiskAllocation [-Datasource] <Datasource> [-ProtectionGroup] <ProtectionGroup> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Manual
```
Set-DPMDatasourceDiskAllocation [-Datasource] <Datasource> [-ProtectionGroup] <ProtectionGroup> [-Manual]
 [-ReplicaArea <Int64>] [-ShadowCopyArea <Int64>] [-ProductionServerJournalSize <Int64>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### MigrateDatasourceDataFromDPMToVolume
```
Set-DPMDatasourceDiskAllocation [-Datasource] <Datasource> [-ProtectionGroup] <ProtectionGroup>
 [-MigrateDatasourceDataFromDPM] [-DestinationReplicaVolume] <DpmServerVolume>
 [-DestinationShadowCopyVolume] <DpmServerVolume> [-FormatVolumes] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ExpectedDataSizePerClientInMB
```
Set-DPMDatasourceDiskAllocation [[-Datasource] <Datasource>] [-ProtectionGroup] <ProtectionGroup>
 [-ShadowCopyArea <Int64>] -ExpectedDataSizePerClientInMB <Int64> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManualDiskStorage
```
Set-DPMDatasourceDiskAllocation [-Datasource] <Datasource> [-ProtectionGroup] <ProtectionGroup>
 [-TargetStorage] <Volume> [-ReplicaArea <Int64>] [-ExpectedDataSizePerClientInMB <Int64>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Custom
```
Set-DPMDatasourceDiskAllocation [-Datasource] <Datasource> [-ProtectionGroup] <ProtectionGroup>
 [-CustomRequirements] [-ReplicaVolume <DpmServerVolume>] [-ShadowCopyVolume <DpmServerVolume>]
 [-FormatVolumes] [-USNJournalSize <Int64>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MigrateDatasourceDataFromDPMToDisk
```
Set-DPMDatasourceDiskAllocation [-Datasource] <Datasource> [-ProtectionGroup] <ProtectionGroup>
 [-MigrateDatasourceDataFromDPM] [-DestinationDiskPool] <Disk[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AutoGrowOption
```
Set-DPMDatasourceDiskAllocation [-ProtectionGroup] <ProtectionGroup> [-AutoGrow] <Boolean> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMDatasourceDiskAllocation** cmdlet changes disk allocation for protected data.
By default, System Center 2016 - Data Protection Manager (DPM) allocates disk space and volumes for the data source.
The cmdlet gives you the following options for changing disk allocation: 

- Specify the amount of disk space to allocate to each data source in a protection group. 
- Specify the custom replica and shadow copy volumes to use for each data source in a protection group.
- Specify the target volume for each data source in a protection group which uses volume-based storage. 
- Specify destination disk or custom volumes for migration of data.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AutoGrow
Indicates whether DPM increases the size of the replica or recovery point volume automatically when it runs out of user space.

```yaml
Type: Boolean
Parameter Sets: AutoGrowOption
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CustomRequirements
Indicates that you can specify replica and shadow copy volumes manually.

```yaml
Type: SwitchParameter
Parameter Sets: Custom
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies a data source object for which this cmdlet modifies disk allocation.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: Default, Manual, MigrateDatasourceDataFromDPMToVolume, ManualDiskStorage, Custom, MigrateDatasourceDataFromDPMToDisk
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: Datasource
Parameter Sets: ExpectedDataSizePerClientInMB
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DestinationDiskPool
Specifies the set of disks on which DPM allocates volumes to migrate a data source.
This parameter is migration specific.

```yaml
Type: Disk[]
Parameter Sets: MigrateDatasourceDataFromDPMToDisk
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationReplicaVolume
Specifies the destination volume that the user allocates to migrate replicas of a data source.
This parameter is migration specific.

```yaml
Type: DpmServerVolume
Parameter Sets: MigrateDatasourceDataFromDPMToVolume
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationShadowCopyVolume
Specifies the destination volume that the user allocates to migrate shadow copies of a data source.
This parameter is migration specific.

```yaml
Type: DpmServerVolume
Parameter Sets: MigrateDatasourceDataFromDPMToVolume
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpectedDataSizePerClientInMB
Specifies the expected size, in megabytes, of data that DPM backs up from each client computer.

```yaml
Type: Int64
Parameter Sets: ExpectedDataSizePerClientInMB
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: Int64
Parameter Sets: ManualDiskStorage
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FormatVolumes
Indicates that DPM formats the allocated volumes.

```yaml
Type: SwitchParameter
Parameter Sets: MigrateDatasourceDataFromDPMToVolume, Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Manual
Indicates that you can apply DPM settings manually.

```yaml
Type: SwitchParameter
Parameter Sets: Manual
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrateDatasourceDataFromDPM
Indicates that DPM migrates the data source from the current volumes to a new set of volumes.

```yaml
Type: SwitchParameter
Parameter Sets: MigrateDatasourceDataFromDPMToVolume, MigrateDatasourceDataFromDPMToDisk
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: Default, Manual, Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductionServerJournalSize
Specifies the journal size of the protected server.

```yaml
Type: Int64
Parameter Sets: Manual
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReplicaArea
Specifies the disk allocation for the replica area of the current data source.

```yaml
Type: Int64
Parameter Sets: Manual, ManualDiskStorage
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaVolume
Specifies a replica volume object.
A replica volume is a volume on the DPM server that contains the replica of a protected data source.

```yaml
Type: DpmServerVolume
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShadowCopyArea
Specifies the disk allocation for the shadow copy area of the current data source.

```yaml
Type: Int64
Parameter Sets: Manual, ExpectedDataSizePerClientInMB
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShadowCopyVolume
Specifies an object for a shadow copy volume.
This object represents the volume that contains the shadow copy.

```yaml
Type: DpmServerVolume
Parameter Sets: Custom
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetStorage
Specifies a volume in the DPM storage pool that will be used to store the replica virtual hard disk (VHD) for the current data source.

```yaml
Type: Volume
Parameter Sets: ManualDiskStorage
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -USNJournalSize
Specifies the journal size for the update sequence number (USN).

```yaml
Type: Int64
Parameter Sets: Custom
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

### Datasource

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Set-DPMDatasourceDefaultDiskAllocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDefaultDiskAllocation.md)

