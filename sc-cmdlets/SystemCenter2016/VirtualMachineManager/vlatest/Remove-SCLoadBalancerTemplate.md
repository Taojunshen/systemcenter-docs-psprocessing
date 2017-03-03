---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6A43BCA4-91ED-4091-8B82-718719B1985C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCLoadBalancerTemplate

## SYNOPSIS
Removes a load balancer template from a service template.

## SYNTAX

```
Remove-SCLoadBalancerTemplate -LoadBalancerTemplate <LoadBalancerTemplate> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLoadBalancerTemplate** cmdlet removes a load balancer template from a service template.

## EXAMPLES

### Example 1: Remove a load balancer template from a service template
```
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $LoadBalancerTemplate = Get-SCLoadBalancerTemplate -ServiceTemplate $ServiceTemplate
PS C:\> Remove-SCLoadBalancerTemplate -LoadBalancerTemplate $LoadBalancerTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the load balancer template for the service template in $ServiceTemplate and stores the object in the $LoadBalancerTemplate variable.

The last command removes the load balancer template stored in $LoadBalancer from the service template stored in $ServiceTemplate.

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

## NOTES

## RELATED LINKS

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Get-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerTemplate.md)

[New-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerTemplate.md)

[Set-SCLoadBalancerTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerTemplate.md)

