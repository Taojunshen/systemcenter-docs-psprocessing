---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCFabricRole.md
schema: 2.0.0
ms.assetid: 2B55C758-20E0-43CE-A585-2D33341F7B6F
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerRoleConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerRoleConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerRoleConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerRoleConfiguration

## SYNOPSIS
Creates a load balancer role configuration.

## SYNTAX

```
New-SCLoadBalancerRoleConfiguration [-VMMServer <ServerConnection>] -LBManagerIPAddress <String>
 [-NatIPExemptions <System.Collections.Generic.List`1[System.String]>]
 [-VipPools <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StaticIPAddressPool]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerRoleConfiguration** cmdlet creates a load balancer role configuration in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Create a load balancer role configuration
```
PS C:\>$IpPool1 = Get-SCStaticIPAddressPool -Name "Private VIP Logical Network"
PS C:\> $IpPool2 = Get-SCStaticIPAddressPool -Name "Public VIP Logical Network"
PS C:\> $NetworkService = Get-SCNetworkService -Name "NC"
PS C:\> $FabricRole =  Get-SCFabricRole -Type LoadBalancer -NetworkService $NetworkService 
PS C:\> $NatIPExemptions = @() 
PS C:\> $FabricRoleConfiguration = New-SCLoadBalancerRoleConfiguration -LBManagerIPAddress "10.20.20.254" -NatIPExemptions $NatIPExemptions -VipPools @($IpPool1, $IpPool2)
```

The first two commands get IP pools from the private and public VIP logical networks by using the Get-SCStaticIPAddressPool cmdlet.

The third command gets the network service named NC by using the Get-SCNetworkService cmdlet.

The fourth command gets the load balancer fabric role from the network service by using the Get-SCFabricRole cmdlet.

The fifth command creates an array variable named $NatIPExemptions.

The final command creates a load balancer configuration object that has the SLBM VIP address 10.20.20.254 and the VIP pools.

## PARAMETERS

### -LBManagerIPAddress
Specifies the load balancer manager virtual IP address.

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

### -NatIPExemptions
Specifies the **NatIPExempltions** subnets list.

```yaml
Type: System.Collections.Generic.List`1[System.String]
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

### -VipPools
Specifies the list of VIP pools that are published to the load balancer manager.
The VIP pools are used for NAT and load balancing.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.StaticIPAddressPool]
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Get-SCFabricRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCFabricRole.md)

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkService.md)

[Get-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStaticIPAddressPool.md)

