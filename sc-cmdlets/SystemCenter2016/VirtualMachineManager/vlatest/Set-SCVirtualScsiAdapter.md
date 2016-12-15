---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: 9EBB2556-8910-4251-A419-8EEDA4BCF2B3
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualScsiAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualScsiAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualScsiAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualScsiAdapter

## SYNOPSIS
Changes properties of a virtual SCSI adapter used in VMM.

## SYNTAX

```
Set-SCVirtualScsiAdapter [-ScsiControllerType <VMSCSIControllerType>]
 [-VirtualScsiAdapter] <VirtualSCSIAdapter> [-AdapterID <Byte>] [-ShareVirtualScsiAdapter <Boolean>]
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualScsiAdapter** cmdlet changes one or more properties of a virtual SCSI adapter used in a Virtual Machine Manager (VMM) environment.
Settings that you can modify include specifying whether or not a virtual SCSI adapter is shared and setting the adapter ID.

Note: Using the *ShareVirtualScsiAdapter* parameter to share a virtual SCSI adapter on a virtual machine in order to enable guest clustering is supported only if the virtual machine is deployed on a VMware ESX host.
The *SharedVirtualScsiAdapter* parameter is not used for a virtual machine on a Hyper-V host because a virtual machine on a Hyper-V host uses iSCSI for shared storage.

Note: **Set-SCVirtualScsiAdapter** is not used for Citrix XenServer hosts because the SCSI adapter on Citrix XenServer virtual machines is not configurable.

## EXAMPLES

### Example 1: Share a specific virtual SCSI adapter on a virtual machine to enable it for guest clustering
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $Adapter = Get-SCVirtualScsiAdapter -VM $VM 
PS C:\> Set-SCVirtualSCSIAdapter -VirtualScsiAdapter $Adapter -ShareVirtualScsiAdapter $True
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the SCSI adapter object on VM01 and stores the object in the $Adapter variable.
This example assumes that VM01 has one virtual SCSI adapter.
However, a virtual machine can have up to four virtual SCSI adapters attached.

The last command enables the virtual SCSI adapter object stored in $Adapter and specifies that is it shared so that it can be used in guest clustering.

Note: Using the *Shared* parameter to share a virtual SCSI adapter on a virtual machine is supported only if the virtual machine is deployed on an ESX host.
The *Shared* parameter is not used for a virtual machine a Hyper-V host because a virtual machine on a Hyper-V host uses iSCSI for shared storage.
The *Shared* parameter is also not used for a virtual machine on a XenServer host because XenServer-based virtual machines always have exactly one SCSI adapter.

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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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
To obtain a user role object, use the Get-SCUserRole cmdlet.

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
-  NoType
-  LsiLogic
-  BusLogic
-  ParaVirtualSCSI
-  LsiLogicSAS

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

Type of Host                      Uses This Parameter

 Hyper-V host:                      No  (for guest clustering, use iSCSI storage) 
 XenServer host:        No  (Xen VMs always have exactly one SCSI adapter)

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

### -VirtualScsiAdapter
Specifies a virtual SCSI adapter object for a virtual machine.

Type of Host           Number of Virtual SCSI Adapters

Hyper-V:                              Up to four synthetic virtual SCSI adapters per VM, and up to 64 devices per adapter.
Supports a virtual disk drive size up to 2040 GB.
Does not support emulated virtual SCSI adapters. 
VMware ESX:               Up to four virtual SCSI adapters per VM, and up to 15 devices per adapter.
Supports a virtual disk drive size up to 2048 GB. 
Citrix XenServer:    Always one virtual SCSI adapter per VM, and up to eight devices per adapter.
Supports a virtual disk drive size up to 2048 GB.

```yaml
Type: VirtualSCSIAdapter
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

### VirtualSCSIAdapter
This cmdlet returns a **VirtualScsiAdapter** object.

## NOTES
* Requires a VMM virtual SCSI adapter object, which can be retrieved by using the Get-SCVirtualScsiAdapter cmdlet.

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualScsiAdapter.md)

[New-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualScsiAdapter.md)

[Remove-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualScsiAdapter.md)

