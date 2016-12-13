---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMDiskStorage.md
schema: 2.0.0
ms.assetid: 8359D5D4-D9A1-4907-880A-4B232DDC82BF
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMDiskStorage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMDiskStorage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMDiskStorage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMDiskStorage

## SYNOPSIS
Retrieves list of disks and volumes on a DPM server.

## SYNTAX

### DPMDisk
```
Get-DPMDiskStorage [[-DPMServerName] <String>] [-All] [-OutputAsStorageResource] [<CommonParameters>]
```

### Volumes
```
Get-DPMDiskStorage [[-DPMServerName] <String>] [-All] [-Volumes] [-OutputAsStorageResource]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMDiskStorage** cmdlet gets the disks or volumes that can be added to the storage pool on a given System Center 2016 - Data Protection Manager (DPM) server.
A storage pool on a DPM server consists of a set of disks where the server stores replicas, shadow copies, and transfer logs for protected data sources and a set of ReFS volumes where the server stores replica VHDs.

## EXAMPLES

### Example 1: Return a list of all disks on a DPM server
```
PS C:\>Get-DPMDiskStorage -DPMServerName "TestingServer" -All
```

This command returns all disks that are locally attached to the DPM server named TestingServer.
This includes the disks with system and boot partitions.

### Example 2: Return a list of disks that are usable by DPM
```
PS C:\>Get-DPMDiskStorage -DPMServerName "TestingServer"
```

This command returns the disks that are locally attached to the DPM server named TestingServer and can be used by the DPM server.
This excludes the disks with system and boot partitions, as well as virtual disks

### Example 3: Return a list of all volumes on a DPM server
```
PS C:\>Get-DPMDiskStorage -DPMServerName "TestingServer" -Volumes -All
```

This command returns all the basic volumes that are present on the DPM server named TestingServer.
This excludes the system and reserved volumes, as well as dynamic volumes.

### Example 4: Return a list of volumes in the DPM storage pool
```
PS C:\>Get-DPMDiskStorage -DPMServerName "TestingServer" -Volumes
```

This command returns the volumes that are added to storage pool on the DPM server named TestingServer.

## PARAMETERS

### -All
Indicates that cmdlet will return all local disks or volumes and not filter out any disk or volume that is not in DPM storage pool.
If this switch is not specified, the cmdlet will either return the disks that can be added to storage pool, or the volumes that are already added to storage pool based on the *Volumes* switch.

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

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets disks or volumes.

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

### -OutputAsStorageResource
Indicates that the output should be of type **StorageResource** class instead of **Disk** or **VolumeStorage** class.
This switch parameter is used by the DPM UI.

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

### -Volumes
Indicates that the cmdlet retrieves only volumes.
If this switch is not specified, the cmdlet will retrieve only disks.

```yaml
Type: SwitchParameter
Parameter Sets: Volumes
Aliases: 

Required: True
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

## RELATED LINKS

[Add-DPMDiskStorage](xref:DataProtectionManager/v1/Add-DPMDiskStorage.md)

[Remove-DPMDiskStorage](xref:DataProtectionManager/v1/Remove-DPMDiskStorage.md)

[Update-DPMDiskStorage](xref:DataProtectionManager/v1/Update-DPMDiskStorage.md)

