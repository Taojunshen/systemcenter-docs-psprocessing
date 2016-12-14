---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-help.xml
online version: 4776c225-8a45-4453-847d-e4f16a57a44e
schema: 2.0.0
ms.assetid: EB08DC8E-50BA-45D3-9ED4-7B10F886774E
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Use-SCStopVM.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Use-SCStopVM.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Use-SCStopVM.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Use-SCStopVM

## SYNOPSIS
Changes a virtual machine from its current state to the Stopped state.

## SYNTAX

```
Use-SCStopVM [-VM] <VM> [-RunAsynchronously] [-JobVariable <String>] [-PROTipID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Use-SCStopVM** cmdlet shuts down a virtual machine in System Center 2016 Virtual Machine Manager.
This cmdlet changes the virtual machine to the Stopped state regardless of the current state.

## EXAMPLES

### Example 1: Move a virtual machine to the Stopped state
```
PS C:\>$VM01 = Get-SCVirtualmachine -Name "ContosoVM01"
PS C:\> Use-SCStopVM -VM $VM01
```

The first command gets the virtual machine named ContosoVM01, and then stores it in the $VM01 variable.
The virtual machine could be in any state.

The second command moves the virtual machine in $VM01 to the Stopped state.

## PARAMETERS

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

