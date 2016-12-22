---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B13035EA-5B51-42AE-8840-39A530301D17
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageClassification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageClassification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageClassification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageClassification

## SYNOPSIS
Modifies the properties of an existing storage classification.

## SYNTAX

```
Set-SCStorageClassification [-StorageClassification] <StorageClassification> [-Name <String>]
 [-Description <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageClassification** cmdlet modifies the properties of an existing storage classification.

## EXAMPLES

### Example 1: Update the name of a storage classification
```
PS C:\> $Class = @(Get-SCStorageClassification)[0]
PS C:\> Set-SCStorageClassification -StorageClassification $Class -Name "Tier2"
```

The first command gets the first item in the storage classification array, and then stores it in the $Class variable.

The second command changes the name of the storage classification stored in $Class to Tier2.

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

### StorageClassficiation
This cmdlet returns a **StorageClassficiation** object.

## NOTES

## RELATED LINKS

[Get-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageClassification.md)

[New-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageClassification.md)

[Remove-SCStorageClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageClassification.md)

