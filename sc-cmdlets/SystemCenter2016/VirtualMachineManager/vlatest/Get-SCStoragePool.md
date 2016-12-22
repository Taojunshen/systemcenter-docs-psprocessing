---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 02900393-D9B0-43AB-888C-FEFCEA97750E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStoragePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStoragePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStoragePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStoragePool

## SYNOPSIS
Gets a storage pool object from the VMM database.

## SYNTAX

### All (Default)
```
Get-SCStoragePool [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCStoragePool [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStoragePool** cmdlet gets one or more storage pool objects from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Get a storage pool by its name
```
PS C:\> Get-SCStoragePool -Name "StoragePool01"
```

This command gets the storage pool named StoragePool01.

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
Specifies the name of a VMM object.

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

### StoragePool
This cmdlet returns a **StoragePool** object.

## NOTES

## RELATED LINKS

[New-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStoragePool.md)

[Remove-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStoragePool.md)

[Set-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStoragePool.md)

