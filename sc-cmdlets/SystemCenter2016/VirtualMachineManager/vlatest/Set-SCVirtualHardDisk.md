---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 89ED5205-CF9A-435C-840A-F8AFA35FAB60
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualHardDisk

## SYNOPSIS
Changes the properties of a virtual hard disk object used in VMM.

## SYNTAX

### Default
```
Set-SCVirtualHardDisk [-OperatingSystem <OperatingSystem>] [-VirtualizationPlatform <VirtualizationPlatform>]
 [-Tag <System.Collections.Generic.List`1[System.String]>] [-ProductKey <String>] [-UserRole <UserRole>]
 [-Enabled <Boolean>] [-VMMServer <ServerConnection>] [-VirtualHardDisk] <VirtualHardDisk> [-JobGroup <Guid>]
 [-Name <String>] [-SharePath <String>] [-Description <String>] [-Owner <String>] [-FamilyName <String>]
 [-Release <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EquivalencySet
```
Set-SCVirtualHardDisk [-VMMServer <ServerConnection>]
 [-VirtualHardDisks] <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.VirtualHardDisk]>
 -FamilyName <String> -Release <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualHardDisk** cmdlet changes one or more properties of a virtual hard disk object used in a Virtual Machine Manager (VMM) environment.
A virtual hard disk file used in VMM is either a Windows-based .vhd file, a Citrix XenServer-based .vhd file, or a VMware-based .vmdk file.

Properties that you can change include: 

- Description
- Enabled
- Name
- Operating System
- Owner
- SharePath

A virtual hard disk file might be stored in the VMM library, or it might be attached to a virtual disk drive on a virtual machine or template.

To change the Bus and LUN settings for a virtual disk drive, use the **Set-SCVirtualDiskDrive** cmdlet.

## EXAMPLES

### Example 1: Change the description of a virtual hard disk
```
PS C:\> $VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "WindowsServer2008R2BootVHD.vhd"}
PS C:\> Set-SCVirtualHardDisk -VirtualHardDisk $VHD -Description "Latest Windows Server 2008 R2 Boot VHD"
```

The first command retrieves the virtual hard disk object named "WindowsServer2003BootVHD.vhd" from the library on VMMServer01 and then stores the object in the $VHD variable.

The second command changes the description of the virtual hard disk object stored in $VHD to "Latest Windows Server 2008 R2 Boot VHD".

### Example 2: Enable a VMware-based virtual hard disk in the library
```
PS C:\> $VMDK = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "WindowsServer2008.vmdk"}
PS C:\> Set-SCVirtualHardDisk -VirtualHardDisk $VMDK -Enabled $FALSE
```

The first command gets the virtual hard disk object named WindowsServer2008.vmdk and then stores the virtual hard disk object in the $VMDK variable.

The second command disables the virtual hard disk object stored in $VMDK.

### Example 3: Specify an owner for all virtual hard disks with an "Unknown" owner
```
PS C:\> Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where {$_.Owner -eq "Unknown"} | Set-SCVirtualHardDisk -Owner "Contoso\ReneeLo"
```

This command gets all virtual hard disk objects from the VMM library whose owner is "Unknown", and then specifies an owner for each virtual hard disk object.

## PARAMETERS

### -Description
Specifies a description for the virtual hard disk object.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Enables an object when set to $True, or disables an object when set to $False.
For example, if you want to upgrade software on a virtual machine template, you can disable the template object in the VMM library to temporarily prevent users from using that object.

```yaml
Type: Boolean
Parameter Sets: Default
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
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: EquivalencySet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To list the names of all available operating systems in VMM, type `Get-SCOperatingSystem`.

```yaml
Type: OperatingSystem
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account. 
 
- Example format: `-Owner "Contoso\PattiFuller"`
- Example format: `-Owner "PattiFuller@Contoso"`

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductKey
Specifies a product key.
The product key is a 25-digit number that identifies the product license.
A product key can be used to register VMM or an operating system to be installed on a virtual machine or host.

```yaml
Type: String
Parameter Sets: Default
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
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: EquivalencySet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path. 

Example format: ` -SharePath "\\LibServer01\LibShare"`

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object.

```yaml
Type: UserRole
Parameter Sets: Default
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

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: VirtualHardDisk
Parameter Sets: Default
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHardDisks
Specifies an array of virtual hard disk objects.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.VirtualHardDisk]
Parameter Sets: EquivalencySet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualizationPlatform
Specifies the virtualization platform of a virtual machine host managed by VMM. 
The acceptable values for this parameter are:

- HyperV
- VMwareESX
- XENServer

```yaml
Type: VirtualizationPlatform
Parameter Sets: Default
Aliases: 
Accepted values: Unknown, VirtualServer, HyperV, VMWareVC, VMWareESX, XENServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualHardDisk
This cmdlet returns a **VirtualHardDisk** object.

## NOTES
* Requires a VMM virtual hard disk object, which can be retrieved by using the **Get-SCVirtualHardDisk** cmdlet.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDisk.md)

[Move-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualHardDisk.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDiskDrive.md)

[Remove-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualHardDisk.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDiskDrive.md)

