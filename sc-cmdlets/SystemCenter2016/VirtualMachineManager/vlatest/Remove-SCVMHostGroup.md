---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 815EA9F6-CE65-4968-A684-7198D8A94F72
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMHostGroup

## SYNOPSIS
Removes a host group from VMM.

## SYNTAX

```
Remove-SCVMHostGroup [-VMHostGroup] <HostGroup> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMHostGroup** cmdlet removes one or more host group objects from the Virtual Machine Manager (VMM) database.
A host group cannot be deleted if it is associated with a private cloud, if it has hosts assigned to it, or if its child host group has hosts assigned to it.
This cmdlet will delete child host groups if the host group and its child host groups do not contain any virtual machine hosts.

This cmdlet returns the object upon success (with the MarkedForDeletion property set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove the specified host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "HostGroup02"
PS C:\> Remove-SCVMHostGroup -VMHostGroup $HostGroup
```

The first command gets the host group named HostGroup02 and stores it in the $HostGroup variable.

The second command removes the host group object stored in the $HostGroup variable.

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

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
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
* Requires a VMM host group object, which can be retrieved by using the **Get-SCVMHostGroup** cmdlet.

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Move-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostGroup.md)

[New-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostGroup.md)

[Set-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md)

