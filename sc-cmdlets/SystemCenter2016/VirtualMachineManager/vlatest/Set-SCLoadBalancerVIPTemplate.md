---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLoadBalancerVIPTemplate.md
schema: 2.0.0
ms.assetid: 9C7E6C83-F2A3-4140-89BB-41CF40D84C28
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerVIPTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerVIPTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerVIPTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLoadBalancerVIPTemplate

## SYNOPSIS
Modifies the properties of a load balancer VIP template.

## SYNTAX

```
Set-SCLoadBalancerVIPTemplate [-VMMServer <ServerConnection>]
 [-LoadBalancerVIPTemplate] <LoadBalancerVIPTemplate> [-Name <String>] [-Description <String>]
 [-LoadBalancerManufacturer <String>] [-LoadBalancerModel <String>]
 [-LoadBalancerConnectionPersistence <LoadBalancerConnectionPersistence>]
 [-LoadBalancerHealthMonitor <LoadBalancerHealthMonitor[]>] [-LoadBalancerProtocol <LoadBalancerProtocol>]
 [-LoadBalancerPort <UInt16>] [-LoadBalancerBackEndPort <UInt16>] [-LoadBalancingMethod <LoadBalancingMethod>]
 [-DisableLoadBalancerConnectionPersistence] [-MakeGeneric] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLoadBalancerVIPTemplate** cmdlet modifies the properties of a load balancer virtual IP (VIP) template.

## EXAMPLES

### Example 1: Change the load balancing method in a load balancer virtual IP (VIP) template
```
PS C:\>$VIPTemplate = Get-SCLoadBalancerVIPTemplate -Manufacturer "LB Manufacturer" -Model "LB01" -Name "VIPTemplate01"
PS C:\> $LBMethod = New-SCLoadBalancingMethod -Name "RoundRobin"
PS C:\> Set-SCLoadBalancerVIPTemplate -LoadBalancerVIPTemplate $VIPTemplate -LoadBalancingMethod $LBMethod
```

The first command gets the VIP template object named VIPTemplate01 and stores the object in the $VIPTemplate variable.

The second command creates a new load balancing method object with the name Round Robin and stores the object in the $LBMethod variable.

The last command changes the load balancing method for the VIP template stored in $VIPTemplate to the method stored in $LBMethod, which is Round Robin.

## PARAMETERS

### -Description
Specifies a description for the VIP template.

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

### -DisableLoadBalancerConnectionPersistence
Indicates that the load balancer connection persistence in a virtual IP (VIP) profile is disabled.

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

### -LoadBalancerBackEndPort
Specifies the port on which the backend service is running which is being load balanced.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerConnectionPersistence
Specifies a load balancer connection persistence object.

```yaml
Type: LoadBalancerConnectionPersistence
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerHealthMonitor
Specifies an array of load balancer health monitor objects.

```yaml
Type: LoadBalancerHealthMonitor[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerManufacturer
Specifies the name of the company that manufactured a load balancer.
The acceptable values for this parameter are:


- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
- Single quote (')

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

### -LoadBalancerModel
Specifies the model of a load balancer.

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

### -LoadBalancerPort
Specifies the port to use when configuring a virtual IP (VIP) in a load balancer.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerProtocol
Specifies the protocol to use when connecting to a load balancer, or a load balancer protocol object.

```yaml
Type: LoadBalancerProtocol
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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancingMethod
Specifies the load balancing method to use.
The acceptable values for this parameter are:

- RoundRobin
- LeastConnectionsmember
- Observedmember
- Predictivemember
- Ratiomember
- Fastestmember
- LeastConnections
- Observednode
- Predictivenode
- Rationode
- FastestResponseTime
- LeastSessions 
- None

To determine the available methods for a specific load balancer, use this command: `(Get-SCLoadBalancer)\[0\].AvailableLoadBalancingMethods`

```yaml
Type: LoadBalancingMethod
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MakeGeneric
Indicates that a virtual IP (VIP) profile is able to apply generic load balancer settings.

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

### LoadBalancer
This cmdlet returns a **LoadBalancer** object.

## NOTES

## RELATED LINKS

[Get-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPTemplate.md)

[New-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPTemplate.md)

[New-SCLoadBalancingMethod](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancingMethod.md)

[Remove-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPTemplate.md)

