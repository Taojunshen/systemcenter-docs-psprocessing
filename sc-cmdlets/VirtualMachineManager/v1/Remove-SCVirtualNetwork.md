---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualNetwork.md
schema: 2.0.0
ms.assetid: F0215E1E-D2EA-4DF9-9AA5-CEEE58C72BDF
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualNetwork

## SYNOPSIS
Removes a virtual network from a host managed by VMM.

## SYNTAX

### Host (Default)
```
Remove-SCVirtualNetwork [-VirtualNetwork] <VirtualNetwork> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Cluster
```
Remove-SCVirtualNetwork [-ClusterVirtualNetwork] <ClusterVirtualNetwork> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualNetwork** cmdlet removes one or more virtual network objects from Virtual Machine Manager (VMM).

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a specific virtual network from a host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $Network = Get-SCVirtualNetwork -VMHost $VMHost -Name "InternalVNet01"
PS C:\> Remove-SCVirtualNetwork -VirtualNetwork $Network -Confirm
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the virtual network object named InternalVNet01 configured on VMHost01 and stores the object in the $Network variable.

The last command removes InternalVNet01 from VMHost01, prompting you for confirmation before continuing the action.

## PARAMETERS

### -ClusterVirtualNetwork
Specifies a cluster virtual network object.

```yaml
Type: ClusterVirtualNetwork
Parameter Sets: Cluster
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -VirtualNetwork
Specifies a virtual network object.

```yaml
Type: VirtualNetwork
Parameter Sets: Host
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

## RELATED LINKS

[Get-SCVirtualNetwork](xref:VirtualMachineManager/v1/Get-SCVirtualNetwork.md)

[Get-SCVMHost](xref:VirtualMachineManager/v1/Get-SCVMHost.md)

[New-SCVirtualNetwork](xref:VirtualMachineManager/v1/New-SCVirtualNetwork.md)

[Repair-SCVirtualNetwork](xref:VirtualMachineManager/v1/Repair-SCVirtualNetwork.md)

[Set-SCVirtualNetwork](xref:VirtualMachineManager/v1/Set-SCVirtualNetwork.md)

