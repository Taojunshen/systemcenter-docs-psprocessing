---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-PROTip.md
schema: 2.0.0
ms.assetid: 3CE41488-5814-4780-8D82-7F157E4591EC
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Invoke-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Invoke-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Invoke-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
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
PS C:\>$PROTips = Get-SCPROTip
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

[Add-PROTip](xref:VirtualMachineManager/v1/Add-PROTip.md)

[Clear-SCPROTip](xref:VirtualMachineManager/v1/Clear-SCPROTip.md)

[Get-SCPROTip](xref:VirtualMachineManager/v1/Get-SCPROTip.md)

[Set-SCPROTip](xref:VirtualMachineManager/v1/Set-SCPROTip.md)

[Test-SCPROTip](xref:VirtualMachineManager/v1/Test-SCPROTip.md)

