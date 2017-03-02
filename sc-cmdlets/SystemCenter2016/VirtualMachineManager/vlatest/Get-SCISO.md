---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D4D1D8F8-EB90-4E27-8939-BECA540BA8EB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISO.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISO.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISO.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCISO

## SYNOPSIS
Gets ISO files from the VMM library.

## SYNTAX

### All (Default)
```
Get-SCISO [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### NameParamSet
```
Get-SCISO [-VMMServer <ServerConnection>] -Name <String> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCISO [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCISO [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCISO** cmdlet gets ISO files from the Virtual Machine Manager (VMM) library.
ISO files are stored in library shares on library servers. 

In VMM, some typical uses of an ISO file include: 



- Storing an operating system ISO in the library that you can use later to install that operating system on a new or existing virtual machine deployed on a host. 


- Storing application software, such as a Microsoft Office ISO, in the library, so that you can install it later on a virtual machine deployed on a host.

## EXAMPLES

### Example 1: Get all ISOs on all VMM library servers
```
PS C:\> Get-SCISO -VMMServer "VMMServer01.Contoso.com"
```

This command gets all ISO objects on VMMServer01 and displays information about these ISOs.

The ISO files that the retrieved objects represent are stored in library shares on library servers.

### Example 2: Get all ISOs on a specific VMM library server
```
PS C:\> Get-SCISO -VMMServer "VMMServer1.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
```

This command gets all objects that represent ISO files stored on LibraryServer01 and displays information about these ISOs to the user.

### Example 3: Get all ISOs with a specific string in the file name on any VMM library server
```
PS C:\> Get-SCISO -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match  "OsISO" }
```

This command gets all ISO objects on any VMM library server managed by VMMServer01 that contain OsISO in the file name, and then displays information about these ISO objects.

Note: By default, the name of an ISO object in the library is the same name as the name of the actual ISO file stored in the file system on the library server.

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

### -FamilyName
Specifies a family name for a physical resource in the VMM library.
This value is used in conjunction with Release, Namespace, and Type to establish equivalency among library resources.

```yaml
Type: String
Parameter Sets: EquivalentResourceParamSet
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
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: NameParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -Release
Specifies a string that describes the release of a library resource.
VMM automatically creates a release value for every resource imported into the library.
After the resource has been imported, the string can be customized.

```yaml
Type: String
Parameter Sets: EquivalentResourceParamSet
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

### ISO
This cmdlet returns an **ISO** object.

## NOTES

## RELATED LINKS

[Remove-SCISO](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCISO.md)

[Set-SCISO](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCISO.md)

