---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F4CEF963-8930-4B7D-8488-87D8C70C13D0
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCDriverPackage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCDriverPackage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCDriverPackage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCDriverPackage

## SYNOPSIS
Gets a driver package stored in a VMM library share.

## SYNTAX

### Connection (Default)
```
Get-SCDriverPackage [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### PNPIdMatching
```
Get-SCDriverPackage [-VMMServer <ServerConnection>]
 [[-PnPID] <System.Collections.Generic.List`1[System.String]>] [<CommonParameters>]
```

### TagMatching
```
Get-SCDriverPackage [-VMMServer <ServerConnection>] [[-Tag] <System.Collections.Generic.List`1[System.String]>]
 [<CommonParameters>]
```

### All
```
Get-SCDriverPackage [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCDriverPackage [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDriverPackage** cmdlet gets one or more driver packages stored in a Virtual Machine Manager (VMM) library share.

## EXAMPLES

### Example 1: Get all driver packages stored in the VMM library
```
PS C:\> Get-SCDriverPackage
```

This command gets all driver packages stored in the VMM library and displays information about each driver package to the user.

### Example 2: Get a driver package by its Plug and Play ID
```
PS C:\> Get-SCDriverPackage -PnPID "ROOT\VMBUS"
```

This command gets the driver package that has a Plug and Play ID (PnPID) of "ROOT\VMBUS".

### Example 3: Get all driver packages with a specified tag value
```
PS C:\> Get-SCDriverPackage -Tag "Production"
```

This command gets all driver packages that have a tag value of Production.

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

### -PnPID
Specifies the plug and play (PnP) ID that the driver package supports.
You can use this parameter to query for driver packages with matching PnP ID values.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: PNPIdMatching
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: TagMatching
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

### DriverPackage[]
This cmdlet returns an array of **DriverPackage** objects.

## NOTES

## RELATED LINKS

[Remove-SCDriverPackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCDriverPackage.md)

[Set-SCDriverPackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCDriverPackage.md)

