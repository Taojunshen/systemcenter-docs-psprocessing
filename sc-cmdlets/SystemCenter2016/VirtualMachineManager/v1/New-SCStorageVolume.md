---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageVolume.md
schema: 2.0.0
ms.assetid: 0B6E9A8F-41E8-4EB2-AA02-CC9D6608B62E
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCStorageVolume.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCStorageVolume.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCStorageVolume.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageVolume

## SYNOPSIS
Creates a storage volume.

## SYNTAX

### NewVolumeOnArray
```
New-SCStorageVolume [-VMMServer <ServerConnection>] -Name <String> -StoragePool <StoragePool>
 -SizeInBytes <UInt64> -FileSystem <String> -StorageArray <StorageArray> [-ResiliencySettingName <String>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-GuidPartitionTable]
 [-RequiredPartitionSize <UInt64>] [-DedupMode <DedupMode>] [-AllocationUnitSizeKB <UInt32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewVolume
```
New-SCStorageVolume [-VMMServer <ServerConnection>] -Name <String> -StoragePool <StoragePool>
 -SizeInBytes <UInt64> -FileSystem <String> -StorageFileServer <StorageFileServer>
 [-ResiliencySettingName <String>] [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>]
 [-GuidPartitionTable] [-RequiredPartitionSize <UInt64>] [-DedupMode <DedupMode>]
 [-AllocationUnitSizeKB <UInt32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### NewVolumeTiered
```
New-SCStorageVolume [-VMMServer <ServerConnection>] -Name <String> -StoragePool <StoragePool>
 -FileSystem <String> -StorageFileServer <StorageFileServer> [-ReadCacheSizeMB <UInt64>] -JobGroup <Guid>
 [-GuidPartitionTable] [-RequiredPartitionSize <UInt64>] [-DedupMode <DedupMode>]
 [-AllocationUnitSizeKB <UInt32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### NewVolumeTieredOnArray
```
New-SCStorageVolume [-VMMServer <ServerConnection>] -Name <String> -StoragePool <StoragePool>
 -FileSystem <String> -StorageArray <StorageArray> [-ReadCacheSizeMB <UInt64>] -JobGroup <Guid>
 [-GuidPartitionTable] [-RequiredPartitionSize <UInt64>] [-DedupMode <DedupMode>]
 [-AllocationUnitSizeKB <UInt32>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageVolume** cmdlet creates a storage volume in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Create a tiered storage volume
```
PS C:\>$StorageArray = Get-SCStorageArray -Name "HCArray" 
PS C:\> $StoragePool = Get-SCStoragePool -Name "S2DPool" 
PS C:\> New-SCStorageTier -StorageTierFriendlyName "Performance" -StorageTierSizeInMB 1024 -RunAsynchronously -JobGroup "191de146-dbec-4955-a347-70edd4315c41" 
PS C:\> New-SCStorageTier -StorageTierFriendlyName "Capacity" -StorageTierSizeInMB 1024 -RunAsynchronously -JobGroup "191de146-dbec-4955-a347-70edd4315c41" 
PS C:\> New-SCStorageVolume -StorageArray $StorageArray -StoragePool $storagePool -Name "Volume1" -RunAsynchronously -JobGroup "191de146-dbec-4955-a347-70edd4315c41" -FileSystem "CSVFS_NTFS"
```

The first command gets a storage array named HCArray, and then stores it in the $StorageArray variable.

The second command gets a storage pool named S2DPool, and then stores it in the $StoragePool variable.

The third and fourth commands create storage tiers by using the configuration of global tiers named Performance and Capacity.
These are existing tiers.

The fifth command creates a tiered volume on hyper converged system.
The command uses the values created in the previous commands.
Make sure that the job group ID is the same as in the previous commands.

## PARAMETERS

### -AllocationUnitSizeKB
Specifies the allocation size of a volume, in kilobytes.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DedupMode
Apply deduplication on the volume or file share based on the workload.
The acceptable values for this parameter are:

- 0 - Disabled
- 1 - GeneralPurpose
- 2 - Hyper-V
- 3 - Backup

```yaml
Type: DedupMode
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, GeneralPurpose, HyperV, Backup, NotAvailable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
Specifies the file system of a storage volume.
The acceptable values for this parameter are:

- CSVFS_NTFS 
- CSVFS_ReFS

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: NTFS, ReFS, CSVFS_NTFS, CSVFS_ReFS

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GuidPartitionTable


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

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: NewVolumeTiered, NewVolumeTieredOnArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumns
Specifies the number of columns for a virtual disk.

```yaml
Type: UInt16
Parameter Sets: NewVolumeOnArray, NewVolume
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDiskRedundancy
Specifies the number of physical disk failures a virtual disk can sustain.

```yaml
Type: UInt16
Parameter Sets: NewVolumeOnArray, NewVolume
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadCacheSizeMB
Specifies cache size, in megabytes, for tiered virtual disk.

```yaml
Type: UInt64
Parameter Sets: NewVolumeTiered, NewVolumeTieredOnArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredPartitionSize


```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingName
Specifies the resiliency setting for a virtual disk.
The acceptable values for this parameter are:

- Mirror 
- Parity

```yaml
Type: String
Parameter Sets: NewVolumeOnArray, NewVolume
Aliases: 
Accepted values: Simple, Mirror, Parity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -SizeInBytes


```yaml
Type: UInt64
Parameter Sets: NewVolumeOnArray, NewVolume
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageArray
Specifies a storage array object.

```yaml
Type: StorageArray
Parameter Sets: NewVolumeOnArray, NewVolumeTieredOnArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFileServer
Specifies a storage file server object.

```yaml
Type: StorageFileServer
Parameter Sets: NewVolume, NewVolumeTiered
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies a storage pool object.

```yaml
Type: StoragePool
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

## NOTES

## RELATED LINKS

[Get-SCStorageVolume](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageVolume.md)

[Set-SCStorageVolume](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageVolume.md)

