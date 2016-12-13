---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: AF3FA484-6C16-4B09-AFC5-9A54C68DED38
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Disable-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Disable-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Disable-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCVMHost

## SYNOPSIS
Places a virtual machine host into maintenance mode.

## SYNTAX

### NoVMMigration (Default)
```
Disable-SCVMHost [-VMHost] <Host> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### InCluster
```
Disable-SCVMHost [-VMHost] <Host> [-MoveWithinCluster] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCVMHost** cmdlet places a virtual machine host that is managed by Virtual Machine Manager (VMM) into maintenance mode so that you can perform maintenance tasks on the host such as applying security updates or replacing hardware.

You can use the **Disable-SCVMHost** cmdlet to put individual Hyper-V hosts, VMware ESX hosts, or Citrix XenServer hosts into maintenance mode.
You can also use **Disable-SCVMHost** to put clustered hosts into maintenance mode.

To return the host to service, use the Enable-SCVMHost cmdlet.

To Put Hyper-V Hosts Into Maintenance Mode

If the host belongs to a cluster that supports live migration, you can choose either of the following methods:

Method 1: Migrate highly available virtual machines and save the other virtual machines.
When the *MoveWithinCluster* parameter is used with **Disable-SCVMHost**, the cmdlet uses Live Migration to migrate all running highly available virtual machines to other hosts in the cluster.
It places the running virtual machines that are not highly available into a saved state, which causes users to lose service.
Then, it places the host into maintenance mode.

Method 2: Save all the virtual machines.
**Disable-SCVMHost** places all the running virtual machines into a saved state, which causes users to lose service.
Then, it places the host into maintenance mode.

If the host does not belong to a cluster, or if it belongs to a cluster that does not support live migration, **Disable-SCVMHost** places all of the running virtual machines into a saved state, which causes users to lose service.
Then, it places the host into maintenance mode.

How **Disable-SCVMHost** Works with VMWare ESX Hosts

When you place an ESX host into maintenance mode using **Disable-SCVMHost**, VMM sends a request to enter maintenance mode to the VMware cCenter Server that manages that host.
The vCenter Server places the ESX host into maintenance mode.

Note: The system behavior of the virtual machines on the ESX Server host is determined by the configuration of the vCenter Server.
For example, if the VMware Distributed Resources Scheduler is not configured, you might have to manually shut down all the virtual machines on the host.
Or, you might have to move the virtual machines to another host to successfully place the ESX Server host into maintenance mode.

To Put XenServer Hosts Into Maintenance Mode

If the host belongs to a cluster that supports live migration, you can choose either of the following methods:

Method 1: Migrate highly available virtual machines and save the other virtual machines.
When the *MoveWithinCluster* parameter is used with **Disable-SCVMHost**, the cmdlet uses XenServer Live Migration to migrate all running highly available virtual machines to other hosts in the cluster.
It also places all the running virtual machines that are not highly available into a saved state, which causes users to lose service.
Then, it places the host into maintenance mode.

Method 2: Save all the virtual machines.
**Disable-VMHost** places all the running virtual machines into a saved state, which causes users to lose service.
Then, it places the host into maintenance mode.

If the host does not belong to a cluster, or if it belongs to a cluster that does not support live migration, **Disable-VMHost** places all of the running virtual machines into a saved state, which causes users to lose service.
Then, it places the host into maintenance mode.

Host Behavior In Maintenance Mode

After you place a host into maintenance mode, the following actions are affected: 

- Virtual machines cannot be created on the host. 
- Virtual machines cannot be migrated to the host. 
- The host is excluded from host ratings calculations performed during virtual machine placement. 
- The host status is not updated.

However, you can perform the following actions: 

- Remove the host from VMM if you make sure that the host is available and that its agent is in an appropriate state. 
- Start or stop virtual machines on the host. 
- Change the host properties. 
- Migrate a virtual machine from the host to another host.

## EXAMPLES

### Example 1: Place the specified host into maintenance mode and save all running virtual machines
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01" 
PS C:\> Disable-SCVMHost -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command places all running virtual machines that are deployed on the host stored in $VMHost into a saved state.
Then it sets the host status to "In Maintenance Mode".

### Example 2: Use live migration to migrate all running highly available virtual machines on a cluster node that is in maintenance mode
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost02"
PS C:\> Disable-SCVMHost -VMHost $VMHost -MoveWithinCluster
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command uses live migration to migrate all running highly available virtual machines on the host stored in $VMHost to another node in the cluster.
It places other running virtual machines into a saved state and then sets the value for the host state property to "In Maintenance Mode".

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

### -MoveWithinCluster
Indicates that all virtual machines currently deployed on a host that is a member of a host cluster will be migrated to another host in the same host cluster if that host is placed into maintenance mode.

```yaml
Type: SwitchParameter
Parameter Sets: InCluster
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

For more information about each type of host, see the Add-SCVMHost cmdlet.

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
* A host that you put into temporary maintenance mode is different from a host that you designate as a maintenance host. A maintenance host is a host that you dedicate for virtual machine maintenance tasks, such as the following: 

- Patching stored virtual machines and templates. 
- Staging scripted virtual machine creation before you move the virtual machines into your production environment.

## RELATED LINKS

[Add-SCVMHost](xref:VirtualMachineManager/v1/Add-SCVMHost.md)

[Enable-SCVMHost](xref:VirtualMachineManager/v1/Enable-SCVMHost.md)

[Get-SCCertificate](xref:VirtualMachineManager/v1/Get-SCCertificate.md)

[Move-SCVMHost](xref:VirtualMachineManager/v1/Move-SCVMHost.md)

[New-SCVMHost](xref:VirtualMachineManager/v1/New-SCVMHost.md)

[Read-SCVMHost](xref:VirtualMachineManager/v1/Read-SCVMHost.md)

[Register-SCVMHost](xref:VirtualMachineManager/v1/Register-SCVMHost.md)

[Remove-SCVMHost](xref:VirtualMachineManager/v1/Remove-SCVMHost.md)

[Restart-SCVMHost](xref:VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:VirtualMachineManager/v1/Set-SCVMHost.md)

[Start-SCVMHost](xref:VirtualMachineManager/v1/Start-SCVMHost.md)

[Stop-SCVMHost](xref:VirtualMachineManager/v1/Stop-SCVMHost.md)

