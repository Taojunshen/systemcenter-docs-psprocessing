---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A371F026-414C-4EA4-9337-F44D239AEE66
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVirtualDiskDrive

## SYNOPSIS
Creates a virtual disk drive object.

## SYNTAX

### existingVHDToVMParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VirtualHardDisk <StandaloneVirtualHardDisk> -Bus <Byte>
 -LUN <Byte> [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-SCSI]
 [-FileName <String>] [-Path <String>] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingVHDToTemplateParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VirtualHardDisk <StandaloneVirtualHardDisk>
 [-SharedStorage <Boolean>] -Bus <Byte> -LUN <Byte> [-VirtualHardDiskFormatType <VHDFormatType>]
 [-CreateDiffDisk <Boolean>] -VMTemplate <Template> [-SCSI] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingVHDToVMParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VirtualHardDisk <StandaloneVirtualHardDisk> -Bus <Byte>
 -LUN <Byte> [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-IDE]
 [-FileName <String>] [-Path <String>] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingVHDToTemplateParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VirtualHardDisk <StandaloneVirtualHardDisk> -Bus <Byte>
 -LUN <Byte> [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template>
 [-IDE] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingVHDToJobGroupParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VirtualHardDisk <StandaloneVirtualHardDisk>
 [-SharedStorage <Boolean>] -Bus <Byte> -LUN <Byte> [-VirtualHardDiskFormatType <VHDFormatType>]
 [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-SCSI] [-FileName <String>] [-Path <String>] [-BootVolume]
 [-SystemVolume] [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingVHDToJobGroupParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -VirtualHardDisk <StandaloneVirtualHardDisk> -Bus <Byte>
 -LUN <Byte> [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-IDE]
 [-FileName <String>] [-Path <String>] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingHostVHDToVMParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-SCSI] -FileName <String>
 -Path <String> [-UseLocalVirtualHardDisk] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToVMParamSetSCSIFixed
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-SCSI] [-Fixed]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToVMParamSetIDEDynamic
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-IDE] [-Dynamic]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToVMParamSetSCSIDynamic
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-SCSI] [-Dynamic]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newVirtualDiskDriveDifferencing
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] [-VM <VM>] [-JobGroup <Guid>] [-SCSI]
 [-IDE] -FileName <String> [-Path <String>] -ParentVirtualHardDiskPath <String> [-Differencing] [-BootVolume]
 [-SystemVolume] [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToVMParamSetIDEFixed
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-IDE] [-Fixed]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingHostVHDToVMParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> [-IDE] -FileName <String>
 -Path <String> [-UseLocalVirtualHardDisk] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HostDiskToVMParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> -StorageDisk <StorageDisk>
 [-IDE] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HostDiskToVMParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VM <VM> -StorageDisk <StorageDisk>
 [-SCSI] [-FileName <String>] [-Path <String>] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToTemplateParamSetSCSIFixed
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template> [-SCSI]
 [-Fixed] -VirtualHardDiskSizeMB <Int64> -FileName <String> [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToTemplateParamSetIDEDynamic
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template> [-IDE]
 [-Dynamic] -VirtualHardDiskSizeMB <Int64> -FileName <String> [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToTemplateParamSetSCSIDynamic
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template> [-SCSI]
 [-Dynamic] -VirtualHardDiskSizeMB <Int64> -FileName <String> [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AnyHostDiskToTemplateParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template>
 [-AnyStorageDisk] [-IDE] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToTemplateParamSetIDEFixed
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template> [-IDE]
 [-Fixed] -VirtualHardDiskSizeMB <Int64> -FileName <String> [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AnyHostDiskToTemplateParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -VMTemplate <Template>
 [-AnyStorageDisk] [-SCSI] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToJobGroupParamSetIDEFixed
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-IDE] [-Fixed]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingHostVHDToVMParamSetSCSIJobGroup
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-SCSI]
 -FileName <String> -Path <String> [-UseLocalVirtualHardDisk] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AnyHostDiskToJobGroupParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-AnyStorageDisk]
 [-IDE] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HostDiskToJobGroupParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid>
 -StorageDisk <StorageDisk> [-SCSI] [-FileName <String>] [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToJobGroupParamSetIDEDynamic
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-IDE] [-Dynamic]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToJobGroupParamSetSCSIDynamic
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-SCSI] [-Dynamic]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HostDiskToJobGroupParamSetIDE
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid>
 -StorageDisk <StorageDisk> [-IDE] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### existingHostVHDToVMParamSetIDEJobGroup
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-IDE]
 -FileName <String> -Path <String> [-UseLocalVirtualHardDisk] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### newToJobGroupParamSetSCSIFixed
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-SCSI] [-Fixed]
 -VirtualHardDiskSizeMB <Int64> -FileName <String> [-Path <String>] [-BootVolume] [-SystemVolume]
 [-VolumeType <VolumeType>] [-StorageClassification <StorageClassification>]
 [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AnyHostDiskToJobGroupParamSetSCSI
```
New-SCVirtualDiskDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte>
 [-VirtualHardDiskFormatType <VHDFormatType>] [-CreateDiffDisk <Boolean>] -JobGroup <Guid> [-AnyStorageDisk]
 [-SCSI] [-BootVolume] [-SystemVolume] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>] [-ReturnImmediately]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualDiskDrive** cmdlet creates a virtual disk drive object on a virtual machine deployed on a host managed by Virtual Machine Manager (VMM), or creates a virtual disk drive object on a template in the VMM library.

In System Center 2016, you can create a differencing disk by using the *Differencing* and *ParentVirtualHardDiskPath* parameters.
A differencing disk is a disk associated in a parent-child relationship to another disk that you want to leave intact.
You can change the data or operating system on the child disk without affecting the parent disk.
You can revert changes to the child disk.
The child disk must have the same virtual hard disk format as the parent disk, either VHD or VHDX.
You can set the format by using the *VirtualHardDiskFormat* parameter.

A virtual hard disk file that is stored on a VMM library share, but is not attached to a virtual disk drive, exists as a stand-alone object in the library.
It could be a Windows-based .vhd or .vhdx file or a VMware-based .vmdk file.

A pass-through disk is a disk on a Hyper-V or VMware ESX host that a virtual machine on that host can use instead of using a virtual hard disk.
The corresponding VMware term is Raw Device Mapping (RDM).
The host disk is either a local hard disk or a logical unit on a Storage Area Network (SAN).
VMM lets the virtual machine bypass the host file system and access the pass-through disk directly.
Hyper-V hosts support pass-through disks and conversion of a pass-through disk to a VHD.
VMware ESX hosts support pass-through disks, but not disk conversion.
Citrix XenServer hosts do not support pass-through disks.

You cannot create a checkpoint of a pass-through disk because checkpoint creation is designed to work with virtual hard disks.

## EXAMPLES

### Example 1: Create a virtual disk drive on a template and attach an existing virtual hard disk
```
PS C:\> $VHD = Get-SCVirtualHardDisk -Name "Blank Disk - Small.vhd"
PS C:\> $VMTemplate = Get-SCVMTemplate | Where-Object {$_.Name -Eq "VMTemplate01"}
PS C:\> New-SCVirtualDiskDrive -VMTemplate $VMTemplate -IDE -Bus 1 -Lun 1 -VirtualHardDisk $VHD
```

The first command gets the virtual hard disk object named Blank Disk - Small from the VMM library by using the **Get-SCVirtualHardDisk** cmdlet.
The command stores that object in the $VHD variable.

The second command gets the virtual machine template object named VMTemplate01 from the library by using the **Get-SCVMTemplate** cmdlet.
The command stores stores that object in the $Template variable.

The last command creates a virtual disk drive on VMTemplate01.
The commandattaches the virtual hard disk stored in $VHD to the second channel in the second slot of the IDE bus on the virtual disk drive.

### Example 2: Create a virtual disk drive and add it to an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> New-SCVirtualDiskDrive -VM $VM -Dynamic -FileName "Test" -IDE -Size 20000 -Bus 0 -LUN 1
```

The first command gets the virtual machine object named VM01 by using the **Get-SCVirtualMachine** cmdlet.
The command stores that object in the $VM variable.

The second command creates a dynamic virtual disk drive on the first IDE channel in the second slot of the virtual machine.
The command specifies its size as 19.5 GB.

### Example 3: Create a virtual disk drive from an existing VHD and attach it to a new virtual machine
```
PS C:\> $JobGroupID = [Guid]::NewGuid().ToString()
PS C:\> $VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | Where-Object {$_.Location -Eq "\\LibServer01.Contoso.com\MSSCVMMLibrary\VHDs\Blank Disk - Large.vhd"} 
PS C:\> New-SCVirtualDiskDrive -IDE -Bus 0 -LUN 1 -JobGroup $JobGroupID -VirtualHardDisk $VHD 
PS C:\> $HWProfile = Get-SCHardwareProfile | Where-Object {$_.Name -Match "NewHWProfile01"}
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost03"
PS C:\> New-SCVirtualMachine -Name "VM10" -Description "New Virtual Machine VM10" -VMMServer "VMMServer01.Contoso.com" -Owner "Contoso\Katarina" -VMHost $VMHost -Path "D:\VirtualMachinePath" -HardwareProfile $HWProfile -JobGroup $JobGroupID -RunAsynchronously -StartAction NeverAutoTurnOnVM -StopAction SaveVM
```

The first command generates a GUID, and the stores it as a string in the $JobGroupID variable.
The job group ID functions as an identifier that groups subsequent commands that include $JobGroupID into a single job group.

The second command gets the virtual hard disk object from the VMM library location \\LibraryServer01.Contoso.com\MSSCVMMLibrary\VHDs\Blank Disk - Large.vhd, and then stores that object in the $VHD variable.

The third command creates a virtual hard disk drive object and assigns the new object to IDE Bus 0 and LUN 1.
This command also attaches the virtual hard disk stored in $VHD to the new object.
By using the *JobGroup* parameter, this command runs just before the last command that invokes the job group and associate the new virtual hard disk drive object with the new virtual machine created in the previous command.

The fourth command gets the hardware profile object that contains the string NewHWProfile01 in its name by using the **Get-SCHardwareProfile** cmdlet.
The command stores that object in the $HwProfile variable.

The fifth command gets the host object named VMHost03 by using the **Get-SCVMHost** cmdlet.
The command stores the host object in the $VMHost variable.

The last command creates a virtual machine named VM10 using the hardware settings stored in $HWProfile.
The command deploys the virtual machine on VMHost03.
The command specifies that the virtual machine is not automatically started when the host starts and is put into a saved state when the virtualization service stops.
This command uses the *JobGroup* parameter to indicate that any previous cmdlets that use the same job group ID is run before creating the virtual machine.
In this case, the **New-SCVirtualDiskDrive** cmdlet from the third command creates a virtual disk drive and associates it with the new virtual machine.

### Example 4: Create a virtual disk drive using a host disk and attach it to an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM04"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost04.Contoso.com"
PS C:\> $HostDisk = @(Get-SCStorageDisk -VMHost $VMHost | Where-Object {$_.IsPassThroughCapable -Eq $True})
PS C:\> New-SCVirtualDiskDrive -VM $VM -HostDisk $HostDisk[0] -SCSI -Bus 0 -LUN 1
```

The first command gets the virtual machine object named VM04, and then stores that object in the $VM variable.

The second command gets the host object named VMHost04, and then stores that object in the $VMHost variable.

The third command gets all storage disk objects on VMHost04 that are pass-through capable, and then stores those objects in the $HostDisk variable.
Using the @ symbol and parentheses makes sure that the command stores the results in an array, in case the command returns a single object or a $Null value.

The last command creates a virtual disk drive object that is connected to a physical host disk on VMHost04.
The virtual disk drive is attached to the second slot of the first SCSI bus on VM04.
This example assumes the virtual machine already has a SCSI controller.

### Example 5: Create a virtual disk drive from an existing VHDX and attach it to an existing virtual machine
```
PS C:\> $VHDX = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | Where-Object {$_.Location -Eq "\\LibServer01.Contoso.com\MSSCVMMLibrary\VHDs\Blank Disk - Large.vhdx"} 
PS C:\> $VM = Get-SCVirtualMachine -Name "VM05"
PS C:\> New-SCVirtualDiskDrive -VM $VM -VirtualHardDisk $VHDX -IDE -Bus 0 -LUN 1
```

The first command gets the virtual hard disk object named Blank Disk - Large.vhdx from the VMM library, and then stores that object in the $VHDX variable.

The second command gets the virtual machine object named VM05, and then stores that object in the $VM variable.

The last command creates a virtual disk drive from Blank Disk - Large.vhdx and attaches the new virtual disk drive to VM05.

### Example 6: Create a differencing disk and attach it to an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM06"
PS C:\> New-SCVirtualDiskDrive -Bus 1 -LUN 1 -FileName "DiffDisk" -ParentVirtualHardDiskPath "C:\VirtualMachines\ParentDisk01.vhdx" -Differencing -VirtualHardDiskFormat "VHDX" -IDE -VM $VM
```

The first command gets the virtual machine object named VM06, and that stores that object in the $VM variable.

The second command creates a differencing disk named DiffDisk.vhdx that has the specified parent disk, and attaches the differencing disk to VM06.

## PARAMETERS

### -AnyStorageDisk
Indicates that this cmdlet uses placeholder parameter that indicates the creation of pass-through disks in a new virtual machine job group.

```yaml
Type: SwitchParameter
Parameter Sets: AnyHostDiskToTemplateParamSetIDE, AnyHostDiskToTemplateParamSetSCSI, AnyHostDiskToJobGroupParamSetIDE, AnyHostDiskToJobGroupParamSetSCSI
Aliases: AnyHostDisk

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BootVolume
Indicates that the volume attached to the **VirtualDiskDrive** is a boot volume.

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

### -Bus
Specifies the IDE bus to which to attach a virtual disk drive or the SCSI bus to which to attach a virtual disk drive.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateDiffDisk
Indicates whether the cmdlet creates a differencing disk.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Differencing
Indicates that the virtual hard disk is created as a differencing disk.

```yaml
Type: SwitchParameter
Parameter Sets: newVirtualDiskDriveDifferencing
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dynamic
Specifies that a virtual hard disk can expand dynamically.

```yaml
Type: SwitchParameter
Parameter Sets: newToVMParamSetIDEDynamic, newToVMParamSetSCSIDynamic, newToTemplateParamSetIDEDynamic, newToTemplateParamSetSCSIDynamic, newToJobGroupParamSetIDEDynamic, newToJobGroupParamSetSCSIDynamic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName
Specifies the file name to use when you rename a virtual hard disk file as you add it to a virtual machine.

```yaml
Type: String
Parameter Sets: existingVHDToVMParamSetSCSI, existingVHDToVMParamSetIDE, existingVHDToJobGroupParamSetSCSI, existingVHDToJobGroupParamSetIDE, HostDiskToVMParamSetSCSI, HostDiskToJobGroupParamSetSCSI
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: existingHostVHDToVMParamSetSCSI, newToVMParamSetSCSIFixed, newToVMParamSetIDEDynamic, newToVMParamSetSCSIDynamic, newVirtualDiskDriveDifferencing, newToVMParamSetIDEFixed, existingHostVHDToVMParamSetIDE, newToTemplateParamSetSCSIFixed, newToTemplateParamSetIDEDynamic, newToTemplateParamSetSCSIDynamic, newToTemplateParamSetIDEFixed, newToJobGroupParamSetIDEFixed, existingHostVHDToVMParamSetSCSIJobGroup, newToJobGroupParamSetIDEDynamic, newToJobGroupParamSetSCSIDynamic, existingHostVHDToVMParamSetIDEJobGroup, newToJobGroupParamSetSCSIFixed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fixed
Indicates that a virtual hard disk is fixed in size.

```yaml
Type: SwitchParameter
Parameter Sets: newToVMParamSetSCSIFixed, newToVMParamSetIDEFixed, newToTemplateParamSetSCSIFixed, newToTemplateParamSetIDEFixed, newToJobGroupParamSetIDEFixed, newToJobGroupParamSetSCSIFixed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IDE
Indicates that IDE is the bus type to which to attach a virtual disk drive object configured on a virtual machine or on a template.

```yaml
Type: SwitchParameter
Parameter Sets: existingVHDToVMParamSetIDE, existingVHDToTemplateParamSetIDE, existingVHDToJobGroupParamSetIDE, newToVMParamSetIDEDynamic, newToVMParamSetIDEFixed, existingHostVHDToVMParamSetIDE, HostDiskToVMParamSetIDE, newToTemplateParamSetIDEDynamic, AnyHostDiskToTemplateParamSetIDE, newToTemplateParamSetIDEFixed, newToJobGroupParamSetIDEFixed, AnyHostDiskToJobGroupParamSetIDE, newToJobGroupParamSetIDEDynamic, HostDiskToJobGroupParamSetIDE, existingHostVHDToVMParamSetIDEJobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: newVirtualDiskDriveDifferencing
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: existingVHDToJobGroupParamSetSCSI, existingVHDToJobGroupParamSetIDE, newToJobGroupParamSetIDEFixed, existingHostVHDToVMParamSetSCSIJobGroup, AnyHostDiskToJobGroupParamSetIDE, HostDiskToJobGroupParamSetSCSI, newToJobGroupParamSetIDEDynamic, newToJobGroupParamSetSCSIDynamic, HostDiskToJobGroupParamSetIDE, existingHostVHDToVMParamSetIDEJobGroup, newToJobGroupParamSetSCSIFixed, AnyHostDiskToJobGroupParamSetSCSI
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: newVirtualDiskDriveDifferencing
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -LUN
Specifies the logical unit number (LUN) for a virtual disk drive object or for a virtual disk drive object on a SCSI bus.

```yaml
Type: Byte
Parameter Sets: (All)
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

### -ParentVirtualHardDiskPath
Specifies the path of the parent virtual hard disk to use to create a differencing disk.

```yaml
Type: String
Parameter Sets: newVirtualDiskDriveDifferencing
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the destination path for the virtual disk drive.

```yaml
Type: String
Parameter Sets: existingVHDToVMParamSetSCSI, existingVHDToVMParamSetIDE, existingVHDToJobGroupParamSetSCSI, existingVHDToJobGroupParamSetIDE, newToVMParamSetSCSIFixed, newToVMParamSetIDEDynamic, newToVMParamSetSCSIDynamic, newVirtualDiskDriveDifferencing, newToVMParamSetIDEFixed, HostDiskToVMParamSetSCSI, newToJobGroupParamSetIDEFixed, HostDiskToJobGroupParamSetSCSI, newToJobGroupParamSetIDEDynamic, newToJobGroupParamSetSCSIDynamic, newToJobGroupParamSetSCSIFixed
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: existingHostVHDToVMParamSetSCSI, existingHostVHDToVMParamSetIDE, existingHostVHDToVMParamSetSCSIJobGroup, existingHostVHDToVMParamSetIDEJobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReturnImmediately
Indicates that control is returned to the calling process immediately, before the job is created.

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

### -SCSI
Specifies SCSI as the bus type to which to attach a virtual disk drive object configured on a virtual machine or on a template.

```yaml
Type: SwitchParameter
Parameter Sets: existingVHDToVMParamSetSCSI, existingVHDToTemplateParamSetSCSI, existingVHDToJobGroupParamSetSCSI, existingHostVHDToVMParamSetSCSI, newToVMParamSetSCSIFixed, newToVMParamSetSCSIDynamic, HostDiskToVMParamSetSCSI, newToTemplateParamSetSCSIFixed, newToTemplateParamSetSCSIDynamic, AnyHostDiskToTemplateParamSetSCSI, existingHostVHDToVMParamSetSCSIJobGroup, HostDiskToJobGroupParamSetSCSI, newToJobGroupParamSetSCSIDynamic, newToJobGroupParamSetSCSIFixed, AnyHostDiskToJobGroupParamSetSCSI
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: newVirtualDiskDriveDifferencing
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedStorage
Indicates whether the virtual disk drive uses shared storage.

```yaml
Type: Boolean
Parameter Sets: existingVHDToTemplateParamSetSCSI, existingVHDToJobGroupParamSetSCSI
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageClassification
Specifies a storage classification object.

```yaml
Type: StorageClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageDisk
Specifies a disk on a Hyper-V or VMware ESX host that a virtual machine on that host can use instead of using a virtual hard disk.
This disk is referred to as a pass-through disk.
The corresponding VMware term is Raw Device Mapping (RDM).
The host disk is either a local hard disk or a logical unit on a Storage Area Network (SAN).
VMM lets the virtual machine bypass the host's file system and access the pass-through disk directly.
Hyper-V hosts support pass-through disks and conversion of a pass-through disk to a VHD.
VMware ESX hosts support pass-through disks, but not disk conversion.
Citrix XenServer hosts do not support pass-through disks.

```yaml
Type: StorageDisk
Parameter Sets: HostDiskToVMParamSetIDE, HostDiskToVMParamSetSCSI, HostDiskToJobGroupParamSetSCSI, HostDiskToJobGroupParamSetIDE
Aliases: HostDisk

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQoSPolicy
Specifies a storage Quality of Service (QoS) policy.

```yaml
Type: StorageQoSPolicy
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemVolume
Indicates that the volume attached to the **VirtualDiskDrive** is a system volume.

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

### -UseLocalVirtualHardDisk
Verifies that the VHD file or files to use to create the virtual machine exist and are stored on the destination host.

```yaml
Type: SwitchParameter
Parameter Sets: existingHostVHDToVMParamSetSCSI, existingHostVHDToVMParamSetIDE, existingHostVHDToVMParamSetSCSIJobGroup, existingHostVHDToVMParamSetIDEJobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: existingVHDToVMParamSetSCSI, existingVHDToVMParamSetIDE, existingHostVHDToVMParamSetSCSI, newToVMParamSetSCSIFixed, newToVMParamSetIDEDynamic, newToVMParamSetSCSIDynamic, newToVMParamSetIDEFixed, existingHostVHDToVMParamSetIDE, HostDiskToVMParamSetIDE, HostDiskToVMParamSetSCSI
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: VM
Parameter Sets: newVirtualDiskDriveDifferencing
Aliases: 

Required: False
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
Specifies a VMM template object that is used to create virtual machines.

```yaml
Type: Template
Parameter Sets: existingVHDToTemplateParamSetSCSI, existingVHDToTemplateParamSetIDE, newToTemplateParamSetSCSIFixed, newToTemplateParamSetIDEDynamic, newToTemplateParamSetSCSIDynamic, AnyHostDiskToTemplateParamSetIDE, newToTemplateParamSetIDEFixed, AnyHostDiskToTemplateParamSetSCSI
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: StandaloneVirtualHardDisk
Parameter Sets: existingVHDToVMParamSetSCSI, existingVHDToTemplateParamSetSCSI, existingVHDToVMParamSetIDE, existingVHDToTemplateParamSetIDE, existingVHDToJobGroupParamSetSCSI, existingVHDToJobGroupParamSetIDE
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskFormatType
Specifies the hard disk format type.
Valid values are: 

- VHD
- VMDK
- VHDX

```yaml
Type: VHDFormatType
Parameter Sets: (All)
Aliases: 
Accepted values: VHD, VMDK, VHDX, VHDS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskSizeMB
Specifies the size, in megabytes (MB), of a fixed virtual hard disk file or the maximum possible size of a dynamically expanding virtual hard disk file.

```yaml
Type: Int64
Parameter Sets: newToVMParamSetSCSIFixed, newToVMParamSetIDEDynamic, newToVMParamSetSCSIDynamic, newToVMParamSetIDEFixed, newToTemplateParamSetSCSIFixed, newToTemplateParamSetIDEDynamic, newToTemplateParamSetSCSIDynamic, newToTemplateParamSetIDEFixed, newToJobGroupParamSetIDEFixed, newToJobGroupParamSetIDEDynamic, newToJobGroupParamSetSCSIDynamic, newToJobGroupParamSetSCSIFixed
Aliases: Size

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeType
Specifies the volume type for a virtual hard disk.
Valid values are: Boot, System, BootAndSystem, and None.

```yaml
Type: VolumeType
Parameter Sets: (All)
Aliases: 
Accepted values: None, Boot, System, BootAndSystem

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

### VirtualDiskDrive
This cmdlet returns a **VirtualDiskDrive** object.

## NOTES
* This cmdlet requires a VMM virtual hard disk object, which can be retrieved by using the **Get-SCVirtualHardDisk** cmdlet.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Expand-SCVirtualDiskDrive.md)

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHardwareProfile.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDisk.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Move-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualHardDisk.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDiskDrive.md)

[Remove-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualHardDisk.md)

[Set-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDiskDrive.md)

[Set-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDisk.md)

