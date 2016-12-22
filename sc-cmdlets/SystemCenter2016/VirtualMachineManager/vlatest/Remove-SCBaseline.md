---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E95D038A-F2D2-45E5-885F-D3EEA55DD4AF
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCBaseline.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCBaseline.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCBaseline.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCBaseline

## SYNOPSIS
Removes a baseline from VMM.

## SYNTAX

```
Remove-SCBaseline [-VMMServer <ServerConnection>] [-Baseline] <Baseline> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCBaseline** cmdlet removes a baseline and its scope assignments from Virtual Machine Manager (VMM).
Compliance is no longer graded for this baseline.

For more information about baselines, type `Get-Help New-SCBaseline`.

## EXAMPLES

### Example 1: Remove a baseline
```
PS C:\> $Baseline = Get-SCBaseline -Name "Security Baseline"
PS C:\> Remove-SCBaseline -Baseline $Baseline
```

The first command gets the baseline object named Security Baseline and stores the object in the $Baseline variable.

The second command removes the baseline stored in $Baseline (Security Baseline).

## PARAMETERS

### -Baseline
Specifies a VMM baseline object.

```yaml
Type: Baseline
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### Baseline
This cmdlet returns a **Baseline** object.

## NOTES

## RELATED LINKS

[Get-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCBaseline.md)

[New-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCBaseline.md)

[Set-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCBaseline.md)

