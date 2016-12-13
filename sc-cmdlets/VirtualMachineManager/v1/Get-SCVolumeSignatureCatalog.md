---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 5d1397ab-f265-4bf5-8445-77d60fb220da
schema: 2.0.0
ms.assetid: 8C5FD598-61CA-41CF-B8D4-45C162133179
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVolumeSignatureCatalog.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVolumeSignatureCatalog.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVolumeSignatureCatalog.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVolumeSignatureCatalog

## SYNOPSIS
Gets the volume signature catalog information from a template disk.

## SYNTAX

### CatalogByDiskId (Default)
```
Get-SCVolumeSignatureCatalog [-VMMServer <ServerConnection>] [-VirtualHardDiskId] <Guid>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### CatalogByDisk
```
Get-SCVolumeSignatureCatalog [-VMMServer <ServerConnection>] [-VirtualHardDisk] <VirtualHardDisk>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVolumeSignatureCatalog** cmdlet gets the volume signature catalog information from a template disk.
The information includes the certificate used to sign the disk, the name, and the version of the disk.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
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

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: VirtualHardDisk
Parameter Sets: CatalogByDisk
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHardDiskId
Specifies the ID of a virtual hard disk.

```yaml
Type: Guid
Parameter Sets: CatalogByDiskId
Aliases: 

Required: True
Position: 0
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

