---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Disable-SCLoadBalancerVIPMember.md
schema: 2.0.0
ms.assetid: B63294F0-6820-434D-922F-A071F54DC9F5
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCLoadBalancerVIPMember.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCLoadBalancerVIPMember.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCLoadBalancerVIPMember.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCLoadBalancerVIPMember

## SYNOPSIS
Removes a member from a load balancer VIP.

## SYNTAX

```
Remove-SCLoadBalancerVIPMember [-VMMServer <ServerConnection>] [-LoadBalancerVIPMember] <LoadBalancerVIPMember>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLoadBalancerVIPMember** cmdlet removes a member from a load balancer virtual IP (VIP).

## EXAMPLES

### Example 1: Remove a member from a load balancer VIP
```
PS C:\>$LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> $VIP = Get-SCLoadBalancerVIP -LoadBalancer $LoadBalancer -IPAddress "10.0.0.1"
PS C:\> $VIPMember = Get-SCLoadBalancerVIPMember -LoadBalancerVIP $VIP -IPAddress "10.0.0.1"
PS C:\> Remove-SCLoadBalancerVIPMember -LoadBalancerVIPMember $VIPMember
```

The first command gets the load balancer object with the address of LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The second command gets the load balancer VIP with the IP address 10.0.0.1 for the load balancer stored in $LoadBalancer and stores the object in the $VIP variable.

The third command gets the VIP member for the load balancer VIP stored in $VIP with the address of 10.0.0.1 and stores the object in the $VIPMember variable.

The last command removes the VIP member stored in $VIPMember from the load balancer VIP.

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

### LoadBalancerVIPMember
This cmdlet returns a **LoadBalancerVIPMember** object.

## NOTES

## RELATED LINKS

[Disable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/Disable-SCLoadBalancerVIPMember.md)

[Enable-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/Enable-SCLoadBalancerVIPMember.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancerVIP.md)

[Get-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancerVIPMember.md)

[New-SCLoadBalancerVIPMember](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCLoadBalancerVIPMember.md)

