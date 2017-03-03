---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-help.xml
online version: 
schema: 2.0.0
ms.assetid: 0660A7E3-F1EB-4F54-9BA3-2EF86A2B67AC
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Use-SCDiscardSavedStateVM.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Use-SCDiscardSavedStateVM.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Use-SCDiscardSavedStateVM.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Use-SCDiscardSavedStateVM

## SYNOPSIS
Changes a virtual machine from the Saved state to the Stopped state.

## SYNTAX

```
Use-SCDiscardSavedStateVM [-VM] <VM> [-RunAsynchronously] [-JobVariable <String>] [-PROTipID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Use-SCDiscardSavedStateVM** cmdlet discards the Saved state of a virtual machine in the Saved state.
This cmdlet changes the virtual machine from the Saved state to the Stopped state.

## EXAMPLES

### Example 1: Move a virtual machine from Saved state to Stopped state
```
PS C:\> $Vm01 = Get-SCVirtualmachine -Name "VM01" 
PS C:\> Use-SCDiscardSavedStateVM -VM $Vm01
```

The first command gets the virtual machine named VM01 by using the **Get-SCVirtualMachine** cmdlet.
The virtual machine is in a saved state.
The command stores the virtual machine it in the $Vm01 variable.

The second command moves the virtual machine in $Vm01 to a stopped state.

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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
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

## NOTES

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

