---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D53A5759-AC34-4E9E-BBD8-0463C299131E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIPTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCLoadBalancerVIPTemplate

## SYNOPSIS
Deletes a load balancer VIP template from VMM.

## SYNTAX

```
Remove-SCLoadBalancerVIPTemplate [-VMMServer <ServerConnection>]
 [-LoadBalancerVIPTemplate] <LoadBalancerVIPTemplate> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLoadBalancerVIPTemplate** cmdlet deletes a load balancer virtual IP (VIP) template from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Delete a load balancer virtual IP template
```
PS C:\> $VIPTemplate = Get-SCLoadBalancerVIPTemplate -Name "VIPTemplate01"
PS C:\> Remove-SCLoadBalancerVIPTemplate -LoadBalancerVIPTemplate $VIPTemplate
```

The first command gets the load balancer VIP template named VIPtemplate01 and stores the object in the $VIPTemplate variable.

The second command removes the load balancer VIP template stored in $VIPTemplate.

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

### -LoadBalancerVIPTemplate
Specifies a load balancer VIP template.

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

### LoadBalancerVIPTemplate
This cmdlet returns a **LoadBalancerVIPTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIPTemplate.md)

[New-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIPTemplate.md)

[Set-SCLoadBalancerVIPTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancerVIPTemplate.md)

