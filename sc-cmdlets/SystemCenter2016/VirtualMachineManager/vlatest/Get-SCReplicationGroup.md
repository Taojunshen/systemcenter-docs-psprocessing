---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CC9E877F-1525-4884-A4D8-F13348186C55
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCReplicationGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCReplicationGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCReplicationGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCReplicationGroup

## SYNOPSIS
Gets a replication group.

## SYNTAX

### All (Default)
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### GetByStorageArray
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>] -StorageArray <StorageArray>
 [<CommonParameters>]
```

### GetByHostGroup
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>] -HostGroup <HostGroup>
 [<CommonParameters>]
```

### GetByStorageLogicalUnit
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>]
 -StorageLogicalUnit <StorageLogicalUnit> [<CommonParameters>]
```

### GetByCloud
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>] -Cloud <Cloud> [<CommonParameters>]
```

### GetByStorageFileShare
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>] -StorageFileShare <StorageFileShare>
 [<CommonParameters>]
```

### ID
```
Get-SCReplicationGroup [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCReplicationGroup** cmdlet gets a replication group.

## EXAMPLES


## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: GetByCloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostGroup
Specifies a host group object.

```yaml
Type: HostGroup
Parameter Sets: GetByHostGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageArray
Specifies a storage array object.

```yaml
Type: StorageArray
Parameter Sets: GetByStorageArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFileShare


```yaml
Type: StorageFileShare
Parameter Sets: GetByStorageFileShare
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageLogicalUnit
Specifies a storage logical unit object.

```yaml
Type: StorageLogicalUnit
Parameter Sets: GetByStorageLogicalUnit
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

[New-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCReplicationGroup.md)

[Remove-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCReplicationGroup.md)

[Set-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCReplicationGroup.md)

