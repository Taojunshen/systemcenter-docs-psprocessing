---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 686a4f37-aed6-4143-bd16-9191c837b5ec
schema: 2.0.0
ms.assetid: A2E59D6B-094D-4EFA-9E83-83F1CBF7FB4B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancingMethod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancingMethod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancingMethod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancingMethod

## SYNOPSIS
Creates a load balancer method object that is used when you create a load balancer virtual IP.

## SYNTAX

```
New-SCLoadBalancingMethod -Name <String> [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancingMethod** cmdlet creates a load balancer method object that is used when you create a load balancer virtual IP.

For information about creating a load balancer virtual IP, type `Get-Help New-SCLoadBalancerVIP -Detailed`.

## EXAMPLES

### Example 1: Create a load balancing method object
```
PS C:\> $LBMethod = New-SCLoadBalancingMethod -Name "LeastConnections"
```

This command creates a load balancing method object named Least Connections and stores the object in the $LBMethod variable.

## PARAMETERS

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Specifies a string used to attribute an object or property.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LoadBalancingMethod
This cmdlet returns a **LoadBalancingMethod** object.

## NOTES

## RELATED LINKS

