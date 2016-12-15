---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Copy-SCVirtualHardDisk.md
schema: 2.0.0
ms.assetid: E7F11623-2B91-497E-904C-BFD0B083D86E
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCV2V.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCV2V.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCV2V.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCV2V

## SYNOPSIS
Converts a virtual machine to a virtual machine deployed on a Hyper-V host that VMM manages.

## SYNTAX

### NoParse
```
New-SCV2V [-EnableVMNetworkOptimization <Boolean>] [-EnableMACAddressSpoofing <Boolean>]
 [-VMMServer <ServerConnection>] [-LibraryServer <LibraryServer>]
 -VMXComputerConfiguration <VmxMachineConfiguration> -VMHost <Host> [-JobGroup <Guid>] [-Trigger]
 [-Description <String>] [-Name <String>] [-Owner <String>] [-UserRole <UserRole>] [-Path <String>] [-StartVM]
 [-CPUCount <Byte>] [-CPURelativeWeight <Int32>] [-CPUType <ProcessorType>] [-MemoryMB <Int32>]
 [-DelayStartSeconds <Int32>] [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-LogicalNetwork <LogicalNetwork>] [-VMNetwork <VMNetwork>] [-NoConnection] [-MACAddress <String>]
 [-MACAddressType <String>] [-SourceNetworkConnectionID <String>] [-VirtualNetwork <VirtualNetwork>]
 [-VirtualNetworkAdapter <VirtualNetworkAdapter>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-OverridePatchPath <String>] [-SkipInstallVirtualizationGuestServices] [-NetworkLocation <String>]
 [-NetworkTag <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Parse
```
New-SCV2V [-EnableVMNetworkOptimization <Boolean>] [-EnableMACAddressSpoofing <Boolean>]
 [-VMMServer <ServerConnection>] [-LibraryServer <LibraryServer>] -VMHost <Host> -VMXPath <String>
 [-JobGroup <Guid>] [-Trigger] [-Description <String>] [-Name <String>] [-Owner <String>]
 [-UserRole <UserRole>] [-Path <String>] [-StartVM] [-CPUCount <Byte>] [-CPURelativeWeight <Int32>]
 [-CPUType <ProcessorType>] [-MemoryMB <Int32>] [-DelayStartSeconds <Int32>] [-StartAction <VMStartAction>]
 [-StopAction <VMStopAction>] [-LogicalNetwork <LogicalNetwork>] [-VMNetwork <VMNetwork>] [-NoConnection]
 [-MACAddress <String>] [-MACAddressType <String>] [-SourceNetworkConnectionID <String>]
 [-VirtualNetwork <VirtualNetwork>] [-VirtualNetworkAdapter <VirtualNetworkAdapter>] [-VLanEnabled <Boolean>]
 [-VLanID <UInt16>] [-OverridePatchPath <String>] [-SkipInstallVirtualizationGuestServices]
 [-NetworkLocation <String>] [-NetworkTag <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### FromVM
```
New-SCV2V [-EnableVMNetworkOptimization <Boolean>] [-EnableMACAddressSpoofing <Boolean>]
 [-VMMServer <ServerConnection>] -VM <VM> -VMHost <Host> [-JobGroup <Guid>] [-Trigger] [-Description <String>]
 [-Name <String>] [-Owner <String>] [-UserRole <UserRole>] [-Path <String>] [-StartVM] [-CPUCount <Byte>]
 [-CPURelativeWeight <Int32>] [-CPUType <ProcessorType>] [-MemoryMB <Int32>] [-DelayStartSeconds <Int32>]
 [-StartAction <VMStartAction>] [-StopAction <VMStopAction>] [-LogicalNetwork <LogicalNetwork>]
 [-VMNetwork <VMNetwork>] [-NoConnection] [-MACAddress <String>] [-MACAddressType <String>]
 [-SourceNetworkConnectionID <String>] [-VirtualNetwork <VirtualNetwork>]
 [-VirtualNetworkAdapter <VirtualNetworkAdapter>] [-VLanEnabled <Boolean>] [-VLanID <UInt16>]
 [-OverridePatchPath <String>] [-SkipInstallVirtualizationGuestServices] [-NetworkLocation <String>]
 [-NetworkTag <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCV2V** cmdlet converts a virtual machine created on a VMware ESX Server host.
This cmdlet converts to a virtual machine to one deployed on a Hyper-V host that Virtual Machine Manager (VMM) manages.
You cannot specify a VMware ESX host as the destination host for the new virtual machine.

A virtual-to-virtual machine (V2V) conversion requires that the host for the new virtual machine is a Hyper-V host.

The source for a V2V conversion of a VMware virtual machine is a set of files in the VMM library.
Store the following files in the VMM library: 

- A .vmx file.
A .vmk file is a VMware virtual machine configuration file.
A .vmx file is similar in function to the virtual machine configuration (.vmc) file that Hyper-V hosted virtual machines use.
A .vmx file is a text file that describes the properties and structure of a virtual machine that include name, memory, disk assignments, and network parameters. 
- One or more .vmdk files.
A .vmdk file is a VMware virtual hard disk file.
A .vmdk file is similar to the virtual hard disk (.vhd) file that Hyper-V hosted virtual machines use.
A .vmdk file contains the guest operating system, applications, and data. 
The current cmdlet identifies these files from the .vmx file.

Supported VMware virtual hard disk formats include the following: 

- monolithicSparse
- monolithicFlat
- vmfs
- twoGbMaxExtentSparse
- twoGbMaxExtentFlat

During the conversion process, this cmdlet converts the .vmdk files to .vhd files.
This cmdlet makes the operating system on the new virtual machine compatible with Hyper-V.
The virtual machine that this cmdlet creates matches VMware virtual machine properties unless these settings are explicitly overridden.
These properties include name, description, memory, and disk-to-bus assignment.
By default, the conversion process does not preserve network adapter settings.
You can explicitly set adapter settings on the target virtual machine.

This cmdlet supports the conversion of VMware virtual machines that are running any of the following guest operating systems: 

- Microsoft Windows 2000 Server with Service Pack 4 (SP4) or later versions
- Windows Server 2003 SP1 or later versions
- Windows Server 2003 R2 or later versions
- Windows Server 2008 or later versions
- Windows XP SP1 or later versions
- Windows Vista

Some conversions of a VMware-based virtual machine whose guest operating system is Windows might require that you add system files and drivers to the internal cache.
You can use the **Add-SCPatch** cmdlet to add the required files to the cache.
To determine what updates you must add, run **New-SCV2V** to attempt to convert the .vmdk file to a .vhd file.
If you need updates, this process puts the V2V conversion into a failed state.
You can review a list of required updates.
Next, use **Add-SCPatch** to add the updates to the internal cache, and then restart the failed V2V job.
The V2V process continues, so that you do not have to redo the disk conversion.

If you convert a VMware-based virtual machine that runs any other operating system, the virtual machine might not start or might not function correctly.
To guarantee a successful conversion, you must first modify the guest operating system to one of the supported operating systems.

For more information about how VMM converts .vmdk files directly, type `Get-Help Copy-SCVirtualHardDisk`.
For more information about how to add required files to the internal cache, type `Get-Help Add-SCPatch`.

## EXAMPLES

### Example 1: Convert a VMware-based virtual machine on an ESX host
```
PS C:\>$ESXHost = Get-SCVMHost -ComputerName "ESXHost01"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "HyperVHost01.Contoso.com"
PS C:\> $VM = Get-SCVirtualMachine -VMHost $ESXHost -Name "SourceVM"
PS C:\> New-SCV2V -VM $VM -VMHost $VMHost -Name "DestinationVM" -Path "C:\VMs" -MemoryMB 512 -RunAsynchronously
```

The first command gets the host named ESXHost01, and then stores that object in the $ESXHost variable.

The second command gets the host named HyperVHost01 in the Contoso.com domain, and then stores that object in the $VMHost variable.

The third command gets the virtual machine named SourceVM on ESXHost01, and then stores that object in the $VM variable.

In the last command**, New-SCV2V** performs the following operations: 

- Creates a Windows-based virtual machine named DestinationVM from the source VMware virtual machine named SourceVM.
The command deploys the new virtual machine, now named DestinationVM, onto HyperVHost01.
It stores the virtual machine files in the folder C:\VMs on HyperVHost01. 
- Assigns 512 MB of memory on HyperVHost01 for use by the new virtual machine. 
- Specifies the -*RunAsynchronously* parameter to return control to the command shell immediately, before the command finishes.

The command converts all of the virtual disks on the source virtual machine and attaches them to the new virtual machine.

### Example 2: Convert a VMware-based virtual machine stored in the VMM library
```
PS C:\>$LibServ = Get-SCLibraryServer -ComputerName "LibServer02.Contoso.com"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VirtualServerHost02.Contoso.com"
PS C:\> New-SCV2V -LibraryServer $LibServ -VMXPath "\\LibServer02\MSSCVMMLibrary\VMware\VMSource.vmx" -VMHost $VMHost -Name "VM02" -Path "C:\VMs" -MemoryMB 512 -RunAsynchronously
```

The first command gets the library server named LibServer02, and then stores that object in the $LibServ variable.

The second command gets the host named VirtualServerHost02, and then stores that object in the $VMHost variable.

In the last command, **New-SCV2V** performs the following operations: 

- Creates a Windows-based virtual machine named VM02 from the source VMware file, VMSource.vmx, stored at the specified path on FileServer02.
The command then deploys the new virtual machine named VM02 onto VirtualServerHost02.
The command stores the virtual machine files in the folder C:\VMs on VirtualServerHost02. 
- Assigns 512 MB of memory on VirtualServerHost02 for use by the new virtual machine. 
- Specifies the *RunAsynchronously* parameter to return control to the command shell immediately, before the command finishes.

## PARAMETERS

### -CPUCount
Specifies the number of CPUs on a virtual machine, on a hardware profile, or on a template.

Types of hosts support the following number of CPUs: 

- Hyper-V.
Up to four CPUs per virtual machine, depending on guest operating system
- VMware ESX.
Up to four CPUs per virtual machine, but only one CPU on a virtual machine that runs Windows NT 4.0
- Citrix XenServer.
Up to eight CPUs per virtual machine, depending on guest operating system

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: ProcessorCount

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPURelativeWeight
Specifies the amount of CPU resources on a host that this virtual machine can use relative to other virtual machines on the same host.
A virtual machine with a higher weight value is allocated more CPU resources than a virtual machine with a lower weight value.
The VMware term for these values is shares.

Types of hosts support the following relative values: 

- Hyper-V.
1 to 10000.
- VMware ESX.
High.
2000.
- VMware ESX.
Above Normal.
1500.
- VMware ESX.
Normal (default).
1000. 
- VMware ESX.
Below Normal.
750.
- VMware ESX.
Low.
500.
- VMware ESX.
Custom 1 to 1000000. 
- Citrix XenServer.
1 to 65536, normal is 256.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: RelativeWeight

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUType
Specifies the type of CPU for a virtual machine.
To retrieve a list of all CPU types that are available for use in virtual machines in a VMM environment, type `Get-SCCPUType`.

```yaml
Type: ProcessorType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DelayStartSeconds
Specifies the number of seconds to wait after the virtualization service starts before automatically starting a virtual machine.
You can use this delay to stagger the startup time of multiple virtual machines.
This technique helps reduce the demand on physical computer resources.
A typical setting might be 30 to 60 seconds.

Types of hosts have the following maximum configurable delays: 

- Hyper-V.
1000000000 seconds or 277777 hours. 
- VMware ESX.
65535 seconds or 18 hours. 
- Citrix XenServer.
Not applicable.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: DelayStart

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the converted virtual machine.

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

### -EnableMACAddressSpoofing
Indicates whether to enable Media Access Control (MAC) address spoofing.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: MACAddressesSpoofingEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableVMNetworkOptimization
Indicates whether to enable virtual machine network optimization.
Optimization improves network performance for virtual machines with network adapters that support virtual machine queue (VMQ) or TCP Chimney Offload.
VMQ enables you to create a unique network queue for each virtual network adapter.
TCP Chimney Offload enables network traffic processing to be offloaded from the networking stack.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: VMNetworkOptimizationEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

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
Specifies a variable in which job progress is tracked and stored.

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

### -LibraryServer
Specifies a VMM library server.
This cmdlet converts a virtual machine stored in the server that this parameter specifies.

```yaml
Type: LibraryServer
Parameter Sets: NoParse, Parse
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetwork
Specifies a logical network for the converted virtual machine.
A logical network is a named grouping of IP subnets and VLANs that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies the MAC address, or a set of MAC addresses, for a physical or virtual network adapter on a computer.
Valid values are: one or more MAC addresses.
Enter more than one MAC address as a comma separated list of strings.

```yaml
Type: String
Parameter Sets: (All)
Aliases: EthernetAddress, PhysicalAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddressType
Specifies the type of MAC address to use for a virtual network adapter.
Valid values are: Static and Dynamic.

```yaml
Type: String
Parameter Sets: (All)
Aliases: EthernetAddressType, PhysicalAddressType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMB
Specifies the amount of random access memory (RAM), in megabytes (MB), on the host that this cmdlet allocates to the converted virtual machine.
The default value is 512 MB.
For a virtual machine on which dynamic memory is enabled on a host that runs Windows Server 2008 R2 SP1 or later versions, specify the startup memory value.

Types of hosts have the following maximum memory assignable to virtual machines: 

- Hyper-V.
Up to 65536 MB RAM per virtual machine.
- VMware ESX Server 3.0.x.
Up to 16384 MB RAM per virtual machine.
- VMware ESX Server 3.5.x.
Up to 65532 MB RAM per virtual machine.
- Citrix XenServer.
Up to 32265 MB RAM per virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the converted virtual machine.

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

### -NetworkLocation
Specifies the network location for a physical network adapter or for a virtual network adapter, or a new default network location of a host physical network adapter.

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

### -NetworkTag
Specifies a word or phrase to associate with a virtual network adapter that is configured to connect to a specific internal or external network on the host.

The network tag identifies all virtual machines with the same network tag as members of the same network.
VMM uses a network tag, if one exists, when it evaluates hosts as possible candidates on which to deploy a virtual machine.
If the host does not include virtual machines on the network that has the same network tag as the virtual machine to be placed, the host receives zero stars in the placement process.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoConnection
Indicates that this cmdlet disconnects a virtual network adapter from a virtual network for the converted virtual machine.

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

### -OverridePatchPath
Do not specify this parameter.
For internal use only.

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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.

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
Specifies the destination path for the virtual machine conversion.
This parameter accepts the wildcard (*) when you specify a UNC path.

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

### -SkipInstallVirtualizationGuestServices
Indicates that this cmdlet skips the installation of virtualization guest services on a virtual machine.

By default, VMM installs the appropriate virtualization guest service automatically.
For a virtual machine on a Hyper-V host, the virtualization guest service is called Integration Components (VMGuest.iso).
For a virtual machine on a XenServer host, the virtualization guest service is called Citrix Tools for Virtual Machines (xs-tools.iso).
Virtual machines on a VMware ESX host do not use a virtualization guest service.

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

### -SourceNetworkConnectionID
Specifies the MAC address or network name of the physical network adapter that this cmdlet converts into a virtual network adapter in the virtual machine.

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

### -StartAction
Specifies the behavior of a virtual machine when the virtualization service starts.
The acceptable values for this parameter are:

- AlwaysAutoTurnOnVM
- NeverAutoTurnOnVM
- TurnOnVMIfRunningWhenVSStopped

```yaml
Type: VMStartAction
Parameter Sets: (All)
Aliases: 
Accepted values: NeverAutoTurnOnVM, AlwaysAutoTurnOnVM, TurnOnVMIfRunningWhenVSStopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartVM
Indicates that the virtual machine starts when it arrives at the destination host.

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

### -StopAction
Specifies the behavior of the virtual machine when the virtualization service stops.
The acceptable values for this parameter are:

- SaveVM
- TurnOffVM
- ShutdownGuestOS

```yaml
Type: VMStopAction
Parameter Sets: (All)
Aliases: 
Accepted values: SaveVM, TurnOffVM, ShutdownGuestOS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trigger
Indicates that this cmdlets runs the commands in a job group for a physical-to-virtual (P2V) conversion, a virtual-to-virtual (V2V) conversion, or the conversion of a physical hard disk to a virtual hard disk.

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

### -UserRole
Specifies a user role for the converted virtual machine.

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

### -VLanEnabled
Indicates whether to enable a virtual LAN (VLAN) for use by virtual machines on a Hyper-V or Citrix XenServer host.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VLanID
Specifies a numeric identifier for a virtual network adapter on a virtual machine or for a physical network adapter on a virtual machine host.
Valid values are integers from 1 to 4094.
Configure a VLan ID for a Hyper-V, VMware ESX, or Citrix XenServer host on an externally bound physical network adapter when the VLan mode is Access.
Configure a VLan ID on a virtual network adapter of a virtual machine that is bound to a physical network adapter on the host, or that is bound to an internal virtual network on the host.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object that this cmdlet converts.

```yaml
Type: VM
Parameter Sets: FromVM
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
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server that manages the converted virtual machine.

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

### -VMNetwork
Specifies a virtual machine network object.
To obtain a virtual machine network object, use the Get-SCVMNetwork cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMXComputerConfiguration
Specifies a VMX computer configuration.

```yaml
Type: VmxMachineConfiguration
Parameter Sets: NoParse
Aliases: MachineConfig, VMXMachineConfig

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMXPath
Specifies the full UNC path of the .vmx file of a VMware virtual machine.

```yaml
Type: String
Parameter Sets: Parse
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network for the converted virtual machine.

```yaml
Type: VirtualNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapter
Specifies a virtual network adapter object for a virtual machine.

Types of hosts support the following number of virtual network adapters: 

 -- Hyper-V. 
Up to four emulated adapters per virtual machine.
There is no driver available for an emulated network adapter on a Windows Server 2003 x64 guest operating system.

- Hyper-V. 
Up to eight synthetic adapters per virtual machine.
- VMware ESX. 
Up to four emulated adapters per virtual machine.
- Citrix XenServer. 
Up to seven emulated adapters per virtual machine.

```yaml
Type: VirtualNetworkAdapter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualMachine
This cmdlet returns a **VirtualMachine** object.

## NOTES
* This cmdlet requires a VMM VMX computer configuration object. To obtain a VMX object, use the Get-SCVMXComputerConfiguration cmdlet.

## RELATED LINKS

[Copy-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Copy-SCVirtualHardDisk.md)

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[New-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetwork.md)

[Get-SCCPUType](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCPUType.md)

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

