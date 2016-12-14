---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageClassification.md
schema: 2.0.0
ms.assetid: 83859642-7FC8-444C-B06B-46880F5DF408
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStoragePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStoragePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStoragePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStoragePool

## SYNOPSIS
Modifies a storage pool object in the VMM database.

## SYNTAX

```
Set-SCStoragePool [-StorageClassification <StorageClassification>] [-StoragePool] <StoragePool>
 [-Name <String>] [-Description <String>] [-AddVMHostGroup <HostGroup[]>] [-RemoveVMHostGroup <HostGroup[]>]
 [-AddStoragePhysicalDisk <StoragePhysicalDisk[]>] [-RemoveStoragePhysicalDisk <StoragePhysicalDisk[]>]
 [-Optimize] [-FaultDomainAwareness <FaultDomainAwarenessType>] [-InterleaveDefaultKB <UInt64>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStoragePool** cmdlet modifies a storage pool object in the Virtual Machine Manager (VMM) database.
You can change the properties of a storage pool, add a VMHostGroup to the storage pool, or remove a VMHostGroup from a storage pool.

## EXAMPLES

### Example 1: Change the name of a storage pool
```
PS C:\>$Pool = @(Get-SCStoragePool)[0]
PS C:\> Set-SCStoragePool -StoragePool $Pool -Name "New name of pool"
```

The first command gets all storage pool objects and places them in an array.
The command then stores the first item in the storage pool array in the $Pool variable.

The second command changes the name of the storage pool stored in the $Pool variable to "New name of pool".

### Example 2: Set the classification for a storage pool
```
PS C:\>$Pool = Get-SCStoragePool -ID "346e17e9-d50a-480e-8dec-c41d7e2125b0"
PS C:\> $Classification = Get-SCStorageClassification -Name "StorageClassification01"
PS C:\> Set-SCStoragePool -StoragePool $Pool -StorageClassification $Classification
```

The first command gets the storage pool object with the ID of 346e17e9-d50a-480e-8dec-c41d7e2125b0 and stores the object in the $Pool variable.

The second command gets the storage classification object named StorageClassification01 and stores the object in the $Classification variable.

The last command associates the storage classification stored in $Classification (StorageClassification01) with the storage pool stored in $Pool.

## PARAMETERS

### -AddStoragePhysicalDisk
Specifies an array of physical disk objects to add.

```yaml
Type: StoragePhysicalDisk[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddVMHostGroup
Specifies an array of host groups that this cmdlet adds to an existing host group array or private cloud.

```yaml
Type: HostGroup[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -FaultDomainAwareness
Specifies the default fault domain for new virtual disks created in this storage pool.
The acceptable values for this parameter are:

- 1,  PhysicalDisk
- 2,  StorageEnclosure
- 3,  Node

```yaml
Type: FaultDomainAwarenessType
Parameter Sets: (All)
Aliases: 
Accepted values: NotSupported, PhysicalDisk, StorageEnclosure, StorageScaleUnit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterleaveDefaultKB
Specifies the default interleave size, in kilobytes, for new virtual disks created in this storage pool.

```yaml
Type: UInt64
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Optimize


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

### -RemoveStoragePhysicalDisk
Specifies an array of physical disks to remove from this storage pool.

```yaml
Type: StoragePhysicalDisk[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveVMHostGroup
Specifies an array of host groups that this cmdlet removes from a host group array or private cloud.

```yaml
Type: HostGroup[]
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

### -StoragePool
Specifies a storage pool object.

```yaml
Type: StoragePool
Parameter Sets: (All)
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

### StoragePool
This cmdlet returns a **StoragePool** object.

## NOTES

## RELATED LINKS

[Get-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageClassification.md)

[Get-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStoragePool.md)

[New-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCStoragePool.md)

[Remove-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStoragePool.md)

