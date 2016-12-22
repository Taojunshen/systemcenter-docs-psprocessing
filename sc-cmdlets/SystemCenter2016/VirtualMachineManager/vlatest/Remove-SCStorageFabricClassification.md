---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 19A64B10-FC6E-43A2-8922-2B93A9CC92A3
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFabricClassification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFabricClassification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFabricClassification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCStorageFabricClassification

## SYNOPSIS
Removes a Fibre Channel fabric classification from VMM.

## SYNTAX

```
Remove-SCStorageFabricClassification [-StorageFabricClassification] <StorageFabricClassification>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCStorageFabricClassification** cmdlet removes a Fibre Channel fabric classification from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove a storage fabric classification
```
PS C:\> Get-SCStorageFabricClassification -Name "PROD" | Remove-SCStorageFabricClassification
```

This example gets the storage fabric classification object named PROD and uses the pipeline operator to pass the object to the current cmdlet.
This cmdlet removes the classification from VMM.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Specifies a classification for storage Fibre Channel fabric that this cmdlet removes from VMM.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Set-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabricClassification.md)

