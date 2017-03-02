---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DDA91FA5-8588-4E45-AEE3-D837E4A2DB85
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCStorageFileShare

## SYNOPSIS
Creates a storage file share in VMM.

## SYNTAX

### NewShareOnWindowsServer
```
New-SCStorageFileShare [-VMMServer <ServerConnection>] -StorageFileServer <StorageFileServer> -Name <String>
 [-Description <String>] -LocalPath <String> [-ContinuouslyAvailable <Boolean>]
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### NewShareOnNASFromPool
```
New-SCStorageFileShare [-VMMServer <ServerConnection>] -StorageFileServer <StorageFileServer> -Name <String>
 [-Description <String>] -StoragePool <StoragePool> [-FileSystem <String>] [-ResiliencySettingName <String>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-DedupMode <DedupMode>]
 [-AllocationUnitSizeKB <UInt32>] -SizeMB <UInt64> [-StorageClassification <StorageClassification>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewShareFromPoolTiered
```
New-SCStorageFileShare [-VMMServer <ServerConnection>] -StorageFileServer <StorageFileServer> -Name <String>
 [-Description <String>] -StoragePool <StoragePool> [-FileSystem <String>] [-DedupMode <DedupMode>]
 [-AllocationUnitSizeKB <UInt32>] [-StorageClassification <StorageClassification>] [-ReadCacheSizeMB <UInt64>]
 -JobGroup <Guid> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewShareFromTieredPool
```
New-SCStorageFileShare [-VMMServer <ServerConnection>] -StorageFileServer <StorageFileServer> -Name <String>
 [-Description <String>] -StoragePool <StoragePool> [-FileSystem <String>] [-ResiliencySettingName <String>]
 [-NumberOfColumns <UInt16>] [-PhysicalDiskRedundancy <UInt16>] [-DedupMode <DedupMode>]
 [-AllocationUnitSizeKB <UInt32>] [-StorageClassification <StorageClassification>]
 -MediaType <StoragePhysicalDiskMediaType[]> -StorageTierSizeMB <UInt64[]> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewShareFromStorageVolume
```
New-SCStorageFileShare [-VMMServer <ServerConnection>] -StorageFileServer <StorageFileServer> -Name <String>
 [-Description <String>] -StorageVolume <StorageVolume> [-StorageClassification <StorageClassification>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewShareOnNASFromHostedPool
```
New-SCStorageFileShare [-VMMServer <ServerConnection>] -StorageFileServer <StorageFileServer> -Name <String>
 [-Description <String>] -HostedStoragePool <String> -SizeMB <UInt64>
 [-StorageClassification <StorageClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageFileShare** cmdlet creates a storage file share in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Create a storage file share
```
PS C:\> $FileServer = Get-SCStorageFileServer -Name "FileServer01.Contoso.com"
PS C:\> New-SCStorageFileShare -Name "FileShare02" -StorageFileServer $FileServer -LocalPath "C:\FileShare02"
```

The first command gets the storage file server object named FileServer01 and stores the object in the $FileServer variable.

The second command creates a storage file share named FileShare02 on FileServer01.

### Example 2: Create a tiered storage file share on a shared SOFS
```
PS C:\> $FileServer = Get-SCStorageFileServer -Name "FileServer01.Contoso.com"
PS C:\> $StoragePool = Get-SCStoragePool -Name "Pool01"
PS C:\> New-SCStorageTier -MediaType "SSD" -SizeMB 1024  -PhysicalDiskRedundancy "2" -ResiliencySettingName "Mirror" -RunAsynchronously -JobGroup "2e42beba-fb19-4c15-94e6-64a54012dce3"
PS C:\> New-SCStorageTier -MediaType "HDD" -SizeMB 1024  -PhysicalDiskRedundancy "2" -ResiliencySettingName "Parity" -RunAsynchronously -JobGroup "2e42beba-fb19-4c15-94e6-64a54012dce3"
PS C:\> $StorageClassification = Get-SCStorageClassification -Name "Gold"
PS C:\> $StorageFileShare = New-SCStorageFileShare -StorageFileServer $FileServer -StoragePool $StoragePool -Name "FileShare01" -Description "shared SOSF" -RunAsynchronously -JobGroup "2e42beba-fb19-4c15-94e664a54012dce3" -FileSystem "CSVFS_ReFS" -StorageClassification $StorageClassification
```

The first command gets the storage file server object named FileServer01, and then stores it in the $FileServer variable.

The second command gets the storage pool named Pool01, and then stores it in the $StoragePool variable.

The third and fourth commands create storage tiers.

The fifth command gets the storage classification named Gold, and then stores it in the $StorageClassification variable.

The last command creates tiered file share named FileShare01.
The command uses values created in previous commands.

### Example 3: Create a tiered storage file share on an S2D system
```
PS C:\> $FileServer = Get-SCStorageFileServer -Name "FileServer01.Contoso.com"
PS C:\> $StoragePool = Get-SCStoragePool -Name "S2DPool01"
PS C:\> New-SCStorageTier -StorageTierFriendlyName "Performance" -StorageTierSizeInMB 1024 -RunAsynchronously -JobGroup "2e42beba-fb19-4c15-94e6-64a54012dce3"
PS C:\> New-SCStorageTier -StorageTierFriendlyName "Capacity" -StorageTierSizeInMB 1024 -RunAsynchronously -JobGroup "2e42beba-fb19-4c15-94e6-64a54012dce3"
PS C:\> $StorageClassification = Get-SCStorageClassification -Name "Gold"
PS C:\> $StorageFileShare = New-SCStorageFileShare -StorageFileServer $FileServer -StoragePool $StoragePool -Name "FileShare01" -Description "storage spaces direct config" -RunAsynchronously -JobGroup "2e42beba-fb19-4c15-94e664a54012dce3" -FileSystem "CSVFS_ReFS" -StorageClassification $StorageClassification"
```

The first command gets the storage file server object named FileServer01, and then stores it in the $FileServer variable.

The second command gets the storage pool named S2DPool01, and then stores it in the $StoragePool variable.
This is a storage spaces direct pool.

The third and fourth commands create storage tiers.

The fifth command gets the storage classification named Gold, and then stores it in the $StorageClassification variable.

The last command creates tiered file share named FileShare01.
The command uses values created in previous commands.

## PARAMETERS

### -AllocationUnitSizeKB
Specifies the allocation size of a volume, in kilobytes.

```yaml
Type: UInt32
Parameter Sets: NewShareOnNASFromPool, NewShareFromPoolTiered, NewShareFromTieredPool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContinuouslyAvailable
Indicates whether the file share is available on a continuous basis.

```yaml
Type: Boolean
Parameter Sets: NewShareOnWindowsServer
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
Parameter Sets: NewShareOnNASFromPool, NewShareFromPoolTiered, NewShareFromTieredPool
Aliases: 
Accepted values: Disabled, GeneralPurpose, HyperV, Backup, NotAvailable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage file share.

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

### -FileSystem
Specifies the file system of a storage volume.
The acceptable values for this parameter are:

- CSVFS_NTFS
- CSVFS_ReFS

```yaml
Type: String
Parameter Sets: NewShareOnNASFromPool, NewShareFromPoolTiered, NewShareFromTieredPool
Aliases: 
Accepted values: CSVFS_NTFS, CSVFS_ReFS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostedStoragePool
Specifies a hosted storage pool.

```yaml
Type: String
Parameter Sets: NewShareOnNASFromHostedPool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: NewShareFromPoolTiered
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -LocalPath
Specifies a local path for a storage file share.

```yaml
Type: String
Parameter Sets: NewShareOnWindowsServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaType
Specifies an array of storage physical disk media type objects.

```yaml
Type: StoragePhysicalDiskMediaType[]
Parameter Sets: NewShareFromTieredPool
Aliases: 
Accepted values: Unknown, HDD, SSD

Required: True
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
Parameter Sets: NewShareOnNASFromPool, NewShareFromTieredPool
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
Parameter Sets: NewShareOnNASFromPool, NewShareFromTieredPool
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadCacheSizeMB


```yaml
Type: UInt64
Parameter Sets: NewShareFromPoolTiered
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

- Simple
- Mirror
- Parity

```yaml
Type: String
Parameter Sets: NewShareOnNASFromPool, NewShareFromTieredPool
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

### -SizeMB
Specifies the size, in megabytes, of a storage file share.

```yaml
Type: UInt64
Parameter Sets: NewShareOnNASFromPool, NewShareOnNASFromHostedPool
Aliases: 

Required: True
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

### -StorageFileServer
Specifies a storage file server object.

```yaml
Type: StorageFileServer
Parameter Sets: (All)
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
Parameter Sets: NewShareOnNASFromPool, NewShareFromPoolTiered, NewShareFromTieredPool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierSizeMB
Specifies, in MB, the storage tier size.

```yaml
Type: UInt64[]
Parameter Sets: NewShareFromTieredPool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageVolume
Specifies a storage volume object on a specific virtual machine host.

```yaml
Type: StorageVolume
Parameter Sets: NewShareFromStorageVolume
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

[Get-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileShare.md)

[Register-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageFileShare.md)

[Remove-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFileShare.md)

[Repair-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCStorageFileShare.md)

[Set-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileShare.md)

[Unregister-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageFileShare.md)

