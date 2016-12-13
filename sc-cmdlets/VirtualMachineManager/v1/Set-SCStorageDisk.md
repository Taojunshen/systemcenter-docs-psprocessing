---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageDisk.md
schema: 2.0.0
ms.assetid: CDDDB848-B297-4E74-A88F-CD89DB0DB330
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCStorageDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCStorageDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCStorageDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageDisk

## SYNOPSIS
Updates a storage disk object in the VMM database.

## SYNTAX

```
Set-SCStorageDisk -StorageDisk <StorageDisk> [-StorageClassification <StorageClassification>]
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageDisk** cmdlet updates a storage disk object in the Virtual Machine Manager (VMM) database.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

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
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageDisk
This cmdlet returns a **StorageDisk** object.

## NOTES

## RELATED LINKS

[Get-SCStorageDisk](xref:VirtualMachineManager/v1/Get-SCStorageDisk.md)

[Mount-SCStorageDisk](xref:VirtualMachineManager/v1/Mount-SCStorageDisk.md)

