---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A4C8C480-07A1-4083-BA47-99A41FE28A66
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServicingWindowSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServicingWindowSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServicingWindowSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCServicingWindowSubscription

## SYNOPSIS
Removes a servicing window from a virtual machine, host, or service.

## SYNTAX

### VM
```
Remove-SCServicingWindowSubscription [-ServicingWindow] <ServicingWindow> -VM <VM> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Host
```
Remove-SCServicingWindowSubscription [-ServicingWindow] <ServicingWindow> -VMHost <Host> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Service
```
Remove-SCServicingWindowSubscription [-ServicingWindow] <ServicingWindow> -Service <Service>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCServicingWindowSubscription** cmdlet removes a servicing window from a virtual machine, host, or service.

## EXAMPLES

### Example 1: Remove a servicing window subscription from all virtual machines owned by a specified user
```
PS C:\> $SvcWindow = Get-SCServicingWindow -Name "Backup Staging A"
PS C:\> Get-SCVirtualMachine | where {$_.Owner -eq "Contoso\ReneeLo"} | Remove-SCServicingWindowSubscription -ServicingWindow $SvcWindow
```

The first command gets the servicing window object named Backup Staging A and stores the object in the $SvcWindow variable.

The second command gets all virtual machine objects, selects only the virtual machines that are owned by Contoso\ReneeLo and then uses the pipeline operator to pass the virtual machines to the **Remove-SCServicingWindowSubscription** cmdlet, which removes all subscriptions for the servicing window stored in $SvcWindow from each virtual machine that is passed to it.

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

### -Service
Specifies a Virtual Machine Manager (VMM) service object.

```yaml
Type: Service
Parameter Sets: Service
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServicingWindow
Specifies a servicing window object.

```yaml
Type: ServicingWindow
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: Host
Aliases: 

Required: True
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

## NOTES
* Requires a VMM servicing window subscription object, which you can get with the **Get-SCServicingWindow** cmdlet.

## RELATED LINKS

[Add-SCServicingWindowSubscription](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCServicingWindowSubscription.md)

[Get-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindow.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCServicingWindowSubscription](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindowSubscription.md)

