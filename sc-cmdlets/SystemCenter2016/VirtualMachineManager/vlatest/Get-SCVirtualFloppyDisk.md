---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 584E546A-2812-4CD9-ADDB-86714241D676
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualFloppyDisk

## SYNOPSIS
Gets virtual floppy disk objects from the VMM library.

## SYNTAX

### All (Default)
```
Get-SCVirtualFloppyDisk [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParamSet
```
Get-SCVirtualFloppyDisk [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCVirtualFloppyDisk [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String>
 [<CommonParameters>]
```

### ID
```
Get-SCVirtualFloppyDisk [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualFloppyDisk** cmdlet gets one or more virtual floppy disk objects from the Virtual Machine Manager (VMM) library.
The virtual floppy disk file (either a Windows-based .vfd file or a VMware-based .flp file) that a virtual floppy disk object represents is stored on a library server.

## EXAMPLES

### Example 1: Get all virtual floppy disks on all VMM library servers
```
PS C:\> Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com"
```

This command gets all virtual floppy disk objects VMM library on VMMServer01 and then displays information about these virtual floppy disk objects to the user.
The virtual floppy disk files themselves are stored in library shares on library servers.

### Example 2: Get all virtual floppy disks on a specific VMM library server
```
PS C:\> Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
```

This command gets all virtual floppy disk objects stored on LibraryServer01 and displays information about these virtual floppy disk objects to the user.

### Example 3: Get all virtual floppy disks with a specific name on any VMM library server
```
PS C:\> Get-SCVirtualFloppyDisk | where { $_.Name -eq "BootFloppy.vfd" }
```

This command gets all virtual floppy disk objects named BootFloppy.vfd that are stored on any library server managed by VMM, and then displays information about these virtual floppy disk objects to the user.

Note: By default, the name of a virtual floppy disk object in the library is the same name (including the extension) as the name of the actual virtual floppy disk file on the library server.

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

### VirtualFloppyDisk
This cmdlet returns a **VirtualFloppyDisk** object.

## NOTES

## RELATED LINKS

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

[Remove-SCVirtualFloppyDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualFloppyDisk.md)

[Set-SCVirtualFloppyDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDisk.md)

