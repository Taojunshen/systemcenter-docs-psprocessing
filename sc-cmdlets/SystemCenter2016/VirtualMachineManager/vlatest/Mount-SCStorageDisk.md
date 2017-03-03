---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6B2BAC47-686D-4395-B9F3-50FADD0F77D2
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Mount-SCStorageDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Mount-SCStorageDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Mount-SCStorageDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Mount-SCStorageDisk

## SYNOPSIS
Mounts a storage disk.

## SYNTAX

### Default (Default)
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> [-StorageLogicalUnit <StorageLogicalUnit>]
 [-MountPoint <String>] [-CreateClusterSharedVolume] [-DeleteClusterSharedVolume] [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### QuickFormatGPT
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> [-QuickFormat] [-ForceFormat] [-GuidPartitionTable]
 [-DesiredUnitAllocationSizeBytes <UInt32>] [-MountPoint <String>] [-CreateClusterSharedVolume]
 [-DeleteClusterSharedVolume] [-VolumeLabel <String>] [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ForceNewDiskIdGuid
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> -DiskId <Guid> [-MountPoint <String>]
 [-CreateClusterSharedVolume] [-DeleteClusterSharedVolume] [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ForceNewDiskIdSignature
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> [-MountPoint <String>] [-CreateClusterSharedVolume]
 [-DeleteClusterSharedVolume] -DiskSignature <String> [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### QuickFormatMBR
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> [-QuickFormat] [-ForceFormat] [-MasterBootRecord]
 [-DesiredUnitAllocationSizeBytes <UInt32>] [-MountPoint <String>] [-CreateClusterSharedVolume]
 [-DeleteClusterSharedVolume] [-VolumeLabel <String>] [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### FullFormatMBR
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> [-FullFormat] [-ForceFormat] [-MasterBootRecord]
 [-DesiredUnitAllocationSizeBytes <UInt32>] [-MountPoint <String>] [-CreateClusterSharedVolume]
 [-DeleteClusterSharedVolume] [-VolumeLabel <String>] [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### FullFormatGPT
```
Mount-SCStorageDisk -StorageDisk <StorageDisk> [-FullFormat] [-ForceFormat] [-GuidPartitionTable]
 [-DesiredUnitAllocationSizeBytes <UInt32>] [-MountPoint <String>] [-CreateClusterSharedVolume]
 [-DeleteClusterSharedVolume] [-VolumeLabel <String>] [-JobGroup <Guid>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ClusterFormatMBR
```
Mount-SCStorageDisk -StorageLogicalUnit <StorageLogicalUnit> [-FullFormat] [-QuickFormat] [-ForceFormat]
 [-MasterBootRecord] [-DesiredUnitAllocationSizeBytes <UInt32>] [-MountPoint <String>]
 [-CreateClusterSharedVolume] [-DeleteClusterSharedVolume] [-VolumeLabel <String>] -JobGroup <Guid>
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ClusterFormatGPT
```
Mount-SCStorageDisk -StorageLogicalUnit <StorageLogicalUnit> [-FullFormat] [-QuickFormat] [-ForceFormat]
 [-GuidPartitionTable] [-DesiredUnitAllocationSizeBytes <UInt32>] [-MountPoint <String>]
 [-CreateClusterSharedVolume] [-DeleteClusterSharedVolume] [-VolumeLabel <String>] -JobGroup <Guid>
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-SCStorageDisk** cmdlet mounts a storage disk.

## EXAMPLES

### Example 1: Format a new disk
```
PS C:\> $JobGroup = [Guid]::NewGuid().ToString()
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $LU = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> Register-SCStorageLogicalUnit -StorageLogicalUnit $LU -VMHost $VMHost -JobGroup $JobGroup
PS C:\> Mount-SCStorageDisk -QuickFormat -MasterBootRecord -VolumeLabel "New Volume" -StorageLogicalUnit $LU -MountPoint "S:\" -JobGroup $JobGroup
PS C:\> Set-SCVMHost -VMHost $VMHost -JobGroup $JobGroup
```

The first command generates a GUID, and then stores the GUID as a string in the $JobGroup variable.
Subsequent commands that include this GUID are collected into a single job group.

The second command gets the host object named VMHost01 by using the **Get-SCVMHost** cmdlet.
The command stores that object in the $VMHost variable.

The third command gets the storage logical unit object named LUN01 by using the **Get-SCStorageLogicalUnit** cmdlet.
The command stores that object in the $LU variable.

The fourth command registers LUN01 with VMHost01 by using the **Register-SCStorageLogicalUnit** cmdlet.
This command specifies the *JobGroup* parameter.
Therefore, this command does not run until just before the final command that includes the job group that has the same GUID.

The fifth command mounts the storage logical unit in $LU on VMHost01.
The command performs a quick format on the volume, labels the volume New Volume, and sets the mount point to S:\.
This command specifies *JobGroup*.

The last command updates VMHost01 with the mounted storage disk.
This command specifies the *JobGroup* parameter to register and mount LUN01 prior to running the **Set-SCVMHost** cmdlet.

## PARAMETERS

### -CreateClusterSharedVolume
Indicates that the cmdlet creates a Cluster Shared Volume.

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

### -DeleteClusterSharedVolume
Indicates that the cmdlet deletes a Cluster Shared Volume.

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

### -DesiredUnitAllocationSizeBytes
Specifies the size, in bytes, of the default allocation of a volume.

```yaml
Type: UInt32
Parameter Sets: QuickFormatGPT, QuickFormatMBR, FullFormatMBR, FullFormatGPT, ClusterFormatMBR, ClusterFormatGPT
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskId
Specifies the ID of a disk object.

```yaml
Type: Guid
Parameter Sets: ForceNewDiskIdGuid
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSignature
Specifies the signature of a disk object.

```yaml
Type: String
Parameter Sets: ForceNewDiskIdSignature
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceFormat
Forces the formatting of the storage disk even if volumes are already present.

```yaml
Type: SwitchParameter
Parameter Sets: QuickFormatGPT, QuickFormatMBR, FullFormatMBR, FullFormatGPT, ClusterFormatMBR, ClusterFormatGPT
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullFormat
Indicates that a full format of the partition is performed.

```yaml
Type: SwitchParameter
Parameter Sets: FullFormatMBR, FullFormatGPT
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: ClusterFormatMBR, ClusterFormatGPT
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GuidPartitionTable
Indicates that the storage disk is a GUID partition table disk.

```yaml
Type: SwitchParameter
Parameter Sets: QuickFormatGPT, FullFormatGPT, ClusterFormatGPT
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: Default, QuickFormatGPT, ForceNewDiskIdGuid, ForceNewDiskIdSignature, QuickFormatMBR, FullFormatMBR, FullFormatGPT
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: ClusterFormatMBR, ClusterFormatGPT
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

### -MasterBootRecord
Indicates that the storage disk is a master boot record disk.

```yaml
Type: SwitchParameter
Parameter Sets: QuickFormatMBR, FullFormatMBR, ClusterFormatMBR
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountPoint
Specifies a mount point location.

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

### -QuickFormat
Indicates that a quick format of the partition is performed.

```yaml
Type: SwitchParameter
Parameter Sets: QuickFormatGPT, QuickFormatMBR
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: ClusterFormatMBR, ClusterFormatGPT
Aliases: 

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

### -StorageClassification
Specifies a storage classification object.

```yaml
Type: StorageClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageDisk
Specifies a disk on a Hyper-V or VMware ESX host that a virtual machine on that host can use instead of using a virtual hard disk.
This disk is referred to as a pass-through disk.
The corresponding VMware term is Raw Device Mapping (RDM).
The host disk is either a local hard disk or a logical unit on a Storage Area Network (SAN).
VMM lets the virtual machine bypass the host's file system and access the pass-through disk directly.
Hyper-V hosts support pass-through disks and conversion of a pass-through disk to a VHD.
VMware ESX hosts support pass-through disks, but not disk conversion.
Citrix XenServer hosts do not support pass-through disks.

```yaml
Type: StorageDisk
Parameter Sets: Default, QuickFormatGPT, ForceNewDiskIdGuid, ForceNewDiskIdSignature, QuickFormatMBR, FullFormatMBR, FullFormatGPT
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageLogicalUnit
Specifies a storage logical unit object.

```yaml
Type: StorageLogicalUnit
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: StorageLogicalUnit
Parameter Sets: ClusterFormatMBR, ClusterFormatGPT
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeLabel
Specifies a label for a disk volume.

```yaml
Type: String
Parameter Sets: QuickFormatGPT, QuickFormatMBR, FullFormatMBR, FullFormatGPT, ClusterFormatMBR, ClusterFormatGPT
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* This cmdlet requires a VMM storage disk object, which can be retrieved using the **Get-SCStorageDisk** cmdlet.

## RELATED LINKS

[Get-SCStorageDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageDisk.md)

[Get-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageLogicalUnit.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Register-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageLogicalUnit.md)

[Set-SCStorageDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageDisk.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

