---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 03001DBD-72D7-41F2-A685-B97E80E954E8
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitchVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitchVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitchVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCLogicalSwitchVirtualNetworkAdapter

## SYNOPSIS
Removes a virtual network adapter (VNIC) from a logical switch.

## SYNTAX

```
Remove-SCLogicalSwitchVirtualNetworkAdapter [-VMMServer <ServerConnection>]
 [-LogicalSwitchVirtualNetworkAdapter] <LogicalSwitchVirtualNetworkAdapter> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLogicalSwitchVirtualNetworkAdapter** cmdlet removes a virtual network adapter that was added to the Uplink Port Profile as part of a logical switch definition.

## EXAMPLES

### Example 1: Delete a logical switch virtual network adapter
```
PS C:\> $HostVNicVarToRemove = Get-SCLogicalSwitchVirtualNetworkAdapter -ID "6615c2c2-4eaa-4f75-be3e-bbdb8cb25ca1"
PS C:\> Remove-SCLogicalSwitchVirtualNetworkAdapter -LogicalSwitchVirtualNetworkAdapter $HostVNicVarToRemove
```

The first command gets a logical switch virtual network adapter by using the **Get-SCLogicalSwitchVirtualNetworkAdapter** cmdlet, and then stores it in the $HostVNicVarToRemove variable.

The second command removes the virtual network adapter.
It is no longer deployed with the logical switch.

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

### -LogicalSwitchVirtualNetworkAdapter
The virtual network adapter to remove.

```yaml
Type: LogicalSwitchVirtualNetworkAdapter
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
Specifies a Virtual Machine Manager (VMM) server object.

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

[Get-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitchVirtualNetworkAdapter.md)

[New-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitchVirtualNetworkAdapter.md)

[Set-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitchVirtualNetworkAdapter.md)

