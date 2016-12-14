---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCReplicationGroup.md
schema: 2.0.0
ms.assetid: 8C3733CC-44F4-415D-A8C8-F705EBD8BE68
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCReplicationGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCReplicationGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCReplicationGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCReplicationGroup

## SYNOPSIS
Creates a new replication group.

## SYNTAX

### NewRGFromLuns (Default)
```
New-SCReplicationGroup [-VMMServer <ServerConnection>] -Name <String> [-Description <String>] [-CreateOnArray]
 -StorageLogicalUnit <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewRGFromHostVolumes
```
New-SCReplicationGroup [-VMMServer <ServerConnection>] -Name <String> [-Description <String>] [-CreateOnArray]
 [-ProtectionMode <String>]
 -StorageVolume <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]>
 [-LogStorageVolume <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]>]
 [-LogSizeInMB <UInt64>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewRGFromFileShares
```
New-SCReplicationGroup [-VMMServer <ServerConnection>] -Name <String> [-Description <String>] [-CreateOnArray]
 [-ProtectionMode <String>]
 -StorageFileShare <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageFileShare]>
 [-ReplicationGroupType <ReplicationGroupType>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### NewSnapshotForTestFailover
```
New-SCReplicationGroup [-VMMServer <ServerConnection>] -Name <String> [-Description <String>] [-CreateOnArray]
 -SourceReplicationGroup <ReplicationGroup> [-LogicalUnitCopyMethod <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCReplicationGroup** cmdlet creates a new replication group.

## EXAMPLES

### 1:
```

```

## PARAMETERS

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
Specifies a description for the replication group.

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

### -LogSizeInMB
Specifies the log size, in megabytes (MB).

```yaml
Type: UInt64
Parameter Sets: NewRGFromHostVolumes
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogStorageVolume


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]
Parameter Sets: NewRGFromHostVolumes
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalUnitCopyMethod


```yaml
Type: String
Parameter Sets: NewSnapshotForTestFailover
Aliases: 
Accepted values: Snapshot, Clone

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group.

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

### -ProtectionMode


```yaml
Type: String
Parameter Sets: NewRGFromHostVolumes, NewRGFromFileShares
Aliases: 
Accepted values: Asynchronous, Synchronous

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationGroupType


```yaml
Type: ReplicationGroupType
Parameter Sets: NewRGFromFileShares
Aliases: 
Accepted values: None, Lun, Disk, Volume, Share, File

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

### -SourceReplicationGroup


```yaml
Type: ReplicationGroup
Parameter Sets: NewSnapshotForTestFailover
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageFileShare


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageFileShare]
Parameter Sets: NewRGFromFileShares
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageLogicalUnit
Specifies a storage logical unit object.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageLogicalUnit]
Parameter Sets: NewRGFromLuns
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageVolume


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StorageVolume]
Parameter Sets: NewRGFromHostVolumes
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

## NOTES

## RELATED LINKS

[Get-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCReplicationGroup.md)

[Remove-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCReplicationGroup.md)

[Set-SCReplicationGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCReplicationGroup.md)

