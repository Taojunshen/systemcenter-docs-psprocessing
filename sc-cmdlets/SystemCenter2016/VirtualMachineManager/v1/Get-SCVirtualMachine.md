---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: 4776C225-8A45-4453-847D-E4F16A57A44E
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualMachine

## SYNOPSIS
Gets virtual machine objects.

## SYNTAX

### All (Default)
```
Get-SCVirtualMachine [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMHostGroup
```
Get-SCVirtualMachine -VMHost <Host> [-VMMServer <ServerConnection>] [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Cloud
```
Get-SCVirtualMachine [-VMMServer <ServerConnection>] -Cloud <Cloud> [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Service
```
Get-SCVirtualMachine [-VMMServer <ServerConnection>] -Service <Service> [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ComputerTier
```
Get-SCVirtualMachine [-VMMServer <ServerConnection>] -ComputerTier <ComputerTier> [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### StorageQoSPolicy
```
Get-SCVirtualMachine [-VMMServer <ServerConnection>] -StorageQoSPolicy <StorageQoSPolicy> [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVirtualMachine [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualMachine** cmdlet gets one or more virtual machine objects from the Virtual Machine Manager (VMM) database.
This cmdlet gets virtual machines that are deployed on a virtual machine host or stored in the VMM library.

## EXAMPLES

### Example 1: Get all virtual machines and display information about each one
```
PS C:\>Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com"
```

This command gets all virtual machine objects on VMMServer01, and displays information about these virtual machine objects.

### Example 2: Get all virtual machines and display information about specific properties
```
PS C:\>Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | Format-List -Property Name, Owner, Description, HostName, OperatingSystem, CPUCount, Memory
```

This command gets all virtual machine objects on VMMServer01, and displays the values of the specified properties.

### Example 3: Get a virtual machine by name that is stored on a specified library server
```
PS C:\>Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> Get-SCVirtualMachine | Where-Object { $_.Name -Eq "VM02" -And $_.LibraryServer -Eq "LibraryServer01" } | Select-Object Name,LibraryServer,Status
```

The first command connects to VMMServer01.

The second command gets the virtual machine object named VM02 stored on LibraryServer01, and then displays the virtual machine name, the name of the library server, and the status of the virtual machine.

### Example 4: Get all virtual machines on the specified host
```
PS C:\>Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> Get-SCVirtualMachine -VMHost "VMHost01.Contoso.com"
```

The first command connects to VMMServer01.

The second command gets all virtual machine objects deployed on VMHost01, and displays information about these virtual machines.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: Cloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerTier
Specifies a computer tier object.

```yaml
Type: ComputerTier
Parameter Sets: ComputerTier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ID
Specifies the unique ID for an object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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

### -Service
Specifies a VMM service object.

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

### -StorageQoSPolicy
Specifies the Quality of Service (QoS) policy for the virtual machines that this cmdlet gets.

```yaml
Type: StorageQoSPolicy
Parameter Sets: StorageQoSPolicy
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
Parameter Sets: VMHostGroup
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualMachine
This cmdlet returns a **VirtualMachine** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMHost.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCUserRole.md)

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMMServer.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Repair-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Save-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Suspend-SCVirtualMachine.md)

