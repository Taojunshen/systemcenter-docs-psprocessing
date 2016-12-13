---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: 63A21708-4A3A-45CB-BAE6-3AEF47BCB71C
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualHardDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualHardDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualHardDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualHardDisk

## SYNOPSIS
Gets virtual hard disk objects from a virtual machine, from a template, or as a standalone file stored in the VMM library.

## SYNTAX

### All (Default)
```
Get-SCVirtualHardDisk [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
Get-SCVirtualHardDisk [-VMMServer <ServerConnection>] -VMTemplate <Template> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VM
```
Get-SCVirtualHardDisk [-VMMServer <ServerConnection>] -VM <VM> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NameParamSet
```
Get-SCVirtualHardDisk [-VMMServer <ServerConnection>] -Name <String> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCVirtualHardDisk [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVirtualHardDisk [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualHardDisk** cmdlet gets virtual hard disk objects from a virtual machine, from a template, or as a standalone file stored in the Virtual Machine Manager (VMM) library.

A virtual hard disk can be a Windows-based .vhd file, a Citrix XenServer-based .vhd file, or a VMware-based.vmdk file.
A virtual hard disk might be stored as a standalone object in the VMM library, attached to a virtual disk drive on a template, or attached to a virtual disk drive on a deployed or stored virtual machine.

## EXAMPLES

### Example 1: Get a virtual hard disk object from the library
```
PS C:\>$VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "VHD01.vhd" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
```

This command gets the virtual hard disk object named VHD01.vhd stored on LibraryServer01 and then stores the object in the $VHD variable.

### Example 2: Get a virtual hard disk object from a virtual machine
```
PS C:\>Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> $VHD = Get-SCVirtualMachine -Name "VM01" | Get-SCVirtualHardDisk | where { $_.Name -match "DataDisk" }
```

The first command connects to VMMServer01.

The second command gets the virtual machine object named VM01, selects all virtual hard disks on VM01 whose name includes the string "DataDisk," and then stores the returned virtual hard disk objects in the $VHD variable.

### Example 3: Get a virtual hard disk object from a specific template
```
PS C:\>Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "Template01"} | Get-SCVirtualHardDisk
```

This command gets the template object named Template01 from the library and displays all virtual hard disk objects on that template.

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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualHardDisk
This cmdlet returns a **VirtualHardDisk** object.

## NOTES
* Requires a VMM virtual machine object or a VMM template object, which can be retrieved by using the Get-SCVirtualMachine cmdlet, or the Get-SCVMTemplate cmdlet, respectively.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Compress-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:VirtualMachineManager/v1/Get-SCVMTemplate.md)

[Remove-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Remove-SCVirtualHardDisk.md)

[Set-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Set-SCVirtualDiskDrive.md)

[Set-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Set-SCVirtualHardDisk.md)

