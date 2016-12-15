---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageLogicalUnit.md
schema: 2.0.0
ms.assetid: D04AB1E0-56B2-4572-BAEA-BC7AED5CABC9
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageLogicalUnit.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageLogicalUnit.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageLogicalUnit.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageLogicalUnit

## SYNOPSIS
Creates a logical unit from unallocated capacity in a storage pool.

## SYNTAX

### NewLunFromLun
```
New-SCStorageLogicalUnit [-LogicalUnitCopyMethod <StorageLogicalUnitCopyMethod>] [-VMHostGroup <HostGroup>]
 [-VMMServer <ServerConnection>] [-StorageLogicalUnit] <StorageLogicalUnit> -Name <String>
 [-Description <String>] [-SetLogicalUnitCopySource] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### NewReplicaLunFromLun
```
New-SCStorageLogicalUnit [-LogicalUnitCopyMethod <StorageLogicalUnitCopyMethod>] [-VMHostGroup <HostGroup>]
 [-VMMServer <ServerConnection>] [-StorageLogicalUnit] <StorageLogicalUnit> -Name <String>
 [-Description <String>] -TargetStoragePool <StoragePool> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### NewLunFromPool
```
New-SCStorageLogicalUnit [-ProvisioningType <StorageProvisioningType>] [-VMHostGroup <HostGroup>]
 [-VMMServer <ServerConnection>] -Name <String> [-Description <String>] [-StoragePool] <StoragePool>
 -DiskSizeMB <UInt64> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageLogicalUnit** cmdlet creates a logical unit from unallocated capacity in a storage pool.

## EXAMPLES

### Example 1: Create a copy of an existing logical unit
```
PS C:\>$SourceLU = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> New-SCStorageLogicalUnit -SetLogicalUnitCopySource -StorageLogicalUnit $SourceLU -Name "NewLU" -LogicalUnitCopyMethod Clone
```

The first command gets the storage logical unit object named LUN01 and stores the object in the $SourceLU variable.

The second command creates a new logical unit named NewLU by cloning LUN01.

## PARAMETERS

### -Description
States a description for the specified object.

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

### -DiskSizeMB
Specifies the size of a disk in megabytes (MB).

```yaml
Type: UInt64
Parameter Sets: NewLunFromPool
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

### -LogicalUnitCopyMethod
Specifies the method used by the array to copy an existing logical unit.
Valid values: Clone, Snapshot.

```yaml
Type: StorageLogicalUnitCopyMethod
Parameter Sets: NewLunFromLun, NewReplicaLunFromLun
Aliases: 
Accepted values: Snapshot, Clone, RemoteMirror

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
Parameter Sets: (All)
Aliases: 

Required: True
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

### -ProvisioningType
Specifies a storage provisioning type.
Valid values are: Thin, Fixed.

Thin indicates that capacity is committed on demand for a storage logical unit.

Fixed indicates that capacity is fully committed for a fixed-size storage logical unit.

```yaml
Type: StorageProvisioningType
Parameter Sets: NewLunFromPool
Aliases: 
Accepted values: Unknown, Thin, Fixed

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

### -SetLogicalUnitCopySource
Indicates that the specified storage logical unit is the source from which a clone is copied.

```yaml
Type: SwitchParameter
Parameter Sets: NewLunFromLun
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageLogicalUnit
Specifies a storage logical unit object.

```yaml
Type: StorageLogicalUnit
Parameter Sets: NewLunFromLun, NewReplicaLunFromLun
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoragePool
Specifies a storage pool object.

```yaml
Type: StoragePool
Parameter Sets: NewLunFromPool
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetStoragePool
Specifies the target storage pool.

```yaml
Type: StoragePool
Parameter Sets: NewReplicaLunFromLun
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: (All)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageLogicalUnit
This cmdlet returns a **StorageLogicalUnit** object.

## NOTES

## RELATED LINKS

[Get-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageLogicalUnit.md)

[Register-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageLogicalUnit.md)

[Remove-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageLogicalUnit.md)

[Set-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageLogicalUnit.md)

[Unregister-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageLogicalUnit.md)

