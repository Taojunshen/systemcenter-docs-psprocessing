---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DAFF2B65-5ACA-4B05-9C05-0B44B7A2180A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Clear-SCPROTip

## SYNOPSIS
Dismisses a PRO tip object that is no longer applicable.

## SYNTAX

```
Clear-SCPROTip [-PROTip] <PROTip> [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-SCPROTip** cmdlet dismisses a Performance and Resource Optimization (PRO) tip object that is no longer applicable.
You can use this cmdlet to dismiss a PRO tip if, for example, its recommended action is no longer valid or is out-of-date.

Virtual Machine Manager (VMM) dismisses some PRO tips automatically if the condition that generated the alert, and the resulting PRO tip recommended action, is no longer an issue.

## EXAMPLES

### Example 1: Dismiss the first active PRO tip
```
PS C:\> $PROTips = Get-SCPROTip
PS C:\> Clear-SCPROTip -PROTip $PROTips[0]
```

The first command gets all active PRO tip objects from the VMM database and stores the objects in the $PROTips object array.

The last command dismisses the first tip stored in $PROTips.

## PARAMETERS

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

### -PROTip
Specifies a PRO tip object.

```yaml
Type: PROTip
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PROTip
This cmdlet returns a **PROTip** object.

## NOTES

## RELATED LINKS

[Add-PROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md)

[Get-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md)

[Invoke-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md)

[Set-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md)

[Test-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md)

