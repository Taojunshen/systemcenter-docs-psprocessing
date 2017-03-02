---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-help.xml
online version: 
schema: 2.0.0
ms.assetid: 4B7F4138-2F7A-4D5F-80B8-41EF05A2C1AA
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Use-SCSaveStateVM.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Use-SCSaveStateVM.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Use-SCSaveStateVM.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Use-SCSaveStateVM

## SYNOPSIS
Changes a virtual machine from the Running state to the Saved state.

## SYNTAX

```
Use-SCSaveStateVM [-VM] <VM> [-RunAsynchronously] [-JobVariable <String>] [-PROTipID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Use-SCSaveStateVM** cmdlet changes a virtual machine from the Running state to the Saved state in System Center 2016 Virtual Machine Manager.

## EXAMPLES

### Example 1: Move a virtual machine from Running to Saved state
```
PS C:\> $VM01 = Get-SCVirtualmachine -Name "ConotosVM01" 
PS C:\> Use-SCSaveStateVM -VM $VM01
```

The first command gets the virtual machine named testvm1, and then stores it in the $VM01 variable.
The virtual machine is in the Running state.

The second command moves the virtual machine in $VM01 to the Saved state.

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

