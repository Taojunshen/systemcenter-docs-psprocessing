---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 225FD757-CD85-46CF-B404-9EA4F3976C86
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindowSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindowSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindowSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCServicingWindowSubscription

## SYNOPSIS
Gets a list of servicing window subscriptions.

## SYNTAX

### Connection (Default)
```
Get-SCServicingWindowSubscription [-VMMServer <ServerConnection>] [[-ServicingWindow] <ServicingWindow>]
 [<CommonParameters>]
```

### FromVM
```
Get-SCServicingWindowSubscription [-VMMServer <ServerConnection>] [[-ServicingWindow] <ServicingWindow>]
 -VM <VM> [<CommonParameters>]
```

### FromHost
```
Get-SCServicingWindowSubscription [-VMMServer <ServerConnection>] [[-ServicingWindow] <ServicingWindow>]
 -VMHost <Host> [<CommonParameters>]
```

### FromService
```
Get-SCServicingWindowSubscription [-VMMServer <ServerConnection>] [[-ServicingWindow] <ServicingWindow>]
 -Service <Service> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCServicingWindowSubscription** cmdlet gets a list of servicing window subscriptions.

## EXAMPLES

### Example 1: Get a list of servicing window subscriptions for a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $SvcWindowSub = Get-SCServicingWindowSubscription -VM $VM
PS C:\> $SvcWindowSub
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the servicing window subscription objects for the virtual machine stored in $VM (VM01) and stores the objects in the $SvcWindowSub variable.

The last command displays the servicing windows stored in $SvcWindowSub for the user.

### Example 2: Get a list of subscriptions for a specified servicing window
```
PS C:\> $SvcWindow = Get-SCServicingWindow -Name "Backup Staging A"
PS C:\> $SvcWindowSub = Get-SCServicingWindowSubscription -ServicingWindow $SvcWindow
PS C:\> $SvcWindowSub
```

The first command gets the servicing window object named Backup Staging A and stores the object in the $SvcWindow variable.

The second command gets the servicing window subscription objects for the servicing window stored in $SvcWindow (Backup Staging A) and stores the objects in the $SvcWindowSub variable.

The last command displays the list of subscriptions stored in $SvcWindowSub to the user.

### Example 3: Get the servicing window subscription for a specified virtual machine and a specified servicing window
```
PS C:\> $VM = Get-VM -Name "VM01"
PS C:\> $SvcWindow = Get-SCServicingWindow -Name "Backup Staging A"
PS C:\> $SvcWindowSub = Get-SCServicingWindowSubscription -VM $VM -ServicingWindow $SvcWindow 
PS C:\> $SvcWindowSub
```

The first command gets the virutal machine object named VM01 and stores the object in the $VM variable.

The second command gets the servicing window object named Backup Staging A and stores the object in the $SvcWindow variable.

The third command gets the servicing window subscription object for the virtual machine stored in $VM (VM01) and the servicing window stored in $SvcWindow (Backup Staging A) and stores the object in the $SvcWindowSub variable.

The last command displays information about the servicing window subscription stored in $SvcWindowSub to the user.

## PARAMETERS

### -Service
Specifies a Virtual Machine Manager (VMM) service object.

```yaml
Type: Service
Parameter Sets: FromService
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicingWindow
Specifies a servicing window object.

```yaml
Type: ServicingWindow
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: FromVM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: FromHost
Aliases: 

Required: True
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

### ServicingWindowSubscription
This cmdlet returns a **ServicingWindowSubscription** object.

## NOTES

## RELATED LINKS

[Add-SCServicingWindowSubscription](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCServicingWindowSubscription.md)

[Get-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindow.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Remove-SCServicingWindowSubscription](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServicingWindowSubscription.md)

