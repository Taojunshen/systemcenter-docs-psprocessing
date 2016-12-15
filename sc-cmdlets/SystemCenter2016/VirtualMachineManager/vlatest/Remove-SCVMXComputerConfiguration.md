---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMXComputerConfiguration.md
schema: 2.0.0
ms.assetid: 3A2D40FB-5C0D-4F10-8723-32E54D5CA040
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMXComputerConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMXComputerConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMXComputerConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMXComputerConfiguration

## SYNOPSIS
Removes a VMX computer configuration object from VMM.

## SYNTAX

```
Remove-SCVMXComputerConfiguration [-VMXComputerConfiguration] <VmxMachineConfiguration> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMXComputerConfiguration** cmdlet removes one or more VMX computer configuration objects from the Virtual Machine Manager (VMM) database.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove all VMX computer configurations without being prompted to confirm each deletion
```
PS C:\>$VMXComputerConfigs = Get-SCVMXComputerConfiguration -VMMServer "VMMServer01.Contoso.com"
PS C:\> $VMXComputerConfigs | Remove-SCVMXComputerConfiguration
```

The first command retrieves all VMX computer configuration objects from the VMM database on VMMServer01 and stores these objects in the $VMXComputerConfigs object array.

The second command passes each object in $VMXComputerConfigs to **Remove-VMXComputerConfiguration**, which removes each VMX computer configuration object.

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

### -VMXComputerConfiguration
Specifies a VMX computer configuration object.

```yaml
Type: VmxMachineConfiguration
Parameter Sets: (All)
Aliases: MachineConfig, VMXMachineConfig

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
* Requires a VMM VMX computer configuration object, which can be retrieved by using the Get-SCVMXComputerConfiguration cmdlet.

## RELATED LINKS

[Get-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMXComputerConfiguration.md)

[New-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md)

