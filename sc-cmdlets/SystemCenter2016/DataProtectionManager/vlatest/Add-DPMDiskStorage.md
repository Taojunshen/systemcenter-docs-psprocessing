---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E22743DB-600A-4AAF-AFEB-8B8D15675D56
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMDiskStorage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMDiskStorage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMDiskStorage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-DPMDiskStorage

## SYNOPSIS
Adds a specified disk to the storage pool on a DPM server.

## SYNTAX

### DPMDisk
```
Add-DPMDiskStorage [-DPMDisk] <Disk[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Volumes
```
Add-DPMDiskStorage [-Volumes] <Volume[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Volume
```
Add-DPMDiskStorage [-Volume] <Volume> [[-Subdirectory] <String>] [[-FriendlyName] <String>]
 [[-DatasourceType] <VolumeTag[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMDiskStorage** cmdlet adds a disk or a volume to the storage pool on a System Center 2016 - Data Protection Manager (DPM) server.
A storage pool on a DPM server consists of a set of disks where the server stores replicas, shadow copies, and transfer logs for protected data sources and a set of Resilient File System (ReFS) volumes in which the server stores replica virtual hard disks (VHDs).

To get a list of all disks on a DPM server, use the [Get-DPMDiskStorage](./Get-DPMDiskStorage.md) cmdlet.
To get a list of all volumes on a DPM server, use the **Get-DPMDiskStorage** cmdlet with the *-All* and *-Volumes* parameters specified.

## EXAMPLES

### Example 1: Add disk to DPM storage pool
```
PS C:\>$disks = Get-DPMDiskStorage -DPMServerName "TestingServer"
PS C:\> Add-DPMDiskStorage -DPMDisk $disks
```

The first command uses **Get-DPMDiskStorage** to get a list of disks attached to the DPM server named TestingServer and stores the list in the $disks variable.

### Example 2: Add volumes to DPM storage pool
```
PS C:\>$volumes = Get-DPMDiskStorage -DPMServerName "TestingServer" -Volumes -All
PS C:\> Add-DPMDiskStorage -Volumes $volumes
```

The first command uses the **Get-DPMDiskStorage** cmdlet to get a list of volumes available in the DPM server named TestingServer.
It stores them in the $volumes variable.

The second command adds all volumes in $volumes to the DPM storage pool.

## PARAMETERS

### -DatasourceType
Specifies an array of data source types that can be backed up on this disk storage.
The data source type list can be any combination of the following values: 

- FileSystem
- Client
- SQL
- SharePoint
- Exchange
- SystemProtection
- HyperV
- VMware
- Other
- All

```yaml
Type: VolumeTag[]
Parameter Sets: Volume
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMDisk
Specifies an array of disks that this cmdlet adds to the DPM storage pool.

```yaml
Type: Disk[]
Parameter Sets: DPMDisk
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FriendlyName
Specifies a friendly name for the volume that this cmdlet adds to the DPM storage pool.

```yaml
Type: String
Parameter Sets: Volume
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subdirectory
Specifies an empty directory inside the volume that this cmdlet adds to the DPM storage pool.
The subdirectory cannot be updated after the volume is added to the DPM storage pool.

```yaml
Type: String
Parameter Sets: Volume
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies a volume to be added to a DPM storage pool.
If the *Subdirectory* parameter is not specified, DPM formats the volume with the ReFS 3.0 file system before adding it to storage pool.
If the *Subdirectory* parameter is specified, the specified volume must be a ReFS 3.0 volume.
In that case, DPM does not format the volume and only uses the subdirectory to store backup data.

```yaml
Type: Volume
Parameter Sets: Volume
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volumes
Specifies an array of volumes to be added to the DPM storage pool.
DPM formats each of these volumes with the ReFS 3.0 file system before adding them to the storage pool.

```yaml
Type: Volume[]
Parameter Sets: Volumes
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

[Get-DPMDiskStorage](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDiskStorage.md)
