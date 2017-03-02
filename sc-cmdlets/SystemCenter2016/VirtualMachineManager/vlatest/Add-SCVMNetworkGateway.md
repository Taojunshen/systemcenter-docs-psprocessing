---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7FFC7990-ABB2-4E3B-AF1A-170371542D49
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMNetworkGateway.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMNetworkGateway.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMNetworkGateway.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCVMNetworkGateway

## SYNOPSIS
Adds a virtual machine network gateway to VMM.

## SYNTAX

### Default (Default)
```
Add-SCVMNetworkGateway [-VMMServer <ServerConnection>] -VMNetwork <VMNetwork> [-RequiresVPN] [-RequiresNAT]
 [-EnableBGP <Boolean>] [-AutonomousSystemNumber <UInt32>] -Name <String> [-Description <String>]
 [-RoutingIPSubnet <String>] [-FabricRole <FabricRole>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByGateway
```
Add-SCVMNetworkGateway [-VMMServer <ServerConnection>] -VMNetwork <VMNetwork>
 -NetworkGateway <NetworkServiceBase> [-EnableBGP <Boolean>] [-AutonomousSystemNumber <UInt32>] -Name <String>
 [-Description <String>] [-RoutingIPSubnet <String>] [-FabricRole <FabricRole>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVMNetworkGateway** cmdlet adds a virtual machine network gateway to Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Create a virtual machine network gateway
```
PS C:\> $ContosoNetworkGateway = Get-SCNetworkGateway -Name "ContosoNetworkGateway"
PS C:\> $VmNetworkGateway = Add-SCVMNetworkGateway -Name "VMNetworkGateway" -EnableBGP $True -NetworkGateway $ContosoNetworkGateway -VMNetwork $VmNetwork -AutonomousSystemNumber "1000" -RoutingIPSubnet "10.251.251.0/29"
```

The first command gets a network gateway named ContosoNetworkGateway, and then stores it in the $ContosoNetworkGateway variable.

The second command creates a virtual machine network gateway for the gateway in $ContosoNetworkGateway.

## PARAMETERS

### -AutonomousSystemNumber
Specifies an Autonomous System Number (ASN).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the virtual machine network gateway.

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

### -EnableBGP
Indicates whether Border Gateway Protocol (BGP) is enabled.

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

### -FabricRole
Specifies a fabric role.

```yaml
Type: FabricRole
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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkGateway
Specifies a network gateway object.

To obtain a network gateway object, use the **Get-SCNetworkGateway** cmdlet.

```yaml
Type: NetworkServiceBase
Parameter Sets: ByGateway
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### -RequiresNAT
Indicates that the connection requires network address translation (NAT).

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiresVPN
Indicates that a virtual private network (VPN) is required.

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingIPSubnet
Specifies a routing IP subnet for a virtual machine network gateway.

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

### -VMNetwork
Specifies a virtual machine network object.

To get a virtual machine network object, use the **Get-SCVMNetwork** cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetworkGateway.md)

[Read-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMNetworkGateway.md)

[Remove-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMNetworkGateway.md)

[Set-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMNetworkGateway.md)

