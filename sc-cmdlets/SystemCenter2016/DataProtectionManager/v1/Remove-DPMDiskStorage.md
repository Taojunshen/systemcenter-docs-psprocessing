---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMDiskStorage.md
schema: 2.0.0
ms.assetid: A98161A1-D7A7-4E43-94D4-5AB3A82B6E41
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Remove-DPMDiskStorage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Remove-DPMDiskStorage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Remove-DPMDiskStorage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-DPMDiskStorage

## SYNOPSIS
Removes disk-based storage from the storage pool on a DPM server.

## SYNTAX

### DPMDisk
```
Remove-DPMDiskStorage [-DPMDisk] <Disk[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Volumes
```
Remove-DPMDiskStorage [-Volume] <Volume[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMDiskStorage** cmdlet removes given disk or volume from the storage pool of a given System Center 2016 - Data Protection Manager (DPM) server.
A storage pool on a DPM server consists of a set of disks where the server stores replicas, shadow copies, and transfer logs for protected data sources and a set of ReFS volumes where the server stores replica VHDs.

To get a list of all disks in the DPM storage pool, use the Get-DPMDiskStorage cmdlet.
To get a list of all volumes in the DPM storage pool, use the **Get-DPMDiskStorage** cmdlet with the *Volume* switch.

## EXAMPLES

### Example 1: Remove a disk from a storage pool
```
PS C:\>$disks = Get-DPMDiskStorage -DPMServerName "TestingServer"
PS C:\> Remove-DPMDiskStorage -DPMDisk $disks[0]
```

First command uses the **Get-DPMDiskStorage** cmdlet to get the disks that are locally attached to the DPM server named TestingServer.
It stores them in the $disks variable.

Second command removes first disk listed in $disks from the DPM storage pool, assuming that this disk was already added to the storage pool.

### Example 2: Remove a volume from a storage pool
```
PS C:\>$volumes = Get-DPMDiskStorage -DPMServerName "TestingServer" -Volumes 
PS C:\> Remove-DPMDiskStorage -Volume $volumes
```

First command uses the **Get-DPMDiskStorage** cmdlet to get the volumes already added to storage pool of the DPM server named TestingServer.
It stores them in the $volumes variable.

The second command removes these volumes from the DPM storage pool.

## PARAMETERS

### -DPMDisk
Specifies an array of disks that this cmdlet removes from the storage pool.

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

### -Volume
Specifies an array of volumes that this cmdlet removes from disk storage pool.

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

[Add-DPMDiskStorage](xref:SystemCenter2016/DataProtectionManager/v1/Add-DPMDiskStorage.md)

[Get-DPMDiskStorage](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMDiskStorage.md)

[Remove-DPMDiskStorage](xref:SystemCenter2016/DataProtectionManager/v1/Remove-DPMDiskStorage.md)

[Update-DPMDiskStorage](xref:SystemCenter2016/DataProtectionManager/v1/Update-DPMDiskStorage.md)

