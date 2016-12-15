---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Disable-SCLoadBalancerVIPMember.md
schema: 2.0.0
ms.assetid: CA5D32C5-17BF-4A91-BE67-00890954CAE0
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCLoadBalancerVIPMember.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCLoadBalancerVIPMember.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCLoadBalancerVIPMember.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCLoadBalancerVIPMember

## SYNOPSIS
Enables a member of a load balancer VIP.

## SYNTAX

```
Enable-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>] [-LoadBalancerVIPMember] <LoadBalancerVIPMember>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCLoadBalancerVIPMember** cmdlet enables a member of a load balancer virtual IP (VIP) and places the member in a Desired Status of Up.

To disable a VIP member, use the Disable-SCLoadBalancerVIPMember cmdlet.

## EXAMPLES

### Example 1: Enable a member of a load balancer virtual IP (VIP)
```
PS C:\>$LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> $VIP = Get-SCLoadBalancerVIP -LoadBalancer $LoadBalancer -IPAddress "192.168.0.1"
PS C:\> $VIPMember = Get-SCLoadBalancerVIPMember -LoadBalancerVIP $VIP -IPAddress "192.168.0.1"
PS C:\> Enable-SCLoadBalancerVIPMember -LoadBalancerVIPMember $VIPMember
```

The first command gets the load balancer object with the address of LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The second command gets the load balancer VIP with the IP address 192.168.0.1 for the load balancer stored in $LoadBalancer and stores the object in the $VIP variable.

The third command gets the VIP member for the load balancer VIP stored in $VIP with the address of 192.168.0.1 and stores the object in the $VIPMember variable.

The last command enables the VIP member stored in $VIPMember and displays information about the VIP member to the user.

## PARAMETERS

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

### -LoadBalancerVIPMember
Specifies a member of a virtual IP (VIP) in a load balancer.

```yaml
Type: LoadBalancerVIPMember
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LoadBalancerVIPMember
This cmdlet returns a **LoadBalancerVIPMember** object.

## NOTES

## RELATED LINKS

[Disable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCLoadBalancerVIPMember.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIP.md)

[Get-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPMember.md)

[New-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPMember.md)

[Remove-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPMember.md)
