---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: 5C4CFF68-6807-41D5-B5F9-D84D732D1DC1
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualDiskDrive

## SYNOPSIS
Gets virtual disk drives on a virtual machine template or on a virtual machine.

## SYNTAX

### All
```
Get-SCVirtualDiskDrive [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VM
```
Get-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VM <VM> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
Get-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VMTemplate <Template> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVirtualDiskDrive [-VMMServer <ServerConnection>] [-ID] <Guid> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualDiskDrive** cmdlet gets Virtual Machine Manager (VMM) virtual disk drive objects.
These virtual disk drives can be configured on virtual machine templates stored in the library, or on virtual machines either deployed on a host or stored in the library.

## EXAMPLES

### Example 1: Get all virtual disk drives in your VMM environment
```
PS C:\>Get-SCVirtualDiskDrive -VMMServer "VMMServer01.Contoso.com" -All
```

This command gets all virtual disk drives bound to all virtual machines registered to VMM on VMMServer01.
The command displays information about each virtual disk drive.

### Example 2: Get virtual disk drives for a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | Where-Object {$_.Name -Eq "VM02"} 
PS C:\> $VirtDiskDrive = Get-SCVirtualDiskDrive -VM $VM
PS C:\> $VirtDiskDrive
```

The first command gets the virtual machine object named VM02 by using the Get-SCVirtualMachine cmdlet.
The command stores that object in the $VM variable.

The second command gets all virtual disk drive objects on VM02, and stores those objects in $VirtDiskDrive.
If, as this example assumes, a virtual machine contains multiple virtual disk drives, each virtual disk drive has connected to it either a virtual hard disk or a pass-through disk.

The last command displays the properties of each virtual disk drive on VM02.
This information includes the name of any virtual hard disks and the path of the physical drive on the host for any pass-through disks.

### Example 3: Count virtual disk drives, except pass-through disks
```
PS C:\>$VirtDiskDrive = @(Get-SCVirtualDiskDrive -All | Where-Object {$_.BusType -Eq "IDE" -And $_.PassThroughDisk -Eq $Null -And $_.LUN -Eq 1 -And ($_.Bus -Eq 0 -Or $_.Bus -Eq 1)})
PS C:\> $VirtDiskDrive.Count
```

The first command gets the virtual disk drive objects, excluding pass-through disks, which are connected to the second slot of either IDE channel.
Using the @ symbol and parentheses makes sure that the command stores the results in an array even if the command returns a single object or a $Null value.

The second command displays the number of virtual disk drive objects that match the filter criteria.

### Example 4: Get virtual disk drives for all virtual machine templates
```
PS C:\> $Templates = @(Get-SCVMTemplate)
PS C:\> $Templates | ForEach-Object {Get-SCVirtualDiskDrive -Template $_ | Where-Object {$_.BusType -Eq "IDE"}} | Format-List Name,BusType,Bus,LUN
```

The first command gets all virtual machine templates, and then stores those objects in the $Templates array.

The second command passes each virtual machine template object stored in $Templates to the ForEach-Object cmdlet.
That cmdlet gets all disk drive objects for each template.
Then the command selects only those virtual disk drive objects that use an IDE bus type and passes those objects to the Format-List cmdlet, which displays the Name, Bus Type, Bus, and LUN for each virtual disk drive object.

## PARAMETERS

### -All
Indicates that this cmdlet retrieves a full list of all virtual disk drive objects independent of the parent object.

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

### -ID
Specifies the unique ID of the virtual disk drive that this cmdlet gets.

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

### -VM
Specifies a virtual machine object from which this cmdlet gets virtual disk drives.

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
Specifies a VMM template object that is used to create virtual machines that contain virtual disk drives that this cmdlet gets.

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

### VirtualDiskDrive
This cmdlet returns a **VirtualDiskDrive** object.

## NOTES
* This cmdlet requires a VMM virtual machine template object or a virtual machine object, which can be retrieved by using the Get-SCVMTemplate cmdlet or the Get-SCVirtualMachine cmdlet.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMTemplate.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVirtualDiskDrive.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualDiskDrive.md)

[Test-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Test-SCVirtualDiskDrive.md)

