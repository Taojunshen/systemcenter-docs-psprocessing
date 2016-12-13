---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierConfiguration.md
schema: 2.0.0
ms.assetid: 6AE8F9A2-F8DA-4992-B183-0DE24D5768D0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCLoadBalancerConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCLoadBalancerConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCLoadBalancerConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLoadBalancerConfiguration

## SYNOPSIS
Gets the configuration details for the load balancer that is contained within a computer tier configuration.

## SYNTAX

```
Get-SCLoadBalancerConfiguration [-VMMServer <ServerConnection>]
 -ComputerTierConfiguration <ComputerTierConfiguration> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLoadBalancerConfiguration** cmdlet gets the configuration details for the load balancer that is contained within a computer tier configuration.

## EXAMPLES

### Example 1: Get the load balancer configuration for a computer tier configuration
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $LBConfig = Get-SCLoadBalancerConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $LBConfig
```

The first command gets service the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the load balancer configuration for the computer tier configuration stored in $TierConfig and stores the object in the $LBConfig variable.

The last command displays the properties of the load balancer configuration stored in $LBConfig to the user.

## PARAMETERS

### -ComputerTierConfiguration
Specifies a computer tier configuration object.

```yaml
Type: ComputerTierConfiguration
Parameter Sets: (All)
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

### LoadBalancerConfiguration
This cmdlet returns a **LoadBalancerConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:VirtualMachineManager/v1/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:VirtualMachineManager/v1/Get-SCServiceConfiguration.md)

[Set-SCLoadBalancerConfiguration](xref:VirtualMachineManager/v1/Set-SCLoadBalancerConfiguration.md)

