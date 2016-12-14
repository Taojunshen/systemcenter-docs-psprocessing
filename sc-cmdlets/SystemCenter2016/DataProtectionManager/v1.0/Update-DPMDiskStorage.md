---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMDiskStorage.md
schema: 2.0.0
ms.assetid: D6B4B3CD-1E6A-4303-8065-79F7274FA8C7
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Update-DPMDiskStorage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Update-DPMDiskStorage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Update-DPMDiskStorage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-DPMDiskStorage

## SYNOPSIS
Updates properties of a volume in the storage pool on a DPM server.

## SYNTAX

```
Update-DPMDiskStorage [-Volume] <Volume> [[-FriendlyName] <String>] [[-DatasourceType] <VolumeTag[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-DPMDiskStorage** cmdlet updates properties of a volume in the storage pool on a System Center 2016 - Data Protection Manager (DPM) server.
The cmdlet can be used to update the friendly name and allowed data source types.

To get a list of all volumes in the DPM storage pool, use the Get-DPMDiskStorage cmdlet with the *Volumes* switch.

## EXAMPLES

### Example 1: Update volume properties of a volume in DPM storage pool
```
PS C:\>$volumes = Get-DPMDiskStorage -DPMServerName "TestingServer" -Volumes 
PS C:\> Update-DPMDiskStorage -Volume $volumes[0] -FriendlyName "New Volume" -DatasourceType FileSystem
```

The first command uses the **Get-DPMDiskStorage** cmdlet to get the volumes already added to the storage pool of the DPM server named TestingServer.
It stores them in the $volumes variable.

The second command updates the friendly name and allowed data source types for the first volume listed in the $volumes variable.

## PARAMETERS

### -DatasourceType
Specifies list of data source types that can be backed up on the current volume. 
The acceptable values for this parameter are:

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the new friendly name for the current volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies the volume for which properties need to be changed.

```yaml
Type: Volume
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

## NOTES

## RELATED LINKS

[Get-DPMDiskStorage](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMDiskStorage.md)

