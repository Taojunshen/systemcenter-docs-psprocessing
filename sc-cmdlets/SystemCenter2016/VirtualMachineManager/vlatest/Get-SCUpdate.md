---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F806CDB0-A1B4-4E5C-9AE6-7341E60FEB88
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCUpdate

## SYNOPSIS
Gets one or more updates.

## SYNTAX

### ID (Default)
```
Get-SCUpdate [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

### Name
```
Get-SCUpdate [-VMMServer <ServerConnection>] [-Name <String>] [<CommonParameters>]
```

### KBArticle
```
Get-SCUpdate [-VMMServer <ServerConnection>] [-KBArticle <String>] [<CommonParameters>]
```

### BulletinId
```
Get-SCUpdate [-VMMServer <ServerConnection>] [-SecurityBulletinId <String>] [<CommonParameters>]
```

### Newest
```
Get-SCUpdate [-VMMServer <ServerConnection>] [-Newest <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCUpdate** cmdlet gets one or more updates.
An update contains metadata that enables the ability to determine the applicability and installation status of an update that is assigned to a target computer using a baseline.

## EXAMPLES

### Example 1: Get a specific update by its bulletin identification number
```
PS C:\> Get-SCUpdate -SecurityBulletinID "MS05-051"
```

This command gets the security bulletin update named MS05-51.

### Example 2: Get a specific update by its KB article number
```
PS C:\> Get-SCUpdate -KBArticle "93051"
```

This command gets the updated identified by KBArticle 93051.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KBArticle
Specifies the KB article ID number for an update.

```yaml
Type: String
Parameter Sets: KBArticle
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Newest
Returns all jobs created in the last specified number of hours, or returns the specified number of most recent software updates.

Example format to return the 10 newest updates: `Get-SCUpdate -Newest 10`

```yaml
Type: Int32
Parameter Sets: Newest
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityBulletinId
Specifies the Microsoft Security Response Center (MSRC) Security Bulletin ID for an update.

Example format: `-SecurityBulletinId "MS05-045"`

```yaml
Type: String
Parameter Sets: BulletinId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Update
This cmdlet returns an **Update** object.

## NOTES

## RELATED LINKS

[Set-SCUpdate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdate.md)

