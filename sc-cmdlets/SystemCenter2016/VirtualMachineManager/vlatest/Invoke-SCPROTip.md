---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3CE41488-5814-4780-8D82-7F157E4591EC
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Invoke-SCPROTip

## SYNOPSIS
Performs the action recommended by a PRO tip.

## SYNTAX

```
Invoke-SCPROTip [-PROTip] <PROTip> [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-SCPROTip** cmdlet performs the action recommended by a Performance and Resource Optimization (PRO) tip.
You can use this cmdlet to manually invoke the action recommended by a PRO tip that is not set to be implemented automatically.

## EXAMPLES

### Example 1: Invoke the first active PRO tip
```
PS C:\> $PROTips = Get-SCPROTip
PS C:\> Invoke-SCPROTip -PROTip $PROTips[0]
```

The first command gets all active PRO tip objects from the VMM database and stores the objects in the $PROTips object array.

The second command implements the suggested action for the first PRO tip stored in $PROTips (designated by the \[0\]).

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

[Clear-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md)

[Get-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md)

[Set-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md)

[Test-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md)

