---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLibraryServer.md
schema: 2.0.0
ms.assetid: A85A886D-3D3E-4410-B850-912B43A1ED6A
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCDirectoryChildItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCDirectoryChildItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCDirectoryChildItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDirectoryChildItem

## SYNOPSIS
Gets all files and subdirectories in the specified directory on a virtual machine host or on a library server managed by VMM.

## SYNTAX

### FromVMHost
```
Get-SCDirectoryChildItem -VMHost <Host> -Path <String> [<CommonParameters>]
```

### FromLibraryServer
```
Get-SCDirectoryChildItem -LibraryServer <LibraryServer> -Path <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDirectoryChildItem** cmdlet gets all files and subdirectories immediately under the specified directory on a virtual machine host or on a library server managed by Virtual Machine Manager (VMM).
If you specify a share path (such as \\\\ServerName\ShareName\Directory\FileName), the subdirectories of the share path are returned.

If you use the **Get-SCDirectoryChildItem** cmdlet to retrieve files and subdirectories on a library server, you must specify a path to a valid library share.
For example, the share path to the default library share installed by Setup when you first install VMM is: \\\\VMMServerName.DomainName.com\MSSCVMMLibrary

## EXAMPLES

### Example 1: Get the files and subdirectories for the specified path on a VMM host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> Get-SCDirectoryChildItem -VMHost $VMHost -Path "C:\"
```

The first command gets the host object named VMHost01 from the VMM database and stores the object in the $VMHost variable.

The second command displays the name and other information about each file and subdirectory immediately under the C:\ drive on VMHost01.

### Example 2: Get the subdirectories for the specified path on a library server
```
PS C:\>$LibServ = Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" -ComputerName "FileServer01.Contoso.com"
PS C:\> Get-SCDirectoryChildItem -LibraryServer $LibServ -Path "\\FileServer01.Contoso.com\MSSCVMMLibrary"
```

The first command gets the library server object named FileServer01 from VMMServer01 and stores the object in the $LibServ variable.

The second command displays the name, parent directory, and other information about each file stored in the directory for the default library share on FileServer01.
You must specify the complete path to the library share.

Note: This example assumes that the default VMM library share (MSSCVMMLibrary) is used in your environment.
To get the names of library shares, type `Get-SCLibraryShare | Select Name`.

## PARAMETERS

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: FromLibraryServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the destination path for the operation. 



Example formats: 


Local path:       `-Path "F:\"`

UNC path:         `-Path "\\\\Library\Templates"`

Volume GUID path: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`

VMware ESX path:  `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`

Citrix XenServer path: `- Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`



This parameter accepts wildcard characters for a UNC path.



Example format: 


UNC path:         `-Path "\\\\VMHostServer\MyVMs\*VM*"`

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

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: FromVMHost
Aliases: 

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

### VMHostFileInformation
This cmdlet returns a **VMHostFileInformation** object.

## NOTES

## RELATED LINKS

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLibraryServer.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md)

