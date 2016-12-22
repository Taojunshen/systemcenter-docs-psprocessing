---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 62730743-21D7-4DC9-80DD-DAE260762EC2
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLoadBalancerTemplate

## SYNOPSIS
Configures the properties of a load balancer template.

## SYNTAX

### Default (Default)
```
Set-SCLoadBalancerTemplate [-VMNetworkVIP <VMNetwork>] [-VMNetworkServiceSetting <String>]
 [-LoadBalancerVIPTemplate <LoadBalancerVIPTemplate>] -LoadBalancerTemplate <LoadBalancerTemplate>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### LogicalNetworkVIP
```
Set-SCLoadBalancerTemplate [-LogicalNetworkVIP <LogicalNetwork>] [-VMNetworkVIP <VMNetwork>]
 [-VMNetworkServiceSetting <String>] [-LoadBalancerVIPTemplate <LoadBalancerVIPTemplate>]
 -LoadBalancerTemplate <LoadBalancerTemplate> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLoadBalancerTemplate** cmdlet configures the properties of a load balancer template.

## EXAMPLES

### Example 1: Configure a load balancer template
```
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $TierTemplate = Get-SCComputerTierTemplate -ServiceTemplate $ServiceTemplate 
PS C:\> $LoadBalancerTemplate = Get-SCLoadBalancerTemplate -ComputerTierTemplate $TierTemplate
PS C:\> Set-SCLoadBalancerTemplate -LoadBalancerTemplate $LoadBalancerTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the computer tier template for the service template stored in $ServiceTemplate and stores the object in the $TierTemplate variable.

The third command gets the load balancer template for the computer tier stored in $TierTemplate and stores the object in the $LoadBalancerTemplate variable.

The last command sets the properties for the load balancer template stored in $LoadBalancerTemplate.

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

### -LoadBalancerTemplate
Specifies a load balancer template object.

```yaml
Type: LoadBalancerTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancerVIPTemplate
Specifies a load balancer virtual IP (VIP) template.

```yaml
Type: LoadBalancerVIPTemplate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetworkVIP
Specifies the logical networks from which the front-end IP address for the load balancer should be assigned (the front-end logical network affinity).

```yaml
Type: LogicalNetwork
Parameter Sets: LogicalNetworkVIP
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

### -VMNetworkServiceSetting
Specifies a virtual machine network service setting.

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

### -VMNetworkVIP
Specifies a **VMNetwork** object.

```yaml
Type: VMNetwork
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

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Get-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierTemplate.md)

[Get-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerTemplate.md)

[New-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerTemplate.md)

[Remove-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerTemplate.md)

