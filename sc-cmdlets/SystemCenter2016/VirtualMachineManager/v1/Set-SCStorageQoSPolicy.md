---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageQoSPolicy.md
schema: 2.0.0
ms.assetid: DFECB9BC-1011-4128-92F2-4E7B597840B8
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageQoSPolicy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageQoSPolicy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageQoSPolicy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageQoSPolicy

## SYNOPSIS
Modifies a storage QoS policy on one or more storage file servers.

## SYNTAX

```
Set-SCStorageQoSPolicy [-StorageQoSPolicy] <StorageQoSPolicy> [-Name <String>] [-Description <String>]
 [-IOPSMaximum <UInt64>] [-IOPSMinimum <UInt64>] [-BandwidthLimitMBPS <UInt64>]
 [-AddStorageFileServer <StorageFileServer[]>] [-RemoveStorageFileServer <StorageFileServer[]>]
 [-AddStorageArray <StorageArray[]>] [-RemoveStorageArray <StorageArray[]>] [-RepairPolicy]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageQoSPolicy** cmdlet modifies a storage Quality of Service (QoS) policy on one or more storage file servers.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AddStorageArray


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

### -AddStorageFileServer
Specifies an array of storage file servers.

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
Specifies a description for the QoS policy.

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

### -RemoveStorageArray


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

### -RemoveStorageFileServer
Specifies an array of storage file servers.

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

### -RepairPolicy
Indicates that this operation repairs the specified policy.

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

### -StorageQoSPolicy
Specifies a **StorageQoSPolicy** object.

```yaml
Type: StorageQoSPolicy
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

### StorageQoSPolicy
This cmdlet returns a **StorageQoSPolicy** object.
**StorageQoSPolicy**

## NOTES

## RELATED LINKS

[Get-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageQoSPolicy.md)

[New-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCStorageQoSPolicy.md)

[Remove-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCStorageQoSPolicy.md)

