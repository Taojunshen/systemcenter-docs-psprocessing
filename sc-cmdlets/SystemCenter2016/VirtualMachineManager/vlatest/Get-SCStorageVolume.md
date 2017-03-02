---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3F284231-E9CC-4EB5-9C2D-7DE8EBCE3D3E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageVolume.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageVolume.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageVolume.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCStorageVolume

## SYNOPSIS
Gets a storage volume object from a host managed by VMM.

## SYNTAX

### NoFilter (Default)
```
Get-SCStorageVolume [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### StorageVolumeByLibraryServer
```
Get-SCStorageVolume -LibraryServer <LibraryServer> [[-Name] <String>] [<CommonParameters>]
```

### StorageVolumeByStorageArray
```
Get-SCStorageVolume -StorageArray <StorageArray> [[-Name] <String>] [<CommonParameters>]
```

### FilterByVMHost
```
Get-SCStorageVolume -VMHost <Host> [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageVolume** cmdlet gets one or more storage volume objects from a host managed by Virtual Machine Manager (VMM).

The information returned includes, but is not limited to, the following: 



- Name.
The name of each host volume (such as C:\, D:\, E:\\). 


- StorageVolumeID.
The volume ID (a GUID) for each host volume.
The host volume ID is unique across your VMM environment. 


- MountPoints.
The mount points for each volume. 
A single volume, such as C:\, can contain multiple mount points. 


- Capacity.
The storage capacity of each volume. 


- FreeSpace.
The amount of free space on each volume. 


- VolumeLabel.
A user-defined label for this volume (if any). 


- IsSANMigrationPossible.
A flag indicating whether or not SAN  migration is available. 


- IsClustered - A flag indicating whether the volume is local storage or  shared storage (that is, uses external storage, such as SAN or iSCSI) and a clustered disk resource exists for this volume. 


- InUse.
A flag that is set to True when one of the highly available virtual machines managed by VMM is using this volume. 


- VMHost.
The FQDN name of the host on which each volume resides. 


- IsAvailableForPlacement.
A flag indicating whether this volume  is available as a location on which to deploy virtual machines  on this host. 


- ServerConnection.
The VMM server connection that is managing  the host that this volume belongs to. 


- ID. 
The ID (a GUID) for each volume.

## EXAMPLES

### Example 1: Get all volumes on the specified host server
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> Get-SCStorageVolume -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets all drive volume objects from VMHost01 and displays information about these volumes to the user.

Note: To translate the capacity and free space from bytes into larger units of measure, divide the number of bytes by 1024 to get kilobytes (KB); divide the result by 1024 to get megabytes (MB); and divide that result by 1024 to get gigabytes (GB).

### Example 2: Get the specified volume on a host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com" 
PS C:\> Get-SCStorageVolume -VMHost $VMHost -Name "C:\"
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command gets the drive volume named C:\ from VMHost02 and displays information about this volume to the user.

### Example 3: Get all volumes on VMware ESX hosts that contain the string "SharedStorage" in the volume name
```
PS C:\> $VMHost = Get-SCVMHost -VMMServer "VMMServer01.Contoso.com" | where { $_.VirtualizationPlatform -eq "VMwareESX" }
PS C:\> $VMHost | Get-SCStorageVolume | select -Property Name, VMHost | where { $_.Name -match "SharedStorage" }
```

The first command gets all host objects from VMMServer01, selects only those host objects whose virtualization platform is VMware ESX, and then stores those host objects in $VMHost.

Note: This example assumes that the names of all volumes on these ESX Servers include the string "storage", but that only some of those volumes' names include the string "SharedStorage."

The second command passes each ESX host object in $VMHost to the **Get-SCStorageVolume** cmdlet, which gets the volume objects on these hosts and then, in turn, passes the volume objects to "select" (the alias for the **Select-Object** cmdlet).
The **Select-Object** cmdlet displays the volume name and the host that volume resides on for those volumes whose name contains the string "SharedStorage".

## PARAMETERS

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: StorageVolumeByLibraryServer
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

### -StorageArray
Specifies a storage array object.
This can be a Fibre Channel or iSCSI storage sub-system that is used to store virtual machine configuration and virtual disks.

```yaml
Type: StorageArray
Parameter Sets: StorageVolumeByStorageArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: NoFilter
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

### StorageVolume
This cmdlet returns a **StorageVolume** object.

## NOTES

## RELATED LINKS

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[New-SCStorageVolume](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageVolume.md)

[Set-SCStorageVolume](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageVolume.md)

