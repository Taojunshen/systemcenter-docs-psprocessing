---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Enable-SCLoadBalancerVIPMember.md
schema: 2.0.0
ms.assetid: 093AEE3A-542F-464F-9518-7917C0B7025C
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Disable-SCLoadBalancerVIPMember.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Disable-SCLoadBalancerVIPMember.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Disable-SCLoadBalancerVIPMember.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCLoadBalancerVIPMember

## SYNOPSIS
Disables a member of a load balancer VIP.

## SYNTAX

```
Disable-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>]
 [-LoadBalancerVIPMember] <LoadBalancerVIPMember> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCLoadBalancerVIPMember** cmdlet disables a member of a load balancer virtual IP (VIP), and places the member in a Desired Status of Down.

To enable a load balancer VIP member, use the Enable-SCLoadBalancerVIPMember cmdlet.

## EXAMPLES

### Example 1: Disable a member of a load balancer virtual IP (VIP)
```
PS C:\>$LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> $VIP = Get-SCLoadBalancerVIP -LoadBalancer $LoadBalancer -IPAddress "192.168.0.1"
PS C:\> $VIPMember = Get-SCLoadBalancerVIPMember -LoadBalancerVIP $VIP -IPAddress "192.168.0.1"
PS C:\> Disable-SCLoadBalancerVIPMember -LoadBalancerVIPMember $VIPMember
```

The first command gets the load balancer object with the address of LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The second command gets the load balancer VIP with the IP address 192.168.0.1 for the load balancer stored in $LoadBalancer and stores the object in the $VIP variable.

The third command gets the VIP member for the load balancer VIP stored in $VIP with the address of 192.168.0.1 and stores the object in the $VIPMember variable.

The last command disables the VIP member stored in $VIPMember and displays information about the VIP member to the user.

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

### LoadBalancerVIPMember
This cmdlet returns a **LoadBalancerVIPMember** object.

## NOTES

## RELATED LINKS

[Enable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/Enable-SCLoadBalancerVIPMember.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancerVIP.md)

[Get-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancerVIPMember.md)

[New-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCLoadBalancerVIPMember.md)

[Remove-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCLoadBalancerVIPMember.md)
