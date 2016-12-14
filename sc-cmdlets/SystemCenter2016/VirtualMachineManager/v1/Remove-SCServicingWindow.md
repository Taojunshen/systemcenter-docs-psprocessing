---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServicingWindow.md
schema: 2.0.0
ms.assetid: E32FCF27-AD5B-495D-8846-FB1B107C3287
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCServicingWindow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCServicingWindow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCServicingWindow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCServicingWindow

## SYNOPSIS
Removes a servicing window definition from VMM.

## SYNTAX

```
Remove-SCServicingWindow [-ServicingWindow] <ServicingWindow> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCServicingWindow** cmdlet removes a servicing window definition from Virtual Machine Manager (VMM).
If the servicing window is assigned to a virtual machine, a host, or a service, the association is also removed.

## EXAMPLES

### Example 1: Remove a servicing window
```
PS C:\>$SvcWindow = Get-SCServicingWindow -Name "Backup Staging A"
PS C:\> Remove-SCServicingWindow -ServicingWindow $SvcWindow -Confirm
```

The first command gets the servicing window object named Backup Staging A and stores the object in the $SvcWindow variable.

The second command removes the servicing window stored in $SvcWindow (Backup Staging A).

Important: All objects subscribing to this service window will lose their subscription.

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

### -ServicingWindow
Specifies a servicing window object.

```yaml
Type: ServicingWindow
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

## NOTES
* Requires a VMM servicing window object, which you can get with the Get-SCServicingWindow cmdlet.

## RELATED LINKS

[Get-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCServicingWindow.md)

[New-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCServicingWindow.md)

[Set-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCServicingWindow.md)

