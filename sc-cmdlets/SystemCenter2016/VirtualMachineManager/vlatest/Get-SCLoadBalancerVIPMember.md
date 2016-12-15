---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Disable-SCLoadBalancerVIPMember.md
schema: 2.0.0
ms.assetid: 6C764051-F0D5-45D6-B601-31C9B9627D14
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPMember.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPMember.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPMember.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLoadBalancerVIPMember

## SYNOPSIS
Gets a member of a load balancer VIP.

## SYNTAX

### All (Default)
```
Get-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>] [-IPAddress <String>] [<CommonParameters>]
```

### ByLoadBalancerVIP
```
Get-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>] -LoadBalancerVIP <LoadBalancerVIP>
 [-IPAddress <String>] [<CommonParameters>]
```

### ByID
```
Get-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>] [-IPAddress <String>] -ID <Guid>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLoadBalancerVIPMember** cmdlet gets a member of a load balancer virtual IP (VIP).

## EXAMPLES

### Example 1: Get a load balancer virtual IP (VIP) member
```
PS C:\>$LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> $VIP = Get-SCLoadBalancerVIP -LoadBalancer $LoadBalancer -IPAddress "192.168.0.1"
PS C:\> Get-SCLoadBalancerVIPMember -LoadBalancerVIP $VIP -IPAddress "192.168.0.1"
```

The first command gets the load balancer object with the address LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The second command gets the load balancer VIP with the IP address of 192.168.0.1 for the load balancer stored in $LoadBalancer and stores the object in the $VIP variable.

The last command gets the load balancer member for the load balancer VIP stored in $VIP with the IP address of 192.168.0.1 and displays information about the member to the user.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ByID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an IPv4 or IPv6 address.

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
Specifies a virtual IP (VIP) in a load balancer.

```yaml
Type: LoadBalancerVIP
Parameter Sets: ByLoadBalancerVIP
Aliases: 

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LoadBalancerVIPMember
This cmdlet returns a **LoadBalancerVIPMember** member.

## NOTES

## RELATED LINKS

[Disable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCLoadBalancerVIPMember.md)

[Enable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCLoadBalancerVIPMember.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIP.md)

[New-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPMember.md)

[Remove-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPMember.md)
