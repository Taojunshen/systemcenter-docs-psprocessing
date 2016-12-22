---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9D0372C6-27B4-4D90-AD72-99D060EF2E1C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageProvider

## SYNOPSIS
Gets a storage provider object.

## SYNTAX

### All (Default)
```
Get-SCStorageProvider [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCStorageProvider [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageProvider** cmdlet gets one or more storage provider objects.

## EXAMPLES

### Example 1: Get a storage provider by its name
```
PS C:\> $Provider = Get-SCStorageProvider -Name "StorProv01.Contoso.com"
```

This command gets the storage provider named StorProv01 and stores it in the $Provider variable.

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

### StorageProvider
This cmdlet returns a **StorageProvider** object.

## NOTES

## RELATED LINKS

[Add-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCStorageProvider.md)

[Import-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Import-SCStorageProvider.md)

[Read-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCStorageProvider.md)

[Remove-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageProvider.md)

[Set-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageProvider.md)

