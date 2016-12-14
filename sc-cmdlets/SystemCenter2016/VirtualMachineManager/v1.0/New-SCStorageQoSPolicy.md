---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageQoSPolicy.md
schema: 2.0.0
ms.assetid: 1BC91730-1197-4C31-8ED1-8BB223545DBC
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageQoSPolicy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageQoSPolicy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageQoSPolicy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageQoSPolicy

## SYNOPSIS
Creates a storage QoS policy on one or more storage file servers.

## SYNTAX

```
New-SCStorageQoSPolicy [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -PolicyType <StorageQoSPolicyType> [-IOPSNormalizationSizeKB <UInt32>] [-IOPSMaximum <UInt64>]
 [-IOPSMinimum <UInt64>] [-BandwidthLimitMBPS <UInt64>] [-StorageFileServer <StorageFileServer[]>]
 [-StorageArray <StorageArray[]>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageQoSPolicy** cmdlet creates a storage Quality of Service (QoS) policy on one or more storage file servers.

## EXAMPLES

### Example 1: Create a multi-instance storage QoS policy with maximum IOPS settings for a single file server
```
PS C:\>$FileServersToAdd = @()
PS C:\> $FileServersToAdd += Get-SCStorageFileServer -Name "FileServer01c"
PS C:\> New-SCStorageQoSPolicy -Name "MAXIOPSPolicy" -Description "" -PolicyType "MultiInstance" -IOPSMinimum "0" -IOPSMaximum "10000" -StorageFileServer $FileServersToAdd
```

This command creates a multi-instance storage QoS policy with maximum IOPS settings for a single file server.

### Example 2: Create a single-instance storage QoS policy with minimum IOPS settings for two file servers
```
PS C:\>$FileServersToAdd = @()
PS C:\> $FileServersToAdd += Get-SCStorageFileServer -Name "FileServer01c"
PS C:\> $FileServersToAdd += Get-SCStorageFileServer -Name "FileServer02c"
New-SCStorageQoSPolicy -Name "MINIOPSPolicy" -Description "" -PolicyType "SingleInstance" -IOPSMinimum "5000" -IOPSMaximum "0" -StorageFileServer $FileServersToAdd
```

This command creates a single-instance storage QoS policy with minimum IOPS settings for two file servers.

## PARAMETERS

### -BandwidthLimitMBPS


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

### -Description
Specifies a description for the policy.

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

### -IOPSMaximum
Specifies the maximum IOPS.

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

### -IOPSMinimum
Specifies the minimum IOPS.

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

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -PolicyType
Specifies the QoS policy type.
The acceptable values for this parameter are:

- SingleInstance
- MultiInstance

```yaml
Type: StorageQoSPolicyType
Parameter Sets: (All)
Aliases: 
Accepted values: Aggregated, Dedicated

Required: True
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


```yaml
Type: StorageArray[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFileServer
Specifies an array of storage file server objects.

```yaml
Type: StorageFileServer[]
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

### StorageQoSPolicy
This cmdlet returns a **StorageQoSPolicy** object.

## NOTES

## RELATED LINKS

[Get-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageQoSPolicy.md)

[Remove-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageQoSPolicy.md)

[Set-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageQoSPolicy.md)

