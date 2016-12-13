---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-PROTip.md
schema: 2.0.0
ms.assetid: DAFF2B65-5ACA-4B05-9C05-0B44B7A2180A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Clear-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Clear-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Clear-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
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
PS C:\>$PROTips = Get-SCPROTip
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

[Add-PROTip](xref:VirtualMachineManager/v1/Add-PROTip.md)

[Get-SCPROTip](xref:VirtualMachineManager/v1/Get-SCPROTip.md)

[Invoke-SCPROTip](xref:VirtualMachineManager/v1/Invoke-SCPROTip.md)

[Set-SCPROTip](xref:VirtualMachineManager/v1/Set-SCPROTip.md)

[Test-SCPROTip](xref:VirtualMachineManager/v1/Test-SCPROTip.md)

