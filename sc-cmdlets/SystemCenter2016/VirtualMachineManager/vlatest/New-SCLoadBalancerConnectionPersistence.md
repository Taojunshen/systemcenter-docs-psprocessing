---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 38c265f6-ffcf-4bbb-a25d-e49307f1f92e
schema: 2.0.0
ms.assetid: 4BD79567-1982-4ED4-AFB4-DD84B1423046
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerConnectionPersistence.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerConnectionPersistence.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerConnectionPersistence.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerConnectionPersistence

## SYNOPSIS
Creates a load balancer connection persistence object that is used when you create a load balancer virtual IP.

## SYNTAX

```
New-SCLoadBalancerConnectionPersistence -Name <String> [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerConnectionPersistence** cmdlet creates a load balancer connection persisetnce object that is used when you create a load balancer virtual IP.

For information about creating a load balancer virtual IP, type `Get-Help New-SCLoadBalancerVIP -Detailed`.

## EXAMPLES

### Example 1: Create a load balancer connection persistence object
```
PS C:\>$LBConnectionPersistence = New-SCLoadBalancerConnectionPersistence -Name "Source IP" -Value "255.255.255.0 "
```

This command creates a load balancer connection persistence object named Source IP and stores the object in the $LBConnectionPersistence variable.

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

### LoadBalancerConnectionPersistence
This cmdlet returns a **LoadBalancerConnectionPersistence** object.

## NOTES

## RELATED LINKS
