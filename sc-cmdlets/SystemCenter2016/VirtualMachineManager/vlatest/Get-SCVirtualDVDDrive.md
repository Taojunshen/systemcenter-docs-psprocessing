---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 86AE7E9B-4813-4178-95FE-DC075FF8E195
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDVDDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDVDDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDVDDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualDVDDrive

## SYNOPSIS
Gets a VMM virtual DVD drive object from a virtual machine, a virtual machine template, or a hardware profile.

## SYNTAX

### All
```
Get-SCVirtualDVDDrive [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HardwareProfile
```
Get-SCVirtualDVDDrive [-VMMServer <ServerConnection>] -HardwareProfile <HardwareProfile>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VM
```
Get-SCVirtualDVDDrive [-VMMServer <ServerConnection>] -VM <VM> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
Get-SCVirtualDVDDrive [-VMMServer <ServerConnection>] -VMTemplate <Template> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVirtualDVDDrive [-VMMServer <ServerConnection>] [-ID] <Guid> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualDVDDrive** cmdlet gets one or more Virtual Machine Manager (VMM) virtual DVD drive objects from a virtual machine object, a virtual machine template object, or a hardware profile object.

## EXAMPLES

### Example 1: Get virtual DVD drives from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Get-SCVirtualDVDDrive -VM $VM
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets all DVD drive objects on VM01 and displays information about these virtual DVD drives to the user.

### Example 2: Get virtual DVD drives from a template
```
PS C:\> $VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> Get-SCVirtualDVDDrive -Template $VMTemplate
```

The first command gets all virtual machine template objects stored in the VMM library, selects the template object named VMTemplate01, and then stores the object in the $Template variable.

The second command gets all virtual DVD drive objects on VMTemplate01 and displays information about these virtual DVD drives to the user.

### Example 3: Get virtual DVD drives from a hardware profile
```
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> Get-SCVirtualDVDDrive -HardwareProfile $HWProfile
```

The first command gets all hardware profile objects in the VMM library, selects the profile object named NewHWProfile01, and then stores the object in the $HWProfile variable.

The second command gets all virtual DVD drive objects on NewHHWProfile01 and displays information about these virtual DVD drives to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
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

### VirtualDVDDrive
This cmdlet returns a **VirtualDVDDrive** object.

## NOTES
* Requires a VMM virtual machine object, virtual machine template object, or hardware profile object. You can retrieve these objects by using the **Get-SCVirtualMachine**, **Get-SCVMTemplate**, or **Get-SCHardwareProfile** cmdlets, respectively.

## RELATED LINKS

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHardwareProfile.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[New-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDVDDrive.md)

[Remove-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDVDDrive.md)

[Set-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md)

