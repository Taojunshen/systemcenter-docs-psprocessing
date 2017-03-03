---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D21D8EC6-9CCC-49A7-9AAD-4616D2FDBE00
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCodeIntegrityPolicy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCodeIntegrityPolicy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCodeIntegrityPolicy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCCodeIntegrityPolicy

## SYNOPSIS
Removes a code integrity policy.

## SYNTAX

```
Remove-SCCodeIntegrityPolicy -CodeIntegrityPolicy <CodeIntegrityPolicy> [-Force] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCCodeIntegrityPolicy** cmdlet removes a code integrity policy from Virtual Machine Manager (VMM).

## EXAMPLES


## PARAMETERS

### -CodeIntegrityPolicy
Specifies the code integrity policy to remove.

```yaml
Type: CodeIntegrityPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCCodeIntegrityPolicy](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCodeIntegrityPolicy.md)

[New-SCCodeIntegrityPolicy](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCCodeIntegrityPolicy.md)

[Set-SCCodeIntegrityPolicy](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCodeIntegrityPolicy.md)

