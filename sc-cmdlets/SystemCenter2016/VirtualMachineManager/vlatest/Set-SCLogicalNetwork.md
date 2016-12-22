---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4CFFF8C4-1241-45F8-A2BE-FD7D9C211E0E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLogicalNetwork

## SYNOPSIS
Changes the properties of a logical network object.

## SYNTAX

### SetDefaultNetworkManager (Default)
```
Set-SCLogicalNetwork [-VMNetworkCreationDefaultNetworkManager <VirtualSwitchExtensionManager>]
 [-VMMServer <ServerConnection>] [-LogicalNetwork] <LogicalNetwork> [-Name <String>] [-Description <String>]
 [-EnableNetworkVirtualization <Boolean>] [-UseGRE <Boolean>] [-LogicalNetworkDefinitionIsolation <Boolean>]
 [-AllowDynamicVlanOnVnic <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### RemoveDefaultNetworkManager
```
Set-SCLogicalNetwork [-VMMServer <ServerConnection>] [-LogicalNetwork] <LogicalNetwork> [-Name <String>]
 [-Description <String>] [-EnableNetworkVirtualization <Boolean>] [-UseGRE <Boolean>]
 [-LogicalNetworkDefinitionIsolation <Boolean>] [-AllowDynamicVlanOnVnic <Boolean>]
 [-RemoveVMNetworkCreationDefaultNetworkManager] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLogicalNetwork** cmdlet changes the properties of a Virtual Machine Manager (VMM) logical network object.
Properties that you can update include the name and description of the logical network.

## EXAMPLES

### Example 1: Change the name of a logical network
```
PS C:\> $LogicalNetwork = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> Set-SCLogicalNetwork -LogicalNetwork $LogicalNetwork -Name "LogicalNetwork02"
```

The first command gets the logical network object named LogicalNetwork01 and stores the object in the $LogicalNetwork variable.

The second command changes the name of the logical network stored in $LogicalNetwork to "LogicalNetwork02".

## PARAMETERS

### -AllowDynamicVlanOnVnic
Specifies whether this vNIC is configured for Dynamic VLAN.
VMM does not expect a VLAN for this adapter.

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
Position: Named
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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and virtual local area networks (VLANs) that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogicalNetworkDefinitionIsolation
Indicates whether logical network definition isolation is enabled.

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

### -RemoveVMNetworkCreationDefaultNetworkManager
Indicates that the VM Network default network manager is removed.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveDefaultNetworkManager
Aliases: 

Required: True
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
Indicates whether network virtualization Generic Routing Encapsulation (GRE) is used.
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

### -VMNetworkCreationDefaultNetworkManager
Specifies a virtual switch extension manager object.

```yaml
Type: VirtualSwitchExtensionManager
Parameter Sets: SetDefaultNetworkManager
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LogicalNetwork
This cmdlet returns a **LogicalNetwork** object.

## NOTES
* Requires a VMM logical network object, which can be retrieved by using the **Get-SCLogicalNetwork** cmdlet.

## RELATED LINKS

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md)

[New-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetwork.md)

[Remove-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalNetwork.md)

