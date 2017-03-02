---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 725D8524-557D-4D67-A722-13CD2BEF5B15
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVirtualFloppyDisk

## SYNOPSIS
Changes the properties of a virtual floppy disk used in VMM.

## SYNTAX

### Default
```
Set-SCVirtualFloppyDisk [-UserRole <UserRole>] [-Enabled <Boolean>] [-VMMServer <ServerConnection>]
 [-VirtualFloppyDisk] <VirtualFloppyDisk> [-Name <String>] [-SharePath <String>] [-Description <String>]
 [-Owner <String>] [-FamilyName <String>] [-Release <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### EquivalencySet
```
Set-SCVirtualFloppyDisk [-VMMServer <ServerConnection>]
 [-VirtualFloppyDisks] <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.VirtualFloppyDisk]>
 -FamilyName <String> -Release <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualFloppyDisk** cmdlet changes one or more properties of a virtual floppy disk used in a Virtual Machine Manager (VMM) environment.
A virtual floppy disk file used in VMM is either a Windows-based .vfd file or a VMware-based .flp file.

Properties that you can change include: 



- Description

- Enabled

- Name 

- Owner

- SharePath

You can store a virtual floppy disk file in the VMM library, or you can add the virtual floppy disk to a virtual machine.

## EXAMPLES

### Example 1: Change the description of a virtual floppy disk
```
PS C:\> $VFD = Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com"  | where { $_.Name -eq "BootFloppy.vfd" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Set-SCVirtualFloppyDisk -VirtualFloppyDisk $VFD -Description "Latest Boot Floppy"
```

The first command gets the floppy disk object named BootFloppy.vfd from the VMM library on VMMServer01 whose file is stored on LibraryServer01, and then stores the object in the $VFD variable.

The second command changes the description of the virtual floppy disk object stored in $VFD to "Latest Boot Floppy".

### Example 2: Disable a virtual floppy disk
```
PS C:\> $VFD = Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "BootFloppy.vfd" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Set-SCVirtualFloppyDisk -VirtualFloppyDisk $VFD -Enabled $FALSE
```

The first command gets the virtual floppy disk object named BootFloppy.vfd whose file is stored on LibraryServer01, and then stores the object in the $VFD variable.

The second command disables the virtual floppy disk object stored in $VFD.

### Example 3: Change the name of a VMware-based virtual floppy disk
```
PS C:\> $FLP = Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "ESXBootFloppy.flp" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Set-SCVirtualFloppyDisk -VirtualFloppyDisk $FLP -Name "ESXBootFloppy-Beta.flp"
```

The first command gets the floppy disk object named ESXBootFloppy.flp on LibraryServer01 and then stores the object in the $FLP variable.

The second command changes the name of the virtual floppy disk object stored in $FLP to ESXBootFloppy-Beta.flp.

Note: By default, the name of a virtual floppy disk object in the library is the same name (including the extension) as the name of the actual virtual floppy disk file on the library share.
Changing the name of the virtual floppy disk object in the library does not change the name of the actual virtual floppy disk file stored on the library server.

### Example 4: Specify an owner for all virtual floppy disks with an "Unknown" owner
```
PS C:\> Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com" | where {$_.Owner -eq "Unknown"} | Set-SCVirtualFloppyDisk -Owner "Contoso\ReneeLo"
```

This command gets all virtual floppy disk objects from the VMM library whose owner is "Unknown", and then specifies an owner for each virtual floppy disk object.

## PARAMETERS

### -Description
Specifies a description for the virtual floppy disk.

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



Example format: `-SharePath "\\LibServer01\LibShare"`

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

### -VirtualFloppyDisk
Specifies a virtual floppy disk object.

```yaml
Type: VirtualFloppyDisk
Parameter Sets: Default
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualFloppyDisks
Specifies an array of floppy disk objects.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.VirtualFloppyDisk]
Parameter Sets: EquivalencySet
Aliases: 

Required: True
Position: 0
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
* Requires a VMM virtual floppy disk object, which can be retrieved by using the **Get-SCVirtualFloppyDisk** cmdlet.

## RELATED LINKS

[Get-SCVirtualFloppyDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDisk.md)

[Get-SCVirtualFloppyDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDrive.md)

[Remove-SCVirtualFloppyDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualFloppyDisk.md)

[Set-SCVirtualFloppyDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDrive.md)

