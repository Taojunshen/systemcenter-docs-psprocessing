---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E811B2FF-06C6-4B8F-AD2A-917617E04ADD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageArray.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageArray.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageArray.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCStorageArray

## SYNOPSIS
Modifies the properties of a storage array object.

## SYNTAX

### Default (Default)
```
Set-SCStorageArray [-LogicalUnitCopyMethod <StorageLogicalUnitCopyMethod>]
 [-CreateStorageGroupsPerCluster <Boolean>] [-MaximumStorageLogicalUnitNameLength <Int16>]
 [-DiscoverPhysicalDisks] [-IOPSNormalizationSizeKB <UInt32>] [-StorageArray] <StorageArray> [-Name <String>]
 [-Description <String>] [-RemoveStoragePoolFromManagement <StoragePool[]>] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EnablePoolManagement
```
Set-SCStorageArray [-LogicalUnitCopyMethod <StorageLogicalUnitCopyMethod>]
 [-CreateStorageGroupsPerCluster <Boolean>] [-MaximumStorageLogicalUnitNameLength <Int16>]
 [-DiscoverPhysicalDisks] [-IOPSNormalizationSizeKB <UInt32>] [-StorageArray] <StorageArray> [-Name <String>]
 [-Description <String>] -AddStoragePoolToManagement <StoragePool[]>
 -StorageClassificationAssociation <StorageClassification[]> [-VMHostGroupAssociation <HostGroup[]>]
 [-RemoveStoragePoolFromManagement <StoragePool[]>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### SetStoragePeerArray
```
Set-SCStorageArray [-LogicalUnitCopyMethod <StorageLogicalUnitCopyMethod>]
 [-CreateStorageGroupsPerCluster <Boolean>] [-MaximumStorageLogicalUnitNameLength <Int16>]
 [-DiscoverPhysicalDisks] [-IOPSNormalizationSizeKB <UInt32>] [-StorageArray] <StorageArray> [-Name <String>]
 [-Description <String>] [-RemoveStoragePoolFromManagement <StoragePool[]>] [-JobGroup <Guid>]
 -PeerStorageArrayName <String> [-Pair] [-UnPair] [-RunAsAccount <RunAsAccount>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageArray** cmdlet modifies the properties of a Virtual Machine Manager (VMM) storage array object.

## EXAMPLES

### Example 1: Change the name of a storage array
```
PS C:\> $Array = @(Get-SCStorageArray)[0]
PS C:\> Set-SCStorageArray -StorageArray $Array -Name "New Name"
```

The first command gets the first item in the storage array, and then stores it in the $Array variable.

The second command changes the name of the storage array stored in $Array to New Name.

## PARAMETERS

### -AddStoragePoolToManagement
Indicates whether management of a storage pool through VMM is enabled.
When set to $True, VMM imports all logical unit objects hosted by the storage pool.

```yaml
Type: StoragePool[]
Parameter Sets: EnablePoolManagement
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateStorageGroupsPerCluster
Indicates whether a storage group is created for each cluster.

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

### -Description
Specifies a description for the storage array.

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

### -DiscoverPhysicalDisks
Indicates that the cmdlet performs a level 3 discovery of physical disks.

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

### -IOPSNormalizationSizeKB


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an ID for a series of commands that run as a set just before the final command that includes the same job group ID runs.

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

### -JobVariable
Specifies the name of a variable in which to track and store job progress.

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
Valid values are: Clone and Snapshot.

```yaml
Type: StorageLogicalUnitCopyMethod
Parameter Sets: (All)
Aliases: 
Accepted values: Snapshot, Clone, RemoteMirror

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumStorageLogicalUnitNameLength
Specifies the maximum length that the name for a logical unit can be.

```yaml
Type: Int16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name for the storage array.

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

### -Pair


```yaml
Type: SwitchParameter
Parameter Sets: SetStoragePeerArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerStorageArrayName


```yaml
Type: String
Parameter Sets: SetStoragePeerArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveStoragePoolFromManagement
Removes a storage pool from VMM management.
This parameter deletes all logical unit information from VMM, but does not delete any data from the logical units themselves.

```yaml
Type: StoragePool[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount


```yaml
Type: RunAsAccount
Parameter Sets: SetStoragePeerArray
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
This array can be a Fibre Channel or iSCSI storage sub-system that is used to store virtual machine configuration and virtual disks.

```yaml
Type: StorageArray
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageClassificationAssociation
Specifies an array of storage classification objects that is associated with a storage pool.

```yaml
Type: StorageClassification[]
Parameter Sets: EnablePoolManagement
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnPair


```yaml
Type: SwitchParameter
Parameter Sets: SetStoragePeerArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroupAssociation
Specifies an array of host group objects.

```yaml
Type: HostGroup[]
Parameter Sets: EnablePoolManagement
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

### StorageArray
This cmdlet returns a **StorageArray** object.

## NOTES

## RELATED LINKS

[Get-SCStorageArray](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageArray.md)

