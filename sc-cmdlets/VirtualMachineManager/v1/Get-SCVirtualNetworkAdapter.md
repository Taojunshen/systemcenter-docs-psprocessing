---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: BEDED999-E5A8-42BB-A157-260A980B2E98
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualNetworkAdapter

## SYNOPSIS
Gets VMM virtual network adapter objects from a virtual machine, virtual machine template, or hardware profile.

## SYNTAX

### All
```
Get-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] [-All] [-ParentTypeVMOrHost]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HardwareProfile
```
Get-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] -HardwareProfile <HardwareProfile>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VM
```
Get-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] -VM <VM> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
Get-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] -VMTemplate <Template> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMHost
```
Get-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] -VMHost <Host> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] [-ID] <Guid> [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualNetworkAdapter** cmdlet gets one or more virtual network adapter objects from a virtual machine object, a virtual machine template object, or a hardware profile object in a Virtual Machine Manager (VMM) environment.

## EXAMPLES

### Example 1: Get virtual network adapters from a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Get-SCVirtualNetworkAdapter -VM $VM
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets all virtual network adapter objects on VM01 and displays information about the adapters to the user.

### Example 2: Get virtual network adapters from a virtual machine template
```
PS C:\>$VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> Get-SCVirtualNetworkAdapter -Template $VMTemplate
```

The first command gets all virtual machine template objects from the VMM library, selects the template object named VMTemplate01, and stores the object in the $VMTemplate variable.

The last command gets all virtual network adapter objects VMTemplate01 and displays information about these adapters to the user.

### Example 3: Get virtual network adapters from a hardware profile
```
PS C:\>$HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> Get-SCVirtualNetworkAdapter -HardwareProfile $HWProfile
```

The first command gets all hardware profile objects in the VMM library, selects the profile object named NewHWProfile01, and then stores the object in the $HWProfile variable.

The second command gets all virtual network adapter objects NewHWProfile01 and displays information about these adapters to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.

For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
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

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a network object.

```yaml
Type: String
Parameter Sets: ID
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

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

### -ParentTypeVMOrHost
Indicates that the parent type is a virtual machine or a host.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: VMHost
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

### VirtualNetworkAdapter
This cmdlet returns a **VirtualNetworkAdapter** object.

## NOTES
* Requires a VMM virtual machine object, virtual machine template object, or hardware profile object, which can be retrieved by using the Get-SCVirtualMachine, Get-SCVMTemplate, or Get-SCHardwareProfile cmdlets, respectively.

## RELATED LINKS

[Get-SCHardwareProfile](xref:VirtualMachineManager/v1/Get-SCHardwareProfile.md)

[Get-SCVMTemplate](xref:VirtualMachineManager/v1/Get-SCVMTemplate.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[New-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/New-SCVirtualNetworkAdapter.md)

[Remove-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapter.md)

[Repair-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Repair-SCVirtualNetworkAdapter.md)

[Set-SCVirtualNetworkAdapter](xref:VirtualMachineManager/v1/Set-SCVirtualNetworkAdapter.md)

