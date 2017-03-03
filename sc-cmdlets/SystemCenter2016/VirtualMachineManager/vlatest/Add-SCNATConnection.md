---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4D30796D-E0B4-4DD9-B8BA-56682E1CCD55
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNATConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNATConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNATConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCNATConnection

## SYNOPSIS
Adds a NAT connection.

## SYNTAX

### ByVMNetworkGateway (Default)
```
Add-SCNATConnection [-VMMServer <ServerConnection>] [-VMNetworkGateway] <VMNetworkGateway> [-Name <String>]
 [-Description <String>] [-MaximumBandwidthInboundKbps <UInt64>] [-MaximumBandwidthOutboundKbps <UInt64>]
 [-ExternalIPPool <StaticIPAddressPool>] [-ExternalIPAddress <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByVMNetwork
```
Add-SCNATConnection [-VMMServer <ServerConnection>] [-VMNetwork] <VMNetwork> [-Name <String>]
 [-Description <String>] [-MaximumBandwidthInboundKbps <UInt64>] [-MaximumBandwidthOutboundKbps <UInt64>]
 [-ExternalIPPool <StaticIPAddressPool>] [-ExternalIPAddress <String>] [-PublicIPAddress <AllocatedIPAddress>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCNATConnection** cmdlet adds a network address translation (NAT) connection.

## EXAMPLES

### Example1: Add NAT connection to a virtual machine network with external IP
```
PS C:\> $VmNetwork = Get-SCVMNetwork -Name "NAT_VmNetwork"
PS C:\> $IpPool = Get-SCStaticIPAddressPool -Name "Private_IPPool"
PS C:\> Add-SCNATConnection -Name "NatConnection" -VMNetwork $VmNetwork -ExternalIPPool $IpPool
```

The first command gets the virtual machine network by its name and stores it in the $VmNetwork variable.

The second command gets the IP Pool by its name from the logical network used for providing Private/Public VIPs and stores it in the $IpPool variable.

The third command adds the NAT connection with name NatConnection to the virtual machine network $VmNetwork with IP from $IpPool.

## PARAMETERS

### -Description
Specifies a description for the NAT connection.

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

### -ExternalIPAddress
Specifies an external IP address.

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

### -ExternalIPPool
Specifies an external IP pool.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

### -MaximumBandwidthInboundKbps
Specifies the maximum inbound bandwidth in kbps.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumBandwidthOutboundKbps
Specifies the maximum outbound bandwidth in kbps.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a network object.

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

### -PublicIPAddress
Specifies an allocated IP address object.

```yaml
Type: AllocatedIPAddress
Parameter Sets: ByVMNetwork
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

### -VMNetwork
Specifies a **VMNetwork** object.

```yaml
Type: VMNetwork
Parameter Sets: ByVMNetwork
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkGateway
Specifies a virtual machine network gateway object.

To obtain a **VMNetworkGateway** object, use the **Get-SCVMNetworkGateway** cmdlet.

```yaml
Type: VMNetworkGateway
Parameter Sets: ByVMNetworkGateway
Aliases: 

Required: True
Position: 0
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

[Get-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATConnection.md)

[Get-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetworkGateway.md)

[Remove-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNATConnection.md)

[Set-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNATConnection.md)

