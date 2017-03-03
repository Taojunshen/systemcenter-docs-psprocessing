---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9345E61F-AF7C-42C7-888A-4541E07884ED
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualScsiAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualScsiAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualScsiAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCVirtualScsiAdapter

## SYNOPSIS
Creates a virtual SCSI adapter on a virtual machine, virtual machine template, or hardware profile used in VMM.

## SYNTAX

### VM (Default)
```
New-SCVirtualScsiAdapter [-VMMServer <ServerConnection>] -VM <VM> [[-AdapterID] <Byte>]
 [-ShareVirtualScsiAdapter <Boolean>] [-Synthetic] [-ScsiControllerType <VMSCSIControllerType>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HardwareProfile
```
New-SCVirtualScsiAdapter [-VMMServer <ServerConnection>] -HardwareProfile <HardwareProfile>
 [[-AdapterID] <Byte>] [-ShareVirtualScsiAdapter <Boolean>] [-Synthetic]
 [-ScsiControllerType <VMSCSIControllerType>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
New-SCVirtualScsiAdapter [-VMMServer <ServerConnection>] -VMTemplate <Template> [[-AdapterID] <Byte>]
 [-ShareVirtualScsiAdapter <Boolean>] [-Synthetic] [-ScsiControllerType <VMSCSIControllerType>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### JobGroup
```
New-SCVirtualScsiAdapter [-VMMServer <ServerConnection>] -JobGroup <Guid> [[-AdapterID] <Byte>]
 [-ShareVirtualScsiAdapter <Boolean>] [-Synthetic] [-ScsiControllerType <VMSCSIControllerType>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualScsiAdapter** cmdlet creates a virtual SCSI adapter on a virtual machine, virtual machine template, or hardware profile used in a Virtual Machine Manager (VMM) environment.
After you create the virtual SCSI adapter, you can use the **Set-SCVirtualScsiAdapter** cmdlet to modify its settings.

Note: Using the *ShareVirtualScsiAdapter* parameter to share a virtual SCSI adapter on a virtual machine in order to enable guest clustering is supported only if the virtual machine is deployed on an ESX host.
The *SharedVirtualScsiAdapter* parameter is not used for a virtual machine on a Hyper-V host because a virtual machine on a Hyper-V host uses iSCSI for shared storage.

A virtual machine on a Citrix XenServer host always has one virtual SCSI adapter.
You cannot remove this adapter or add additional adapters.

## EXAMPLES

### Example 1: Create a virtual SCSI adapter on a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> New-SCVirtualScsiAdapter -VM $VM
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a virtual SCSI adapter on VM01.

### Example 2: Create a virtual SCSI adapter on a virtual machine template
```
PS C:\> $VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> New-SCVirtualScsiAdapter -VMTemplate $VMTemplate
```

The first command gets the virtual machine template object named VMTemplate01 from the VMM library and stores the object in the $VMTemplate variable.

The second command creates a virtual SCSI adapter on VMTemplate01.

### Example 3: Create a virtual SCSI adapter on a hardware profile
```
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> New-SCVirtualScsiAdapter -HardwareProfile $HWProfile
```

The first command gets the hardware profile object named NewHWProfile01 from the VMM library and stores the object in the $HWProfile variable.

The second command creates a virtual SCSI adapter on NewHWProfile01.

## PARAMETERS

### -AdapterID
Specifies the logical unit number, or LUN ID.
Hyper-V and XenServer do not expose this value, and it cannot be changed.
For a VMware ESX host, the default is 7 and cannot be changed.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: JobGroup
Aliases: 

Required: True
Position: Named
Default value: None
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

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the **Get-SCUserRole** cmdlet.

```yaml
Type: UserRole
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

### -ScsiControllerType
Specifies a SCSI controller type.
Valid values are: 

- DefaultType
- NoType
- LsiLogic
- BusLogic
- ParaVirtualSCSI
- LsiLogicSAS

```yaml
Type: VMSCSIControllerType
Parameter Sets: (All)
Aliases: 
Accepted values: DefaultTypeNoType, LsiLogic, BusLogic, ParaVirtualSCSI, LsiLogicSAS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareVirtualScsiAdapter
Indicates whether a virtual SCSI adapter is shared so that it can be used in guest clustering. 

- Hyper-V host: No  (for guest clustering, use iSCSI storage) 
- XenServer host: No  (Xen VMs always have exactly one SCSI adapter)

Note: When sharing a SCSI controller on a virtual machine on an ESX host, VMM defaults the SCSI sharing policy on VMware to "physical."

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: Shared

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Synthetic
Indicates that a device, such as a virtual network adapter, on a virtual machine deployed on a Hyper-V host is a high-performance synthetic device.
Requires a virtualization-aware guest operating system on the virtual machine.

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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualSCSIAdapter
This cmdlet returns a **VirtualSCSIAdapter** object.

## NOTES
* Requires a VMM virtual machine object, virtual machine template object, or hardware profile object, which can be retrieved by using the **Get-SCVirtualMachine**, **Get-SCVMTemplate**, or **Get-SCHardwareProfile** cmdlets, respectively.

## RELATED LINKS

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHardwareProfile.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualScsiAdapter.md)

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Remove-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualScsiAdapter.md)

[Set-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualScsiAdapter.md)

