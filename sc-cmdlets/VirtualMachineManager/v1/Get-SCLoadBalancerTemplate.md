---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierTemplate.md
schema: 2.0.0
ms.assetid: B0908063-B291-4535-B49E-A6984CA265D8
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCLoadBalancerTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCLoadBalancerTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCLoadBalancerTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLoadBalancerTemplate

## SYNOPSIS
Gets a load balancer template for a service or computer tier template.

## SYNTAX

### ComputerTierTemplate
```
Get-SCLoadBalancerTemplate [-VMMServer <ServerConnection>] -ComputerTierTemplate <ComputerTierTemplate>
 [<CommonParameters>]
```

### ServiceTemplate
```
Get-SCLoadBalancerTemplate [-VMMServer <ServerConnection>] -ServiceTemplate <ServiceTemplate>
 [<CommonParameters>]
```

### All
```
Get-SCLoadBalancerTemplate [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCLoadBalancerTemplate [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLoadBalancerTemplate** cmdlet gets the load balancer template for a service template or a computer tier template.

## EXAMPLES

### Example 1: Get the load balancer template for a service template
```
PS C:\>$ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $LoadBalancerTemplate = Get-SCLoadBalancerTemplate -ServiceTemplate $ServiceTemplate
PS C:\> $LoadBalancerTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the load balancer template for the service template stored in $ServiceTemplate and stores the object in the $LoadBalancerTemplate variable.

The last command displays the properties of the load balancer template stored in $LoadBalancerTemplate to the user.

### Example 2: Get the load balancer template for a computer tier template
```
PS C:\>$ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $TierTemplate = Get-SCComputerTierTemplate -ServiceTemplate $ServiceTemplate
PS C:\> $LoadBalancerTemplate = Get-SCLoadBalancerTemplate -ComputerTierTemplate $TierTemplate
PS C:\> $LoadBalancerTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the computer tier template for the service template stored in $ServiceTemplate and stores the object in the $TierTemplate variable.

The third command gets the load balancer template for the computer tier template stored in $TierTemplate and stores the object in the $LoadBalancerTemplate variable.

The last command displays the properties of the load balancer template stored in $LoadBalancerTemplate to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerTierTemplate
Specifies a computer tier template object.

```yaml
Type: ComputerTierTemplate
Parameter Sets: ComputerTierTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: ServiceTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### LoadBalancerTemplate
This cmdlet returns a **LoadBalancerTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierTemplate](xref:VirtualMachineManager/v1/Get-SCComputerTierTemplate.md)

[Get-SCServiceTemplate](xref:VirtualMachineManager/v1/Get-SCServiceTemplate.md)

[New-SCLoadBalancerTemplate](xref:VirtualMachineManager/v1/New-SCLoadBalancerTemplate.md)

[Remove-SCLoadBalancerTemplate](xref:VirtualMachineManager/v1/Remove-SCLoadBalancerTemplate.md)

[Set-SCLoadBalancerTemplate](xref:VirtualMachineManager/v1/Set-SCLoadBalancerTemplate.md)

