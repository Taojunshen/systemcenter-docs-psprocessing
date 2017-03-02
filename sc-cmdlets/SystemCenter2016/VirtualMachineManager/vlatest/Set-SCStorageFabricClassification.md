---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A49B2839-FC27-4272-AD9B-80A8B3D81325
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabricClassification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabricClassification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabricClassification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCStorageFabricClassification

## SYNOPSIS
Modifies a Fibre Channel fabric classification.

## SYNTAX

```
Set-SCStorageFabricClassification [-StorageFabricClassification] <StorageFabricClassification> [-Name <String>]
 [-Description <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageFabricClassification** cmdlet modifies a Fibre Channel fabric classification.

## EXAMPLES

### Example 1: Modify a storage fabric classification
```
PS C:\> $Classification = Get-SCStorageFabricClassification -Name "PROD"
PS C:\> Set-SCStorageFabricClassification -StorageFabricClassification $Classification -Name "NewName" -Description "Description"
```

The first command gets the storage classification object named PROD, and then stores it in the $Classification variable.

The second command applies a new name and a description to the classification object stored in $Classification.

## PARAMETERS

### -Description
Specifies a description for the Fibre Channel fabric classification.

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
Specifies the name of the new Fibre Channel fabric classification that this cmdlet modifies.

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

### -StorageFabricClassification
Specifies a classification for storage Fibre Channel fabric that this cmdlet modifies.

```yaml
Type: StorageFabricClassification
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

### StorageFabricClassification
This cmdlet returns a **StorageFabricClassification** object.

## NOTES

## RELATED LINKS

[Get-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFabricClassification.md)

[New-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFabricClassification.md)

[Remove-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFabricClassification.md)

