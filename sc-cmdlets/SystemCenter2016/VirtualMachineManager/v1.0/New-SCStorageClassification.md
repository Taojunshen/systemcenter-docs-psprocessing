---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageClassification.md
schema: 2.0.0
ms.assetid: 17BC3968-1DD0-4773-969E-46FCACBF7E7E
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageClassification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageClassification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageClassification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageClassification

## SYNOPSIS
Creates a storage classification.

## SYNTAX

```
New-SCStorageClassification [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageClassification** cmdlet creates a storage classification.
A storage classification defines the capabilities of a storage pool.
For example, a classification of Gold could be associated with storage pools that have the highest performance and availability.

For information about associating a storage classification with a storage pool, see the  Set-SCStoragePool cmdlet.

## EXAMPLES

### Example 1: Create a storage classification
```
PS C:\>$Class = New-SCStorageClassification -Name "StorageClassification01" -Description "New storage classification"
```

This command creates a storage classification named StorageClassification01, and then stores it in the $Class variable.

## PARAMETERS

### -Description
Specifies a description for the storage classification.

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
Specifies the name of a variable in which job progress is tracked and stored.

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
Specifies the name of the storage classification.

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

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### StorageClassficiation
This cmdlet returns a **StorageClassficiation** object.

## NOTES

## RELATED LINKS

[Get-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageClassification.md)

[Remove-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageClassification.md)

[Set-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageClassification.md)

[Set-SCStoragePool](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStoragePool.md)

