---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 060198BD-F5E2-4D09-B6CB-603376410C78
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerTemplate

## SYNOPSIS
Creates a load balancer template that can be added to a service template.

## SYNTAX

### Default (Default)
```
New-SCLoadBalancerTemplate -ComputerTierTemplate <ComputerTierTemplate>
 -LoadBalancerVIPTemplate <LoadBalancerVIPTemplate> -VirtualNetworkAdapter <VirtualNetworkAdapter>
 [-VMNetworkVIP <VMNetwork>] [-VMNetworkServiceSetting <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### LogicalNetworkVIP
```
New-SCLoadBalancerTemplate -ComputerTierTemplate <ComputerTierTemplate>
 -LoadBalancerVIPTemplate <LoadBalancerVIPTemplate> -VirtualNetworkAdapter <VirtualNetworkAdapter>
 -LogicalNetworkVIP <LogicalNetwork> [-VMNetworkVIP <VMNetwork>] [-VMNetworkServiceSetting <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerTemplate** cmdlet creates a load balancer template that you can add to a service template.
When you deploy a service instance based on the service template, Virtual Machine Manager (VMM) locates an appropriate load balancer in your VMM environment during placement, and configures it based on the properties provided in the load balancer template.

## EXAMPLES

### Example 1: Create a load balancer template
```
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $TierTemplate = Get-SCComputerTierTemplate -ServiceTemplate $ServiceTemplate
PS C:\> $LBVIPTemplate = Get-SCLoadBalancerVIPTemplate -Manufacturer "LB Manufacturer" -Model "LB01"
PS C:\> $VMTemplate = Get-SCVMTemplate -ComputerTierTemplate $TierTemplate
PS C:\> $Adapter = Get-SCVirtualNetworkAdapter -VMTemplate $VMTemplate
PS C:\> $LBTemplate = New-SCLoadBalancerTemplate -ComputerTierTemplate $TierTemplate -LoadBalancerVIPTemplate $LBVIPTemplate -VirtualNetworkAdapter $Adapter
PS C:\> $LBTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the computer tier template for the service template stored in $ServiceTemplate (in this case, ServiceTemplate01) and stores the object in the $TierTemplate variable.

The third command gets the load balancer VIP template with the manufacturer of LB Manufacturer and model LB01, and stores the template in the $LBVIPTemplate variable.

The fourth command gets the virtual machine template for the computer tier template stored in $TierTemplate.

The fifth command gets the virtual network adapter for the virtual machine template stored in $VMTemplate.

The sixth command creates a load balancer template using the computer tier template, load balancer template, and virtual network adapter objects obtained in the previous commands, and stores the object in the $LBTemplate variable.

The last command displays information about the load balancer template.

## PARAMETERS

### -ComputerTierTemplate
Specifies a computer tier template object.

```yaml
Type: ComputerTierTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -LoadBalancerVIPTemplate
Specifies a load balancer virtual IP (VIP) template.

```yaml
Type: LoadBalancerVIPTemplate
Parameter Sets: (All)
Aliases: 

Required: True
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

Required: True
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

### LoadBalancerTemplate
This cmdlet returns a **LoadBalancerTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPTemplate.md)

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Get-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapter.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Get-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerTemplate.md)

[Remove-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerTemplate.md)

[Set-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerTemplate.md)

