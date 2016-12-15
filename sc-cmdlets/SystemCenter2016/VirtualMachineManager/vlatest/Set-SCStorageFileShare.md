---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageFileShare.md
schema: 2.0.0
ms.assetid: 18D185E5-ABAD-401D-9E01-093327987E6D
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageFileShare

## SYNOPSIS
Modifies a storage file share.

## SYNTAX

```
Set-SCStorageFileShare [-StorageClassification <StorageClassification>] [-StorageFileShare] <StorageFileShare>
 [-Description <String>] [-DedupMode <DedupMode>] [-IsAvailableForPlacement <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageFileShare** cmdlet modifies a storage file share.

## EXAMPLES

### Example 1: Update the storage classification for a storage file share
```
PS C:\>$FileShare = Get-SCStorageFileShare -Name "FileShare01"
PS C:\> $StorageClass = Get-SCStorageClassification -Name "StorageClassification02"
PS C:\> Set-SCStorageFileShare -StorageFileShare $FileShare -StorageClassification $StorageClass
```

The first command gets the storage file share object named FileShare01 and stores the object in the $FileShare variable.

The second command gets the storage classification object named StorageClassification02 and stores the object in the $StorageClass variable.

The last command changes the storage classification on FileShare01 to StorageClassification02.

## PARAMETERS

### -DedupMode
Apply deduplication on the volume or file share based on the workload.
The acceptable values for this parameter are:

- 0 - Disabled
- 1 - GeneralPurpose
- 2 - Hyper-V
- 3 - Backup

```yaml
Type: DedupMode
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, GeneralPurpose, HyperV, Backup, NotAvailable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage file share.

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

### -IsAvailableForPlacement


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

### -StorageFileShare
Specifies a storage file share.

```yaml
Type: StorageFileShare
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

## NOTES

## RELATED LINKS

[Get-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileShare.md)

[New-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFileShare.md)

[Register-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageFileShare.md)

[Remove-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFileShare.md)

[Repair-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCStorageFileShare.md)

[Unregister-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageFileShare.md)

