---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 28FE2E7A-2E73-4324-81BD-0C4D8C8059D5
updated_at: 12/22/2016 5:13 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCHardwareProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCHardwareProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17600c3a31aaf782880f045fab1671fdd067cc23/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCHardwareProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCHardwareProfile

## SYNOPSIS
Changes the properties of a hardware profile used in VMM.

## SYNTAX

```
Set-SCHardwareProfile [-HardwareProfile] <HardwareProfile> [-HighlyAvailable <Boolean>]
 [-HAVMPriority <UInt32>] [-DRProtectionRequired <Boolean>] [-ReplicationGroup <ReplicationGroup>]
 [-SecureBootEnabled <Boolean>] [-NumLock <Boolean>] [-CPULimitFunctionality <Boolean>]
 [-CPULimitForMigration <Boolean>] [-Name <String>] [-RemoveCapabilityProfile] [-Owner <String>]
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
The **Set-SCHardwareProfile** cmdlet changes one or more properties of a hardware profile object used in a Virtual Machine Manager (VMM) environment.
Properties that you can change include settings for boot order, CPU settings, the amount memory on the host that is assigned to a virtual machine, and other options.

To change the properties of a virtual floppy drive, virtual DVD drive, virtual COM port, virtual network adapter, or virtual SCSI adapter associated with a specific hardware profile, use the **Set-SCVirtualFloppyDrive**, **Set-SCVirtualDVDDrive**, **Set-SCVirtualCOMPort**, **Set-SCVirtualNetworkAdapter**, or **Set-SCVirtualScsiAdapter** cmdlets, respectively.

Changes made to a hardware profile affect only the hardware profile itself.
The changes do not affect any existing virtual machines that were created by using this profile.

## EXAMPLES

### Example 1: Specify an amount of memory for an existing hardware profile
```
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> Set-SCHardwareProfile -HardwareProfile $HWProfile -MemoryMB 1024
```

The first command gets the hardware profile object named NewHWProfile01 and stores the object in the $HWProfile variable.

The second command changes the memory value for NewHWProfile01 to 1024 MB.

### Example 2: Specify a new owner for multiple hardware profiles
```
PS C:\> $HWProfiles = Get-SCHardwareProfile | where {$_.Name -match "Profile"}
PS C:\> ForEach ($HWProfile in $HWProfiles) {Set-SCHardwareProfile -HardwareProfile $HWProfile -Owner "Contoso\Cesar"}
```

The first command gets the hardware profile objects that match the search criteria and stores the objects in the $HWProfiles object array.

The second command uses a **ForEach** statement to specify a new owner for each of the profiles in the array.

For more information about the standard PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

### Example 3: Specify a new boot order for multiple hardware profiles
```
PS C:\> $HWProfiles = @(Get-SCHardwareProfile | where {$_.Name -match "HWProfile"})
PS C:\> ForEach ($HWProfile in $HWProfiles) {Set-SCHardwareProfile -HardwareProfile $HWProfile -BootOrder PXEBoot,CD,IDEHardDrive,Floppy}
```

The first command gets all hardware profile objects the library that match the search criteria (the profile name contains the string "HWProfile") and stores the hardware profile objects in the $HWProfiles object array.
Using the @ symbol and parentheses ensures that the command stores the results in an array, in case the command returns a single object or a $Null value.

The second command uses a **ForEach** statement to specify a new boot order for each hardware profile object in the $HWProfiles array.

### Example 4: Search for hardware profiles with a specific configuration and append text to the description field
```
PS C:\> $HWProfiles = @(Get-SCHardwareProfile | where {$_.CPUCount -eq 4})
PS C:\> ForEach ($HWProfile in $HWProfiles) {$Text = $HWProfile.Description; Set-SCHardwareProfile -HardwareProfile $HWProfile -Description $Text" (Contains four Processors)"}
```

The first command gets all hardware profile objects that match the search criteria (CPU count is equal to 4) and stores the hardware profile objects in the $HWProfiles object array.

The second command uses a **ForEach** statement to iterate through each profile object in the $HWProfiles array.
For each profile, the description text is stored to a variable ($Text), and then the **Set-SCHardwareProfile** cmdlet uses the *Description* parameter to append "(Contains four Processors)" to the contents of each instance of $Text.

### Example 5: Enable Dynamic Memory for an existing hardware profile
```
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile05" }
PS C:\> Set-SCHardwareProfile -HardwareProfile $HWProfile -DynamicMemoryEnabled $True -MemoryMB 1024 -DynamicMemoryMaximumMB 2048
```

The first command gets the hardware profile object named NewProfile5 and stores the object in the $HWProfile variable.

The second command enables dynamic memory for NewHWProfile05, changes the startup memory value to 1024 MB and sets the maximum memory value to 2048 MB.

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
Specifies the order, as an array, of devices that a virtual machine on a Hyper-V host uses to start.
Valid values are: 

- CD
- IDEHardDrive
- PXEBoot
- Floppy

Example format: `-BootOrder PXEBoot,IDEHardDrive,CD,Floppy`

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
Normal (default). 1000. 

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

Example:  `-DiskIO 1500` (to specify 1500 IOPS)

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
Enabling dynamic memory on a virtual machine stored in a library will limit placement of that machine to hosts running Windows Server 2008 SP1 or later.

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

Example format: `-DynamicMemoryMinimumMB 1024`

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
Specifies the device on which a boot is first attempted.

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

Required: True
Position: 0
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

Required: False
Position: Named
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

- Example format: `-Owner "Contoso\PattiFuller"`
- Example format: `-Owner "PattiFuller@Contoso"`

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

### -RemoveCapabilityProfile
Removes one or more specified capability profile objects.

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

### -ReplicationGroup
Specifies a **ReplicationGroup** object.

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
Indicates whether secure boot is enabled.

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
Specifies a secure boot template.

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

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHardwareProfile.md)

[New-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCHardwareProfile.md)

[Remove-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCHardwareProfile.md)

