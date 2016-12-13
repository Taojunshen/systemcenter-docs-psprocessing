---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVirtualizationManager.md
schema: 2.0.0
ms.assetid: 333A8F00-8935-4583-A023-55126C6502B7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualizationManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualizationManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualizationManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualizationManager

## SYNOPSIS
Removes a VMware vCenter Server from VMM.

## SYNTAX

```
Remove-SCVirtualizationManager [-VirtualizationManager] <VirtualizationManager> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualizationManager** cmdlet removes one or more VMware vCenter Server objects from Virtual Machine Manager (VMM).
This cmdlet deletes the vCenter Server object from the VMM database and also removes all imported ESX host objects and virtual machine objects associated with the vCenter Server.

When you remove a VirtualCenter Server, the cmdlet does not make any changes within the vCenter Server and does not remove any hosts or virtual machines from the vCenter Server.

## EXAMPLES

### Example 1: Remove a VMware vCenter Server from VMM
```
PS C:\>$VirtMgrServer = Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com" -ComputerName "VirtMgrServer01.Contoso.com"
PS C:\> Remove-SCVirtualizationManager -VirtualizationManager $VirtMgrServer
```

The first command gets the virtualization manager object named VirtMgrServer01 from VMMServer01 and stores the object in the $VirtMgrServer variable.

The second command removes the vCenter Server object, as well as all associated host and virtual machine objects, from VMM.

### Example 2: Remove a set of VMware vCenter Servers from VMM
```
PS C:\> $VirtManagers = Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "Server" }
PS C:\> ForEach ($VirtManager in $VirtManagers) {Remove-SCVirtualizationManager -VirtualizationManager $VirtManager}
```

The first command gets all virtualization manager objects whose name includes the string "Server" and stores the objects in $VirtManagers.

The second command removes each object in $VirtManagers from VMM, as well as all associated host and virtual machine objects.

For more information about the standard Windows PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

### Example 3: Remove all VMware vCenter Servers from VMM
```
PS C:\>Get-SCVirtualizationManager | Remove-SCVirtualizationManager -RunAsynchronously
```

This command removes all virtualization manager objects from VMM.

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

### -VirtualizationManager
Specifies a virtualization manager object managed by VMM.

```yaml
Type: VirtualizationManager
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
* Requires a VMM virtualization manager object, which can be retrieved by using the Get-SCVirtualizationManager cmdlet.

## RELATED LINKS

[Add-SCVirtualizationManager](xref:VirtualMachineManager/v1/Add-SCVirtualizationManager.md)

[Get-SCVirtualizationManager](xref:VirtualMachineManager/v1/Get-SCVirtualizationManager.md)

[Read-SCVirtualizationManager](xref:VirtualMachineManager/v1/Read-SCVirtualizationManager.md)

[Set-SCVirtualizationManager](xref:VirtualMachineManager/v1/Set-SCVirtualizationManager.md)

