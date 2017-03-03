---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1589E3EC-6B1D-4641-B296-081D9F8BBDAB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Register-SCVirtualMachine

## SYNOPSIS
Registers an existing virtual machine with VMM that is currently not registered with the virtualization platform of any host managed by VMM and is not stored in the VMM library.

## SYNTAX

```
Register-SCVirtualMachine [-VMHost] <Host> [-Path] <String> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Register-SCVirtualMachine** cmdlet registers an existing virtual machine with Virtual Machine Manager (VMM).
Register a host that is not currently registered with the virtualization platform of any host managed by VMM, and is not stored in the VMM library.
Virtualization platforms are Hyper-V, VMware, and XenServer.
If virtual machine files are stored in the VMM library, you do not have to register the virtual machine before you deploy it on a host.

The configuration files for the virtual machine to register must be stored either in the file system on the host on which to deploy the virtual machine or stored on shared storage available to this host.

To register a virtual machine for a Hyper-V host, the configuration files for that virtual machine must be stored in a folder on the file system of the host or on shared storage.
Additionally, you must create an export of the virtual machine by using the Export command in the Hyper-V Manager console.
The path must specify a folder.

To register a virtual machine for a VMware ESX host,  the VMware configuration .vmx must be stored on the file system of the host or on shared storage.
There is no separate export step.
The path must specify the folder and the configuration file.

Do not use this cmdlet to register virtual machines on a XenServer host.

## EXAMPLES

### Example 1: Register an existing virtual machine on a Hyper-V host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "HyperVHost01"
PS C:\> Register-SCVirtualMachine -VMHost $VMHost -Path "D:\HyperVFolderForVMs"
```

The first command gets the Hyper-V host object named HyperVHost01, and then stores that object in the $VMHost variable.

The second command adds the existing virtual machine on HVHost02 to VMM by specifying the path of the folder that contains the virtual machine configuration file.

### Example 2: Register an existing virtual machine on a VMware ESX host
```
PS C:\> $VMHost = Get-VMHost -ComputerName "ESXHost03" 
PS C:\> Register-SCVirtualMachine -VMHost $VMHost -Path "[storage1]\VMwareFolderForVMs\MyVM.vmx"
```

The first command gets the object that represents a VMware ESX host called ESXHost03, and stores that host object in the $VMHost variable.

The second command adds an existing virtual machine on ESXHost03 to VMM by specifying the path of the virtual machine's virtual machine configuration file.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

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

### -JobVariable
Specifies the name of a variable in which to track and store job progress.

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

### -Path
Specifies the path of the virtual machine configuration file for the virtual machine that this cmdlet registers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### VirtualMachine

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Save-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

