---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CC8F8CE2-C2A2-45FF-871A-9F5A9580570F
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Copy-SCVirtualHardDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Copy-SCVirtualHardDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Copy-SCVirtualHardDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Copy-SCVirtualHardDisk

## SYNOPSIS
Copies a VMware virtual hard disk file (a .vmdk file) to a Windows-based virtual hard disk file (a .vhd file) and converts the virtual hard disk for use in a VMM environment.

## SYNTAX

```
Copy-SCVirtualHardDisk [-VMMServer <ServerConnection>] -VMDKPath <String> [-LibraryServer <LibraryServer>]
 [-SourceVMHost <Host>] -VMHost <Host> -Path <String> [-Owner <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-SCVirtualHardDisk** cmdlet copies a VMware virtual hard disk file (a .vmdk file) to a Windows-based virtual hard disk file (a .vhd file) and converts the virtual hard disk for use in a Virtual Machine Manager (VMM) environment.
The disk's contents are preserved by this copy operation.

VMware virtual hard disks, stored in .vmdk files, contain the virtual machine's guest operating system, applications, and data.
VMWare virtual hard disk formats supported by **Copy-SCVirtualHardDisk** include: 



 -- monolithicSparse

 -- monolithicFlat

 -- vmfs

 -- twoGbMaxExtentSparse

 -- twoGbMaxExtentFlat

The **Copy-SCVirtualHardDisk** cmdlet takes as its input the .vmdk file that the .vmx file points to: 



- The .vmx file points to a .vmdk file that contains metadata, which in turn points to the binary .vmdk file. 

- The .vmdk file that you specify with the **Copy-VMDK** cmdlet is the .vmdk file that contains the metadata (not the binary .vmdk file).

## EXAMPLES

### Example 1: Convert a VMware .vmdk file in the VMM library to a Windows-based .vhd file on a host
```
PS C:\> $LibServ = Get-SCLibraryServer -ComputerName "LibServer01.Contoso.com"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMMHost01.Contoso.com"
PS C:\> Copy-SCVirtualHardDisk -LibraryServer $LibServ -VMDKPath "\\LibServer01\MSSCVMMLibrary\VMware\VM01.vmdk" -VMHost $VMHost -Path "C:\StoredWindowsVMs"
```

The first command gets the library server object named LibServer01 and stores the object in the $LibServ variable.

The second command gets the host object named VMHost01 and stores the object in the $VMHost variable.
VMHost01 is a Hyper-V host.

The last command copies and converts the .vmdk file located at the specified path (\\LibServer01\MSSCVMMLibrary\VMware\VM01.vmdk) on the library server and stores the resulting .vhd file at the specified path (C:\StoredWindowsVMs) on VMHost01.
Note that the *Path* parameter, when used with **Copy-SCVirtualHardDisk**, cannot take a UNC path.

Note: **Copy-SCVirtualHardDisk** takes as its input the .vmdk file that the .vmx file points to: 



- The .vmx file points to a .vmdk file that contains metadata, which in turn points to the binary .vmdk file. 

- The .vmdk file that you specify with **Copy-SCVirtualHardDisk** is the .vmdk file that contains the metadata (not the binary .vmdk file).

## PARAMETERS

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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: (All)
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
Parameter Sets: (All)
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

### -Path
Specifies the destination path for the operation. 

Example formats: 

- Local path: `-Path "F:\"`
- UNC path: `-Path "\\Library\Templates"`
- Volume GUID path: `-Path "\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`
- VMware ESX path: `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`
- Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

```yaml
Type: String
Parameter Sets: (All)
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

### -SourceVMHost
Specifies the source virtual machine host object.

```yaml
Type: Host
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMDKPath
Specifies the path to a VMware virtual hard disk file (a .vmdk file) to be converted to a Windows-based virtual hard disk file (a .vhd file).
The VMDK stands for the Virtual Machine Disk (VMDK) file format. 



Example format: `-VMDKPath "\\FileServer01\MSSCVMMLibrary\VMDKS\VM01.vmdk"`

Example format: `-VMDKPath "\[storage1\] /VM01/VM01.vmdk"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: (All)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StandaloneVirtualHardDisk[]
This cmdlet returns an array of **StandaloneVirtualHardDisk** objects.

## NOTES

## RELATED LINKS

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

[New-SCV2V](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCV2V.md)

[New-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md)

