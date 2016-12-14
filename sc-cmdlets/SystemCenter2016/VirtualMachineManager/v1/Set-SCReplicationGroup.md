---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCReplicationGroup.md
schema: 2.0.0
ms.assetid: AD86DE61-C1F7-4745-81E5-ABCC6E1DDEB2
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCReplicationGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCReplicationGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCReplicationGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCReplicationGroup

## SYNOPSIS
Modifies a replication group.

## SYNTAX

### AddRemoveLunsToRG (Default)
```
Set-SCReplicationGroup [-ReplicationGroup] <ReplicationGroup> [-Name <String>] [-Description <String>]
 [-AddStorageLuns <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]>]
 [-RemoveStorageLuns <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]>]
 [-CreateOnArray] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddRemoveFileSharesToRG
```
Set-SCReplicationGroup [-ReplicationGroup] <ReplicationGroup> [-Name <String>] [-Description <String>]
 [-AddStorageFileShare <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageFileShare]>]
 [-RemoveStorageFileShare <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageFileShare]>]
 [-LogStorageVolume <StorageVolume>] [-LogSizeInMB <UInt64>] [-CreateOnArray] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddRemoveHostVolumesToRG
```
Set-SCReplicationGroup [-ReplicationGroup] <ReplicationGroup>
 [-AddStorageVolume <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]>]
 [-RemoveStorageVolume <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]>]
 [-CreateOnArray] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### ModifyOperations
```
Set-SCReplicationGroup [-ReplicationGroup] <ReplicationGroup> [-CreateOnArray] -Operation <String>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EnableProtectionOperation
```
Set-SCReplicationGroup [-ReplicationGroup] <ReplicationGroup> [-CreateOnArray] -Operation <String>
 [-TargetReplicationGroup <ReplicationGroup>]
 [-TargetLogicalUnit <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]>]
 [-TargetStoragePool <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StoragePool]>]
 [-Rpo <UInt32>] -EnableProtectionMode <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCReplicationGroup** cmdlet modifies a replication group.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AddStorageFileShare


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageFileShare]
Parameter Sets: AddRemoveFileSharesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddStorageLuns


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]
Parameter Sets: AddRemoveLunsToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddStorageVolume


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]
Parameter Sets: AddRemoveHostVolumesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateOnArray


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

### -Description
Specifies a description for a replication group.

```yaml
Type: String
Parameter Sets: AddRemoveLunsToRG, AddRemoveFileSharesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableProtectionMode
Specifies the enable protection mode.
The acceptable values for this parameter are:

- Asynchronous
- Synchronous

```yaml
Type: String
Parameter Sets: EnableProtectionOperation
Aliases: 
Accepted values: Asynchronous, Synchronous

Required: True
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

### -LogSizeInMB
Specifies the log size, in megabytes (MB).

```yaml
Type: UInt64
Parameter Sets: AddRemoveFileSharesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogStorageVolume


```yaml
Type: StorageVolume
Parameter Sets: AddRemoveFileSharesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group to modify.

```yaml
Type: String
Parameter Sets: AddRemoveLunsToRG, AddRemoveFileSharesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operation
Specifies the operation.
The acceptable values for this parameter are:

- EnableProtection
- PrepareForFailover
- Failover
- PrepareForReverseRoles
- ReverseRoles
- Resync
- TearDown

```yaml
Type: String
Parameter Sets: ModifyOperations, EnableProtectionOperation
Aliases: 
Accepted values: EnableProtection, PrepareForFailover, Failover, PrepareForReverseRoles, ReverseRoles, Resync, TearDown

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

### -RemoveStorageFileShare


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageFileShare]
Parameter Sets: AddRemoveFileSharesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveStorageLuns


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]
Parameter Sets: AddRemoveLunsToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveStorageVolume


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]
Parameter Sets: AddRemoveHostVolumesToRG
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationGroup
Specifies the replication group to modify.

```yaml
Type: ReplicationGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Rpo


```yaml
Type: UInt32
Parameter Sets: EnableProtectionOperation
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

### -TargetLogicalUnit


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]
Parameter Sets: EnableProtectionOperation
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetReplicationGroup


```yaml
Type: ReplicationGroup
Parameter Sets: EnableProtectionOperation
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetStoragePool


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StoragePool]
Parameter Sets: EnableProtectionOperation
Aliases: 

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

## NOTES

## RELATED LINKS

[Get-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCReplicationGroup.md)

[New-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCReplicationGroup.md)

[Remove-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCReplicationGroup.md)

