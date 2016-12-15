---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMTemplate.md
schema: 2.0.0
ms.assetid: 22C6EBAF-CAB7-402C-957C-4B4A076D4673
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMTemplate

## SYNOPSIS
Removes a template object from VMM.

## SYNTAX

```
Remove-SCVMTemplate [-VMTemplate] <Template> [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMTemplate** cmdlet removes a template object from the Virtual Machine Manager (VMM) library.
Removing a template object does not delete any virtual hard disks associated with the template.

The types of files that can be associated with a template include virtual hard disk files (Windows-based .vhd files, Citrix XenServer-based .vhd files, or VMware-based .vmdk files), virtual floppy disk files (Windows-based .vfd files or VMware-based .flp files), and script files (Windows PowerShell .ps1 script files or answer file scripts, including Sysprep.inf and Unattend.xml files).

This cmdlet returns the object upon success (with the property MarkedForDeletion set to TRUE) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a specific template from the library
```
PS C:\>$Template = Get-SCVMTemplate -VMMServer "VMMServer1.Contoso.com" | where { $_.Name -eq "Template01" }
PS C:\> Remove-SCVMTemplate -VMTemplate $Template
```

The first command gets the template object named Template01 from the library on VMMServer01 and stores the object in the $Template variable.

The second command removes the template object stored in $Template from the library.

### Example 2: Remove all templates from the library
```
PS C:\>$Templates = Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com"
PS C:\> $Templates | Remove-SCVMTemplate -Confirm
```

The first command gets all the template objects from VMMServer01 and stores the objects in the array named $Templates.

The second command passes each template object in $Templates to the **Remove-SCVMTemplate** cmdlet, which removes each template object from the VMM library.
The *Confirm* parameter prompts you to confirm whether you want to delete each template.

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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: (All)
Aliases: Template

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

### SCVMTemplate
This cmdlet returns an **SCVMTemplate** object.

## NOTES
* Requires a VMM template object, which can be retrieved by using the Get-SCVMTemplate cmdlet.

## RELATED LINKS

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[New-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMTemplate.md)

[Set-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMTemplate.md)

