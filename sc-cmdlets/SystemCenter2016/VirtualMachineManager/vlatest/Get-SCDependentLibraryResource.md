---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D45E1272-89DB-49AB-AA0E-0D757B681304
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCDependentLibraryResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCDependentLibraryResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCDependentLibraryResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCDependentLibraryResource

## SYNOPSIS
Identifies dependencies between VMM objects.

## SYNTAX

### LibraryResource (Default)
```
Get-SCDependentLibraryResource [-VMMServer <ServerConnection>] [-LibraryResource] <LibObjectBase>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### LibraryShare
```
Get-SCDependentLibraryResource [-VMMServer <ServerConnection>] [-LibraryShare] <LibraryShare>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### LibraryServer
```
Get-SCDependentLibraryResource [-VMMServer <ServerConnection>] [-LibraryServer] <LibraryServer>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDependentLibraryResource** cmdlet identifies dependencies between Virtual Machine Manager (VMM) objects. 

You can use the **Get-SCDependentLibraryResource** cmdlet to identify objects that are dependent on the existence of: 



- The specified library object.

- Any object on the specified library share.

- Any object on the specified library server.

## EXAMPLES

### Example 1: Find all objects that depend on a particular virtual hard disk
```
PS C:\> $VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "VHD01"  -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Get-SCDependentLibraryResource -LibraryResource $VHD
```

The first command gets the hard disk object named VHD01 on LibraryServer01 from the VMM library on VMMServer01 and stores the object in the $VHD variable.
This example assumes that only one virtual hard disk named VHD01 exists.

The second command returns all of the library objects that are dependent on VHD01.

If dependent objects exist, removing this virtual hard disk will modify those dependent objects so that they no longer reference the removed virtual hard disk.
Thus, if VHD01 is associated with a specific virtual machine or with a specific template, that virtual machine or template is modified so that it no longer references VHD01 after it is removed.

## PARAMETERS

### -LibraryResource
Specifies a resource stored in the VMM library.

```yaml
Type: LibObjectBase
Parameter Sets: LibraryResource
Aliases: LibraryObject

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: LibraryServer
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LibraryShare
Specifies a VMM library share object.

```yaml
Type: LibraryShare
Parameter Sets: LibraryShare
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### HardwareProfile
This cmdlet returns a **HardwareProfile** object.

## NOTES

## RELATED LINKS

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDisk.md)

