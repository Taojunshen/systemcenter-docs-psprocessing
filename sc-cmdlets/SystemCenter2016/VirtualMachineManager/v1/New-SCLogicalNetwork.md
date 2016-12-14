---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalNetwork.md
schema: 2.0.0
ms.assetid: 01C95931-4225-4343-92A6-1CBE52B5B6A0
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCLogicalNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCLogicalNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCLogicalNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLogicalNetwork

## SYNOPSIS
Creates a logical network object.

## SYNTAX

```
New-SCLogicalNetwork [-NetworkController <VirtualSwitchExtensionManager>] [-VMMServer <ServerConnection>]
 [-Name] <String> [[-Description] <String>] [-EnableNetworkVirtualization <Boolean>] [-UseGRE <Boolean>]
 [-IsPVLAN <Boolean>] [-LogicalNetworkDefinitionIsolation <Boolean>] [-PublicIPNetwork]
 [-AllowDynamicVlanOnVnic <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLogicalNetwork** cmdlet creates a logical network object for a Virtual Machine Manager (VMM).
Each logical network must have a unique name within a VMM installation.

Logical networks enable network administrators to model a network by grouping subnets and virtual local area networks (VLANs) based on categories that align to business needs.
To assign IP subnets and VLANs to a logical network, create a logical network definition by using the New-SCLogicalNetworkDefinition cmdlet.

## EXAMPLES

### Example 1: Create a logical network
```
PS C:\>New-SCLogicalNetwork -Name "LogicalNetwork01"
```

This command creates a logical network named LogicalNetwork01.

### Example 2: Create a network virtualization-enabled logical network
```
PS C:\>New-SCLogicalNetwork -Name "LogicalNetwork02" -EnableNetworkVirtualization $True -UseGRE $True
```

This command creates a logical network named LogicalNetwork02 that is enabled for network virtualization and implements Generic Routing Encapsulation (GRE).

## PARAMETERS

### -AllowDynamicVlanOnVnic
Specifies that this vNIC is configured for Dynamic VLAN.
VMM does not expect a VLAN for this network adapter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the logical network object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNetworkVirtualization
Indicates whether network virtualization is enabled.
The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPVLAN
Indicates whether the logical network is a Private Virtual LAN (PVLAN).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies the name of a variable in which job progress is tracked and stored.

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

### -LogicalNetworkDefinitionIsolation
Indicates whether to enable network isolation for the logical network definition.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkController
Specifies a network controller.

```yaml
Type: VirtualSwitchExtensionManager
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

### -PublicIPNetwork
Specifies if a Network Controller managed network is meant for Public IPs.

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

### -UseGRE
Indicates whether to use network virtualization with Generic Routing Encapsulation (GRE).
The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LogicalNetwork
This cmdlet returns a **LogicalNetwork** object.

## NOTES

## RELATED LINKS

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalNetwork.md)

[New-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCLogicalNetworkDefinition.md)

[Remove-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCLogicalNetwork.md)

[Set-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCLogicalNetwork.md)

