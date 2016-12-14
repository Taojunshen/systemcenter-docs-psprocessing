---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCStorageFileShare.md
schema: 2.0.0
ms.assetid: 75931420-B96A-46AB-A1C0-4A45E5DAC0A4
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageFileShare

## SYNOPSIS
Gets a storage file share.

## SYNTAX

### All (Default)
```
Get-SCStorageFileShare [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### FilterByVMHost
```
Get-SCStorageFileShare [-VMMServer <ServerConnection>] [[-Name] <String>] -VMHost <Host> [<CommonParameters>]
```

### FilterByVMHostCluster
```
Get-SCStorageFileShare [-VMMServer <ServerConnection>] [[-Name] <String>] -VMHostCluster <HostCluster>
 [<CommonParameters>]
```

### FilterByLibraryServer
```
Get-SCStorageFileShare [-VMMServer <ServerConnection>] [[-Name] <String>] -LibraryServer <LibraryServer>
 [<CommonParameters>]
```

### ID
```
Get-SCStorageFileShare [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageFileShare** cmdlet gets a storage file share from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Get a storage file share by its name
```
PS C:\>$FileShare = Get-SCStorageFileShare -Name "FileShare01" 
PS C:\> $FileShare
```

The first command gets the storage file share object named FileShare01 and stores the object in the $FileShare variable.

The second command displays information about the storage file share stored in FileShare01.

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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: FilterByLibraryServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
Parameter Sets: FilterByVMHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: FilterByVMHostCluster
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

### StorageFileShare
This cmdlet returns a **StorageFileShare** object.

## NOTES

## RELATED LINKS

[New-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageFileShare.md)

[Register-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Register-SCStorageFileShare.md)

[Remove-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageFileShare.md)

[Repair-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Repair-SCStorageFileShare.md)

[Set-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageFileShare.md)

[Unregister-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Unregister-SCStorageFileShare.md)

