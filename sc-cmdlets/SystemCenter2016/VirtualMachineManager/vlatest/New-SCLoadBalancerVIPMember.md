---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1877BA87-A3AC-4972-8FF4-9545EEBA4244
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPMember.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPMember.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPMember.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCLoadBalancerVIPMember

## SYNOPSIS
Adds a virtual machine to a load balancer VIP.

## SYNTAX

```
New-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>] -LoadBalancerVIP <LoadBalancerVIP>
 -IPAddress <String> [-Name <String>] -Port <UInt16> -VirtualNetworkAdapter <VirtualNetworkAdapter>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerVIPMember** cmdlet adds a virtual machine to a load balancer virtual IP (VIP).

## EXAMPLES

### Example 1: Add a virtual machine to a load balancer virtual IP
```
PS C:\> $VM = Get-VM -Name "VM01" -VMHost "VMHost01.Contoso.com" 
PS C:\> $VNIC = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> $LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> $VIP = Get-SCLoadBalancerVIP -LoadBalancer $LoadBalancer -IPAddress "10.0.0.1"
PS C:\> New-SCLoadBalancerVIPMember -LoadBalancerVIP $VIP -IPAddress "10.0.0.1" -Port 35 -VirtualNetworkAdapter $VNIC
```

The first command gets the virtual machine object named VM01 on VMHost01 and stores the object in the $VM variable.

The second command gets the virtual network adapter for the virtual machine stored in $VM and stores the object in the $VNIC variable.

The third command gets the load balancer with the address LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The fourth command gets the load balancer VIP with the address 10.0.0.1 for the load balancer stored in $LoadBalancer and stores the object in the $VIP variable.

The last command adds the virtual network adapter stored in $VNIC (in this case, the virtual network adapter for VM01) to the load balancer VIP stored in $VIP.

## PARAMETERS

### -IPAddress
Specifies an IPv4 or IPv6 address.

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

### -LoadBalancerVIP
Specifies a VIP in a load balancer.

```yaml
Type: LoadBalancerVIP
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -Port
Specifies the network port to use when adding an object or creating a connection.
Valid values are: 1 to 4095.

```yaml
Type: UInt16
Parameter Sets: (All)
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

### -VirtualNetworkAdapter
Specifies a virtual network adapter object for a virtual machine.

The maximum number of virtual network adapters varies by the type of host.
If the host type is Hyper-V, the maximum number of virtual network adapters is: 
- Up to four emulated adapters per virtual machine. 
- Up to eight synthetic adapters per virtual machine.
An exception is that no driver is available for an emulated network adapter on a Windows Server 2003 x64 guest.

If the host type is VMware ESX:
- Up to four emulated adapters per virtual machine.

If the host type is Citrix XenServer: 
- Up to seven emulated adapters per virtual machine.

```yaml
Type: VirtualNetworkAdapter
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

### LoadBalancerVIPMember
This cmdlet returns a **LoadBalancerVIPMember** object.

## NOTES

## RELATED LINKS

[Disable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCLoadBalancerVIPMember.md)

[Enable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCLoadBalancerVIPMember.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPMember.md)

[Get-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapter.md)

[Remove-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPMember.md)

