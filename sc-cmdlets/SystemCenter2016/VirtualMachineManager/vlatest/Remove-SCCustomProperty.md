---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E66D74CA-CAAC-445D-A916-EF326BDAFC2F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomProperty.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomProperty.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomProperty.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCCustomProperty

## SYNOPSIS
Removes a custom property definition from the VMM database.

## SYNTAX

```
Remove-SCCustomProperty -CustomProperty <CustomProperty> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCCustomProperty** cmdlet removes a custom property definition from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Remove a custom property definition
```
PS C:\> $CustomProp = Get-SCCustomProperty -Name "Cost Center"
PS C:\> Remove-SCCustomProperty -CustomProperty $CustomProp
```

The first command gets the custom property object named Cost Center and stores the object in the $CustomProp variable.

The second command removes the custom property object stored in $CustomProp.

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

### -CustomProperty
Specifies a custom property object.

```yaml
Type: CustomProperty
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
This lets you audit of PRO tips.

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

## NOTES
* Requires a VMM custom property object, which can be retrieved by using the **Get-SCCustomProperty** cmdlet.

## RELATED LINKS

[Get-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomProperty.md)

[New-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCCustomProperty.md)

[Set-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomProperty.md)

