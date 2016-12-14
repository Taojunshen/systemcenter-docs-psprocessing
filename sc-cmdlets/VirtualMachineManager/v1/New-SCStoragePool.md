---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStoragePhysicalDisk.md
schema: 2.0.0
ms.assetid: 98511440-94FE-443E-A603-1F0A8AB53E94
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCStoragePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCStoragePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCStoragePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStoragePool

## SYNOPSIS
Creates a storage pool.

## SYNTAX

```
New-SCStoragePool [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -StorageArray <StorageArray> -StoragePhysicalDisk <StoragePhysicalDisk[]>
 -StorageClassification <StorageClassification> [-FaultDomainAwareness <FaultDomainAwarenessType>]
 [-InterleaveDefaultKB <UInt64>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStoragePool** cmdlet creates a storage pool.

## EXAMPLES

### Example 1: Create pool from physical disks
```
PS C:\>$Disks = Get-SCStoragePhysicalDisk | where {$_.CanPool -eq $True}
PS C:\> New-SCStoragePool -StoragePhysicalDisk $Disks -Name "Pool01"
```

The first command gets all physical disk objects that can be pooled and stores the objects in the $Disks variable.

The second command creates a storage pool named Pool01 with the physical disks stored in $Disks.

## PARAMETERS

### -Description
Specifies a description for the storage pool.

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
Specifies the default interleave size, in kilobytes, for new virtual disks created in this storage pool,

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

### -StorageArray
Specifies a storage array object.
This can be a Fibre Channel or iSCSI storage sub-system that is used to store virtual machine configuration and virtual disks.

```yaml
Type: StorageArray
Parameter Sets: (All)
Aliases: 

Required: True
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePhysicalDisk
Specifies an array of physical disks (spinning media or solid state).

```yaml
Type: StoragePhysicalDisk[]
Parameter Sets: (All)
Aliases: 

Required: True
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

### StoragePool
This cmdlet returns a **StoragePool** object.

## NOTES

## RELATED LINKS

[Get-SCStoragePhysicalDisk](xref:VirtualMachineManager/v1/Get-SCStoragePhysicalDisk.md)

[Get-SCStoragePool](xref:VirtualMachineManager/v1/Get-SCStoragePool.md)

[Remove-SCStoragePool](xref:VirtualMachineManager/v1/Remove-SCStoragePool.md)

[Set-SCStoragePool](xref:VirtualMachineManager/v1/Set-SCStoragePool.md)
