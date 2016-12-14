---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierConfiguration.md
schema: 2.0.0
ms.assetid: 06A121A3-4834-4C34-835A-027E29BD9455
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCLoadBalancerConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCLoadBalancerConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCLoadBalancerConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLoadBalancerConfiguration

## SYNOPSIS
Updates a load balancer configuration object for a computer tier.

## SYNTAX

```
Set-SCLoadBalancerConfiguration [-LoadBalancerVIP <String>] [-Port <Int32>] [-LoadBalancer <LoadBalancer>]
 [-PinLoadBalancer <Boolean>] [-UseExistingVIPAddress <Boolean>] [-VIPAddressPool <StaticIPAddressPool>]
 [-PinVIPAddressPool <Boolean>] -LoadBalancerConfiguration <LoadBalancerConfiguration> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLoadBalancerConfiguration** cmdlet updates a load balancer configuration object for a computer tier.

## EXAMPLES

### Example 1: Set the properties of a load balancer configuration
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $LBConfig = Get-SCLoadBalancerConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $LB = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> Set-SCLoadBalancerConfiguration -LoadBalancerConfiguration $LBConfig -LoadBalancer $LB
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the load balancer configuration for the computer tier configuration stored in $TierConfig and stores the object in the $LBConfig variable.

The fourth command gets the load balancer with the address of LB01.Contoso.com and stores the object in the $LB variable.

The last command set the properties of the load balancer configuration object stored in $LB.

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

### -LoadBalancer
Specifies a load balancer object.

```yaml
Type: LoadBalancer
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerConfiguration
Specifies a load balancer configuration object.

```yaml
Type: LoadBalancerConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancerVIP
Specifies a virtual IP (VIP) in a load balancer.

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

### -PinLoadBalancer
Indicates whether the load balancer chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinVIPAddressPool
Indicates whether the virtual IP (VIP) address pool chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
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
Type: Int32
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

### -UseExistingVIPAddress
Indicates whether the existing virtual IP (VIP) address is used, if one has been assigned.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VIPAddressPool
Specifies a static IP address pool.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LoadBalancerConfiguration
This cmdlet returns a **LoadBalancerConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCComputerTierConfiguration.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCLoadBalancerConfiguration.md)

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceConfiguration.md)

