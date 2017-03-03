---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0B8E3E1B-B73C-4533-8C62-9ECB97C13697
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Enable-SCVMHost

## SYNOPSIS
Restores a virtual machine host in maintenance mode to full service.

## SYNTAX

```
Enable-SCVMHost [-VMHost] <Host> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCVMHost** cmdlet restores a virtual machine host in maintenance mode to full service as a host managed by Virtual Machine Manager (VMM).

**Enable-SCVMHost** supports any type of host managed by VMM, including Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

When you use **Enable-SCVMHost** to restore a host to full service, VMM automatically restores some capabilities but requires you to perform certain actions manually.

VMM automatically re-enables the following items: 

- Creation of virtual machines on the host. 
- Migration of virtual machines to the host. 
- Host ratings for the host.

VMM also automatically refreshes the host to its current state.

You must manually restart any virtual machines that are in a saved state on a standalone host.
For hosts that are a node in a host cluster, you must manually restart the virtual machines and manually move any migrated virtual machines back to this node that you migrated to another node when you placed the host into maintenance mode.

## EXAMPLES

### Example 1: Restore the specified host to service
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> Enable-SCVMHost -VMHost $VMHost
```

The first command gets host object named VMHost01, and then stores the object in the $VMHost variable.

The second unblocks virtual machine creation operations on the host stored in $VMHost, and includes the host in host ratings during placement.
It also takes the host status out of "In Maintenance Mode" so that the next host refresh job sets the host status to its current state.

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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Host
This cmdlet returns a **Host** object.

## NOTES
* A host that you put into temporary maintenance mode is different from a host that you designate as a maintenance host. A maintenance host is a host that you dedicate for virtual machine maintenance tasks, such as the following tasks: 

- Patching stored virtual machines and templates. 
- Staging scripted virtual machine creation before you move the virtual machines into your production environment.

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCVMHost.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVMHost.md)

