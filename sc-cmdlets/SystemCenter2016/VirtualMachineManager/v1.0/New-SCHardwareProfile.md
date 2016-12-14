---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: FD4329B3-6A2D-415D-B581-FAF9214E83D7
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCHardwareProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCHardwareProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCHardwareProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCHardwareProfile

## SYNOPSIS
Creates a hardware profile in the VMM library.

## SYNTAX

```
New-SCHardwareProfile [-VMMServer <ServerConnection>] [-Generation <Int32>] [-HighlyAvailable <Boolean>]
 [-HAVMPriority <UInt32>] [-DRProtectionRequired <Boolean>] [-ReplicationGroup <ReplicationGroup>]
 [-SecureBootEnabled <Boolean>] [-NumLock <Boolean>] [-CPULimitFunctionality <Boolean>]
 [-CPULimitForMigration <Boolean>] [-Name] <String> [-HardwareProfile <HardwareProfile>] [-Owner <String>]
 [-UserRole <UserRole>] [-JobGroup <Guid>] [-CapabilityProfile <CapabilityProfile>] [-Description <String>]
 [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>]
 [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>]
 [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>] [-RecoveryPointObjective <Int32>]
 [-ProtectionProvider <ProtectionProvider>] [-BootOrder <BootDevice[]>] [-FirstBootDevice <String>]
 [-SecureBootTemplate <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPUExpectedUtilizationPercent <Int32>] [-DiskIops <Int32>] [-NetworkUtilizationMbps <Int32>]
 [-CPURelativeWeight <Int32>] [-CPUReserve <Int32>] [-CPUMaximumPercent <Int32>]
 [-CPUPerVirtualNumaNodeMaximum <Byte>] [-MemoryPerVirtualNumaNodeMaximumMB <Int32>]
 [-VirtualNumaNodesPerSocketMaximum <Byte>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCHardwareProfile** cmdlet creates a hardware profile for use in Virtual Machine Manager (VMM) that stores hardware configuration information.
You can create a standalone hardware profile or customize a template or virtual machine to include hardware profile settings.
**New-SCHardwareProfile** stores the new hardware profile object in the VMM library.

You can create a hardware profile based on defaults or an existing hardware profile, or, you can customize a hardware profile as you create it.
If you specify no parameters other than *Name*, which is required, VMM creates a default hardware profile object.

Hardware profile settings that you can configure for a virtual machine include: 


- Boot order settings in the BIOS that specify the device startup order for a virtual machine.
The boot order setting is available only for virtual machines on a Hyper-V host or Citrix XenServer host. 

- CPU settings for a virtual machine. 

- Memory available on a virtual machine. 

- A virtual floppy drive. 

- Two virtual COM ports (COM1 and COM2). 

- A built-in virtual IDE device. 

- One or more virtual SCSI adapters. 


- One or more virtual network adapters that you can attach to a logical network.
A virtual network adapter can be emulated or synthetic. 


- The priority assigned to a virtual machine for using the host's CPU resources relative to the use of the host's CPU by other virtual machines deployed on the same host.
CPU priorities are determined by the virtualization software. 


- Whether a virtual machine created from this profile will be highly available.
A highly available virtual machine is a virtual machine that can only be placed on a host that is part of a host cluster.

## EXAMPLES

### Example 1: Create a default hardware profile
```
PS C:\>New-SCHardwareProfile -Name "NewHWProfile01"
```

This command creates a default hardware profile named NewHWProfile01.

### Example 2: Create a hardware profile that sets boot order, CPU, and memory
```
PS C:\>New-SCHardwareProfile -Name "NewHWProfile02" -BootOrder PXEBoot,CD,Floppy,IDEHardDrive -MemoryMB 1024 -CPUCount 4
```

This command creates a new hardware profile, names it NewHWProfile02, sets PXEBoot as the first entry in the BIOS boot order, specifies 1024 MB of memory, and specifies that a virtual machine created by using this hardware profile will have four processors.

### Example 3: Clone and then modify an existing hardware profile
```
PS C:\>$HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> New-SCHardwareProfile -Name "NewHWProfile03" -HardwareProfile $HWProfile -RelativeWeight 100
```

The first command gets the hardware profile object named NewHWProfile01 and stores the object in the $HWProfile variable.

The second command creates a hardware profile called NewHWProfile03 based on NewHWProfile01, but modifies the value for relative weight.
All other settings in NewHWProfile03 are identical to those in NewHWProfile01.

### Example 4: Create a hardware profile that contains a network adapter, a SCSI adapter, and a DVD drive
```
PS C:\>$JobGroupId = [Guid]::NewGuid().ToString()
PS C:\> New-SCVirtualNetworkAdapter -JobGroup $JobGroupID -PhysicalAddressType Dynamic -VirtualNetwork "Internal Network" 
PS C:\> New-SCVirtualSCSIAdapter -JobGroup $JobGroupID -AdapterID 6 -Shared $False
PS C:\> New-SCVirtualDVDDrive -JobGroup $JobGroupID -Bus 1 -LUN 0
PS C:\> New-SCHardwareProfile -Name "NewHWProfile04" -Owner "Contoso\Katarina" -Description "Temporary Hardware Config used to create a VM/Template" -MemoryMB 512 -JobGroup $JobGroupID
```

The first command generates a globally unique identifier (GUID) and stores the GUID string in variable $JobGroupID.
The job group ID functions as an identifier that groups subsequent commands that include this identifier into a single job group.

The second command creates a virtual network adapter but uses the *JobGroup* parameter to specify that the network adapter is not created until just before the **New-SCHardwareProfile** cmdlet in the last command runs.
This command sets the physical (MAC) address type to dynamic and specifies that the new virtual network adapter will connect to a virtual network named Internal Network.

The third command creates a virtual SCSI adapter but uses the *JobGroup* parameter to specify that the SCSI adapter is not created until just before the **New-SCHardwareProfile** cmdlet in the last command runs.
This command sets the adapter ID to 6, and it sets the *Shared* parameter to $False so that the adapter is not shared (as it would have had to be if you wanted to use the adapter in guest clustering).

The fourth command creates a virtual DVD drive but uses the *JobGroup* parameter to specify that the DVD drive is not created until just before the **New-SCHardwareProfile** cmdlet in the last command runs.
Specifying Bus 1 and LUN 0 attaches the virtual DVD drive to Secondary Channel (0) on the IDE bus.

The last command creates a hardware profile named NewHWProfile04, sets the owner to Contoso\Katarina, specifies a description, and specifies that the amount of memory on the host that a virtual machine created by using this hardware profile will use is 512 MB.
Before the **New-SCHardwareProfile** cmdlet creates the hardware profile, the *JobGroup* parameter in this final command executes all of the preceding cmdlets that specify the same *JobGroup* GUID.
When New-SCVirtualNetworkAdapter, New-SCVirtualScsiAdapter, and New-SCVirtualDVDDrive run, the resulting objects that are created are automatically associated with the new hardware profile.

### Example 5: Create a hardware profile and add it to a new virtual machine template
```
PS C:\>$HWProfile = New-SCHardwareProfile -Name "NewHWProfile05" -CPUCount 4 -MemoryMB 64000 -CPUMax 100 -Owner "Contoso\Katarina" -HighlyAvailable $True 
PS C:\> $VHD = Get-SCVirtualHardDisk | where { $_.Name -eq "VHD01.vhd"  -and $_.LibraryServer.Name -eq "LibServer01.Contoso.com" }
PS C:\> $OS = Get-SCOperatingSystem | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Datacenter"}
PS C:\> New-SCVMTemplate -Name "LargeVMTemplate" -HardwareProfile $HWProfile -OperatingSystem $OS -VirtualHardDisk $VHD -NoCustomization
```

The first command creates a new hardware profile, names it NewHWProfile05, specifies that it contains four processors, and that the highest percentage of the total resources of a single CPU on a host that can be used by a virtual machine is 100 percent, assigns 64 GB of RAM and an owner, sets the *HighlyAvailable* parameter to $True, and then stores the new hardware profile object in the $HWProfile variable.
The *HighlyAvailable* parameter specifies that a virtual machine created by using this hardware profile, either directly or through a template, will be placed on a host that is a node of a host cluster.

The second command gets the virtual hard disk object nameed VHD01 from the library and stores the object in the $VHD variable.

The third command gets an operating system object by name and stores the object in the $OS variable.

The last command creates a new virtual machine template, names it LargeVMTemplate, and specifies that it use the operating system, hardware profile, and virtual hard disk retrieved or created in the preceding commands, without any customization to the operating system.

## PARAMETERS

### -AutomaticCriticalErrorAction
Specifies the action to take when the VM encounters a critical error, and exceeds the timeout duration specified by the *AutomaticCriticalErrorActionTimeout* parameter.
The acceptable values for this parameter are: Pause and None.

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

### -AutomaticCriticalErrorActionTimeout
Specifies the amount of time, in minutes, to wait in critical pause before powering off the virtual machine.

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

### -BootOrder
Specifies the order of devices that a virtual machine on a Hyper-V host uses to start.
The acceptable values for this parameter are:

- CD
- IDEHardDrive
- PXEBoot
- Floppy

```yaml
Type: BootDevice[]
Parameter Sets: (All)
Aliases: 
Accepted values: Floppy, CD, IdeHardDrive, PxeBoot, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUCount
Specifies the number of CPUs on a virtual machine, on a hardware profile, or on a template.

Types of hosts support the following number of CPUs: 

- Hyper-V.
Up to four CPUs per virtual machine, depending on guest operating system.
- VMware ESX.
Up to four CPUs per virtual machine, but only one CPU on a virtual machine that runs Windows NT 4.0.
- Citrix XenServer.
Up to eight CPUs per virtual machine, depending on guest operating system.

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

### -CPUExpectedUtilizationPercent
Specifies the percent of CPU on the host that you expect this virtual machine to use.
This value is used only when VMM determines a suitable host for the virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ExpectedCPUUtilization

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPULimitForMigration
Indicates whether to limit processor features for the specified virtual machine in order to enable migration to a physical computer that has a different version of the same processor as the source computer.
VMM does not support migrating virtual machines between physical computers that have processors from different manufacturers.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: LimitCPUForMigration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPULimitFunctionality
Indicates whether to enable running an older operating system such as Windows NT 4.0 on a virtual machine deployed on a Hyper-V host or on a VMware ESX host by providing limited CPU functionality for the virtual machine.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: LimitCPUFunctionality

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUMaximumPercent
Specifies the highest percentage of the total resources of a single CPU on the host that can be used by a specific virtual machine at any given time.

Example: `-CPUMaximumPercent 80` (to specify 80 per cent)

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: CPUMax

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUPerVirtualNumaNodeMaximum
Specifies the maximum number of CPUs allowed for each virtual NUMA node.

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

### -CPUReserve
Specifies the minimum percentage of the resources of a single CPU on the host to allocate to a virtual machine.
The percentage of CPU capacity that is available to the virtual machine is never less than this percentage.

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

### -CapabilityProfile
Specifies a capability profile object.

```yaml
Type: CapabilityProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CheckpointType
Specifies the Checkpoint type.
The acceptable values for this parameter are:

- Disabled 
- Production 
- ProductionOnly 
- Standard

```yaml
Type: CheckpointType
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, Production, ProductionOnly, Standard

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DRProtectionRequired
This parameter is reserved for future use.

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

### -Description
States a description for the specified object.

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

### -DiskIops
Specifies the number of disk input/output operations per second (IOPS) on the host that can be used by a specific virtual machine.

Example: `-DiskIO 1500` (to specify 1500 IOPS)

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: DiskIO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicMemoryBufferPercentage
Specifies the percentage of memory above a virtual machine's current memory allocation which the host should try to reserve as a buffer.
The default value is 20.

Example format: `-DynamicMemoryTargetBufferPercentage 20`

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

### -DynamicMemoryEnabled
Indicates whether to enable dynamic memory for virtual machines.
You can enable dynamic memory directly on a virtual machine, or on a template or hardware profile that will be used to create virtual machines.
The default value is $False.

Required: You can enable dynamic memory for a virtual machine only if that virtual machine is deployed on a host running Windows Server 2008 SP1 or later or if the virtual machine is stored in a library in a stopped state (hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots).
Enabling dynamic memory on a virtual machine stored in a library limits placement of that machine to hosts running Windows Server 2008 SP1 or later.

Example format: `-DynamicMemoryEnabled $True`

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

### -DynamicMemoryMaximumMB
Specifies the maximum amount of memory that can be allocated to a virtual machine if dynamic memory is enabled.
The default value is 65536.

Required: You can enable dynamic memory for a virtual machine only if that virtual machine is deployed on a host running Windows Server 2008 R2 SP1 or later or if the virtual machine is stored in a library in a stopped state (hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots).
Enabling dynamic memory on a virtual machine stored in a library will limit placement of that machine to hosts running Windows Server 2008 R2 SP1 or later.

Example format: `-DynamicMemoryMaximumMB 1024`

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

### -DynamicMemoryMinimumMB
Specifies the minimum amount of memory that can be allocated to a virtual machine if dynamic memory is enabled.
The default value is 65536.

Required: You can enable dynamic memory for a virtual machine only if that virtual machine is deployed on a host running Windows Server 2008 R2 SP1 or later or if the virtual machine is stored in a library in a stopped state (hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots).
Enabling dynamic memory on a virtual machine stored in a library will limit placement of that machine to hosts running Windows Server 2008 R2 SP1 or later.

Example format: ` -DynamicMemoryMinimumMB 1024`

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

### -FirstBootDevice
Indicates the device on which a boot is first attempted.

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

### -Generation
Indicates the generation of virtual machine that is created.

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

### -HAVMPriority
Specifies the virtual machine priority.
Virtual machines start in priority order up to the limits of a host cluster node.
Valid input for this parameter is a numeric representation of the priority: 

- High.
3000
- Medium.
2000 
- Low.
1000 

If you specify a value of zero (0), the virtual machine does not restart automatically.

Example format: `-HAVMPriority 2000`

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HighlyAvailable
Indicates whether to place a virtual machine on a Hyper-V host that is part of a host cluster.
Configure this setting on a virtual machine, or on a template or hardware profile that will be used to create virtual machines.

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

### -MemoryPerVirtualNumaNodeMaximumMB
Specifies the maximum amount of memory, in MB, that each virtual NUMA node is allowed.

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

### -MemoryWeight
Indicates the priority in allocating memory to a virtual machine, relative to other virtual machines on the same host.
A virtual machine with a higher setting is allocated more memory resources than a virtual machine with a lower setting.

For a host running Windows Server 2008 R2 SP1 or later: 

- 5000 - Normal
- 10000 - High
- 0 - Low
- 1 to 10000 - Custom

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

### -MonitorMaximumCount
Specifies the maximum number of monitors that a virtual video adapter supports.

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

### -MonitorMaximumResolution
Specifies the value, as a string, that represents the maximum possible monitor resolution of a virtual video adapter.
The acceptable values for this parameter are:

- 1024x768
- 1280x1024
- 1600x1200
- 1920x1200

The default value is 1280x1024.

Example format: `-MonitorResolutionMaximum "1600x1200"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: MonitorResolutionMaximum

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

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkUtilizationMbps
Specifies, in megabits per second (Mbps), the amount of bandwidth on the host's network that can be used by a specific virtual machine. 



Example format: `-NetworkUtilization 10`

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: NetworkUtilization

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumLock
Indicates whether to enable the BIOS value for NumLock on a hardware profile that is used to create virtual machines on a Hyper-V host.
This parameter does not apply to virtual machines on VMware ESX hosts, or on Citrix XenServer hosts.

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

### -NumaIsolationRequired
Indicates whether NUMA isolation is required.

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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account. 



Example format: `-Owner "Contoso\PattiFuller"`

Example format: `-Owner "PattiFuller@Contoso"`

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

### -ProtectionProvider
Specifies a protection provider.

```yaml
Type: ProtectionProvider
Parameter Sets: (All)
Aliases: 
Accepted values: None, HVR8, HVRBlue, HVRAzure, DiskReplication, SANReplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPointObjective
Specifies the maximum period for which it is tolerable to lose data from an IT service due to a major incident.

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

### -ReplicationGroup
Specifies a replication group.

```yaml
Type: ReplicationGroup
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

### -SecureBootEnabled
Indicates whether secure booting is enabled.

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

### -SecureBootTemplate
Specifies the secure boot template to be used for the Generation 2 virtual machine.

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

### -UserRole
Specifies a user role object.

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

### -VirtualNumaNodesPerSocketMaximum
Specifies the maximum number of NUMA nodes allowed for each socket.

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

### -VirtualVideoAdapterEnabled
Indicates whether to enable the Microsoft Synthetic 3D Virtual Video Adapter for virtual machines.
You can enable the Virtual Video Adapter directly on a virtual machine, or on a template or hardware profile that will be used to create virtual machines.

Required: You can enable the Microsoft Synthetic 3D Virtual Video Adapter for a virtual machine only if that virtual machine is deployed on a host running Windows Server 2008 R2 SP1 (with the Remote Desktop Services role and Remote Desktop Virtual Graphics role service installed) or later or if the virtual machine is stored in a library in a stopped state (hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots).
Enabling the Microsoft Synthetic 3D Virtual Video Adapter on a virtual machine stored in a library will limit placement of that machine to hosts running Windows Server 2008 R2 SP1 (with the Remote Desktop Services role and Remote Desktop Virtual Graphics role service installed) or later.

Example format: `-VirtualVideoAdapterEnabled $True`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### HardwareProfile
This cmdlet returns a **HardwareProfile** object.

## NOTES

## RELATED LINKS

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCHardwareProfile.md)

[Get-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCOperatingSystem.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualHardDisk.md)

[New-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVirtualDVDDrive.md)

[New-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVirtualNetworkAdapter.md)

[New-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVirtualScsiAdapter.md)

[New-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMTemplate.md)

[Remove-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCHardwareProfile.md)

[Set-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCHardwareProfile.md)

