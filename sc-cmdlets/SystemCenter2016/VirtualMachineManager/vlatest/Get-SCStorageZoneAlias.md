---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6AF67E89-9748-4D42-9B86-AFA68B1CF572
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZoneAlias.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZoneAlias.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZoneAlias.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageZoneAlias

## SYNOPSIS
Gets a Fibre Channel zone alias.

## SYNTAX

### All (Default)
```
Get-SCStorageZoneAlias [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCStorageZoneAlias [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageZoneAlias** cmdlet gets a Fibre Channel zone alias.

## EXAMPLES

### Example 1: Get a storage zone alias by name
```
PS C:\> Get-SCStorageZoneAlias -Name "Alias01"
```

This command gets the storage zone alias named Alias01.

## PARAMETERS

### -All
Indicates that this cmdlet retrieves a full list of all subordinate Fibre Channel zone aliases independent of the parent object with which they are associated.

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
Specifies the unique ID for a Fibre Channel zone.

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
Specifies the name the Fibre Channel zone alias.

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
Specifies a Virtual Machine Manager (VMM) server object.

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

### StorageZoneAlias
This cmdlet returns a **StorageZoneAlias** object.

## NOTES

## RELATED LINKS

[New-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageZoneAlias.md)

[Remove-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageZoneAlias.md)

[Set-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageZoneAlias.md)

