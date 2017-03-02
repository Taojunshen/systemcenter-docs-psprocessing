---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 666B38CD-CACC-49BC-8A92-AE69057D570C
updated_at: 12/22/2016 5:13 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17600c3a31aaf782880f045fab1671fdd067cc23/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVirtualMachine

## SYNOPSIS
Changes properties of a virtual machine managed by VMM.

## SYNTAX

```
Set-SCVirtualMachine [-VM] <VM> [-VMwareResourcePool <VmwResourcePool>] [-StartAction <VMStartAction>]
 [-StopAction <VMStopAction>] [-RemoveSelfServiceUserRole <Boolean>] [-EnableOperatingSystemShutdown <Boolean>]
 [-EnableTimeSync <Boolean>] [-EnableDataExchange <Boolean>] [-EnableHeartbeat <Boolean>]
 [-EnableBackup <Boolean>] [-InstallVirtualizationGuestServices <Boolean>] [-Owner <String>]
 [-OperatingSystem <OperatingSystem>] [-Enabled <Boolean>] [-HighlyAvailable <Boolean>]
 [-HAVMPriority <UInt32>] [-DRProtectionRequired <Boolean>] [-ReplicationGroup <ReplicationGroup>]
 [-SecureBootEnabled <Boolean>] [-NumLock <Boolean>] [-CPULimitFunctionality <Boolean>]
 [-CPULimitForMigration <Boolean>] [-VMShieldingData <KeyFile>] [-RunAsSystem]
 [-RunAsUserCredential <PSCredential>] [-DelayStartSeconds <Int32>]
 [-UseHardwareAssistedVirtualization <Boolean>] [-Cloud <Cloud>] [-CapabilityProfile <CapabilityProfile>]
 [-RemoveCapabilityProfile] [-RemoveFromCloud]
 [-ClusterNonPossibleOwner <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.Host]>]
 [-ClusterPreferredOwner <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.Host]>]
 [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>] [-UserRole <UserRole>]
 [-Name <String>] [-JobGroup <Guid>] [-QuotaPoint <UInt32>] [-CostCenter <String>] [-Tag <String>]
 [-Custom1 <String>] [-Custom2 <String>] [-Custom3 <String>] [-Custom4 <String>] [-Custom5 <String>]
 [-Custom6 <String>] [-Custom7 <String>] [-Custom8 <String>] [-Custom9 <String>] [-Custom10 <String>]
 [-BlockDynamicOptimization <Boolean>] [-ClearDRProtection] [-Description <String>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-RecoveryPointObjective <Int32>]
 [-ProtectionProvider <ProtectionProvider>] [-BootOrder <BootDevice[]>] [-FirstBootDevice <String>]
 [-SecureBootTemplate <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPUExpectedUtilizationPercent <Int32>] [-DiskIops <Int32>] [-NetworkUtilizationMbps <Int32>]
 [-CPURelativeWeight <Int32>] [-CPUReserve <Int32>] [-CPUMaximumPercent <Int32>]
 [-CPUPerVirtualNumaNodeMaximum <Byte>] [-MemoryPerVirtualNumaNodeMaximumMB <Int32>]
 [-VirtualNumaNodesPerSocketMaximum <Byte>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualMachine** cmdlet changes properties of a virtual machine managed by Virtual Machine Manager (VMM).

Properties that you can change include the following: 

- Associate a virtual machine to a cloud. 
- Name, owner, and description of a virtual machine. 
- BIOS boot order, if the virtual machine is deployed on a Hyper-V host. 
- Amount of resources on the host used by a virtual machine.
These include the following: 
 - Maximum amount of host CPU resources that a virtual machine can use. 
 - Expected use of host CPU by a virtual machine. 
 - Amount of host CPU resources used by one virtual machine relative to other virtual machines on the same host. 
 - Amount of host memory that a virtual machine can use. 
 - Amount of bandwidth on the host's network that a virtual machine can use. 
- Hardware settings for a virtual machine unrelated to host resources.
These include the following: 
 - Number of CPUs. 
 - Type of CPU. 
 - Number of disk input/output operations per second (IOPS). 
 - Limiting CPU functionality, for an older operating system,   such as Windows NT 4.0. 
- Cost center, tag, and custom settings that are used to filter virtual machines by criteria. 
- Settings that enable various optional capabilities, which include the following: 
 - Enabling or disabling a library object to make it available,  or temporarily unavailable, to users. 
 - Enabling backing up a virtual machine on a Hyper-V host with Volume Shadow Copy  service. 
 - Enabling a key/value pair for data exchange between a virtual machine and its Hyper-V host. 
 - Enabling shutdown of a virtual machine from the Hyper-V console. 
 - Enabling time synchronization between a virtual machine and its Hyper-V host. 
 - Enabling the BIOS value for NumLock for a virtual machine on a Hyper-V host. 
- Setting that identifies whether a virtual machine is highly available, that is, a virtual machine to be deployed on a node of a Hyper-V host cluster or a Citrix  XenServer host cluster. 
- Setting that determines whether virtualization guest services are installed on a virtual machine deployed on a Hyper-V host. 
- Number of seconds to delay before starting a virtual machine. 
- Setting that identifies the operating system that is used for a virtual machine. 
- Start and stop actions for a virtual machine. 
- Setting that limits the number of virtual machines self-service users can create. 
- Setting used to switch the role that a self-service user who belongs to multiple roles uses to manage a virtual machine. 
- Setting that assigns a virtual machine on an ESX host to a VMware resource pool.

If you want to change the properties of a virtual floppy drive, virtual DVD drive, virtual network adapter, or virtual SCSI adapter associated with a specific virtual machine, use the **Set-SCVirtualFloppyDrive**, **Set-SCVirtualDVDDrive**, **Set-SCVirtualNetworkAdapter**, or **Set-SCVirtualScsiAdapter** cmdlet.

## EXAMPLES

### Example 1: Specify an amount of memory for an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> If($VM.Status -ne "PowerOff"){Stop-SCVirtualMachine -VM $VM}
PS C:\> Set-SCVirtualMachine -VM $VM -MemoryMB 1024
```

The first command gets the virtual machine object named VM01, and then stores that object in the $VM variable.

The second determines whether the virtual machine stored in $VM is in a powered off state.
If the virtual machine is not in a powered off state, the command uses the Stop-SCVirtualMachine command to power off the virtual machine.
For more information about powering off a virtual machine, type `Get-Help Stop-SCVirtualMachine`.

The last command changes the memory allocated to VM01 to 1024 MB.

### Example 2: Change the user role used to manage a virtual machine for a user who belongs to multiple self-service user roles
```
PS C:\> $VM = Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" -Name "VM02"
PS C:\> $SSRole = Get-SCUserRole -Name "ContosoSelfServiceUsers"
PS C:\> Set-SCVirtualMachine -VM $VM -UserRole $SSRole
```

The first command gets the virtual machine object named VM02 from VMMServer01, and then stores that object in the $VM variable.

The second command gets the user role object named ContosoSelfServiceUsers, and then stores the object in the $SSRole variable.

The last command specifies that members of the self-service user role called SSUserRole3 are now granted the permission to manage the virtual machine called VM02.

Note: VMM uses the *UserRole* parameter to set which virtual machines are managed by the members of a specific self-service user role.
Typically, you do not have to use the **Set-SCVirtualMachine** cmdlet with the *UserRole* parameter to configure this setting.
However, if one or more users are members of multiple self-service user roles and you grant them permission to manage multiple virtual machines on the same host, you might encounter a case where you want to switch which user role is authorized to manage a particular virtual machine.
This example illustrates that scenario.

### Example 3: Disable time syncronization on a virtual machine used as a domain controller
```
PS C:\> $EAP = $ErrorActionPreference
PS C:\> $ErrorActionPreference = "STOP" 
PS C:\> $VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> trap{"Fail: Cannot disable Time Synchronization for VM: $VM";continue} Set-SCVirtualMachine -VM $VM -EnableTimeSynchronization $TRUE | Out-Null
PS C:\> $ErrorActionPreference = $EAP
```

The first command stores the current setting for $ErrorActionPreference in variable $EAP.
This variable is used later to return the setting to its original value.

The second command sets the action preference to STOP.
This error action preference changes an error from a non-terminating error to a terminating error.
The error object is raised as an exception instead of being written to the output pipe, and the command does not continue to run.

The third command gets the virtual machine object named VM03, and stores that object in the $VM variable.

The fourth command disables the time synchronization setting.
Typically, disabling time synchronization is required for virtual machines that act as domain controllers.
The command uses the **trap** statement to catch terminating exceptions.
If the **Set-SCVirtualMachine** command fails, the string in the **trap** statement is displayed.
Continue is used in the **trap** statement to continue running instead of exiting.
The Out-Null cmdlet redirects the output to $Null instead of sending it to the console.

The last command sets the value for $ErrorActionPreference to the value stored in $EAP.

### Example 4: Set the device start order for all virtual machines that support this feature
```
PS C:\> $EAP = $ErrorActionPreference
PS C:\> $ErrorActionPreference = "Stop" 
PS C:\> $VMs = @(Get-SCVirtualMachine)
PS C:\> ForEach($VM in $VMs){trap{"Fail: Cannot set BIOS for VM: $VM";continue} Set-SCVirtualMachine -VM $VM -BootOrder "PXEBoot","IDEHarddrive","CD","Floppy" | Out-Null}
PS C:\> $ErrorActionPreference = $EAP
```

The first command stores the current setting for $ErrorActionPreference in $EAP.
This variable is used later to return the setting to its original value.

The second command sets the error action preference to Stop.
This error action preference changes an error from a non-terminating error to a terminating error.
The error object is raised as an exception instead of being written to the output pipe, and the command does not continue to run.

The third command gets each virtual machine object stores the objects in $VMs.
Using the @ symbol and parentheses makes sure that that the command stores the results in an array in case the command returns a single object or a null value.

The fourth command sets the BIOS boot order for each virtual machine to PXEBoot,IDEHarddrive,CD,Floppy.
The command uses a trap statement to catch terminating exceptions.
If the **Set-SCVirtualMachine** command fails, the string in the trap statement is displayed.
Continue is used in the trap statement to continue running instead of exiting the **ForEach** loop.
The **Out-Null** cmdlet redirects the output to $Null instead of sending it to the console.

Note: The *BootOrder* parameter is used only for virtual machines on Hyper-V and Citrix XenServer hosts.
It is not used for virtual machines on VMware ESX hosts.
XenServer hosts do not support floppy disks, and therefore ignores Floppy if listed in the boot order.

The last command sets the value for $ErrorActionPreference to the value stored in EAP.

For more information about the standard Windows PowerShell**ForEach** loop statement, type `Get-Help about_ForEach`.

### Example 5: Specify an owner for all virtual machines without an owner
```
PS C:\> Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | where {$_.Owner -eq ""} | Set-SCVirtualMachine -Owner "Contoso\ReneeLo"
```

This command gets all virtual machine objects on VMMServer01, selects only those virtual machine objects where no owner is listed, and specifies an owner for each virtual machine.

### Example 6: Enable dynamic memory for an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM06"
PS C:\> if($VM.Status -ne "PowerOff"){Stop-SCVirtualMachine -VM $VM}
PS C:\> Set-SCVirtualMachine -VM $VM -DynamicMemoryEnabled $True -MemoryMB 1024 -DynamicMemoryMaximumMB 2048
```

The first command gets the virtual machine object VM06, and stores that object in the $VM variable.
To enable dynamic memory on a virtual machine, the virtual machine must reside on a host that runs Windows Server 2008 R2 SP1 or a later version.

The second command determines whether the virtual machine stored in $VM is in a powered off state.
If the virtual machine is not in a powered off state, the command uses the **Stop-SCVirtualMachine** command to power off the virtual machine.

The last command enables Dynamic Memory, sets the startup memory to 1024 MB, and sets the maximum memory to 2048 MB.
The startup memory is the amount of memory on the host that is allocated to VM06 upon startup.
The maximum memory is the maximum amount of memory on the host that is allocated to VM06.

## PARAMETERS

### -AutomaticCriticalErrorAction
Specifies the action to take when the virtual machine encounters a critical error, and exceeds the timeout duration specified by the *AutomaticCriticalErrorActionTimeout* parameter.
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

### -AvailabilitySetNames
Specifies a list of availability set names.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockDynamicOptimization
Indicates whether dynamic optimization is blocked for a virtual machine.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ExcludeFromPRO

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
Specifies the number of CPUs on the virtual machine.
The following hosts support the following number of processors: 

- Hyper-V.
Up to four CPUs per virtual machine, depending on guest operating system.
- VMware ESX.
Up to four CPUs per virtual machine for any supported guest operating system, except one CPU on a virtual machine that run Windows NT 4.0. 
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
Specifies the percentage of CPU on the host that you expect this virtual machine to use.
This value is used only when VMM determines an appropriate host for the virtual machine.

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
Indicates whether to provide limited CPU functionality for the virtual machine.
Specify a value of $True to support an older operating system, such as Windows NT 4.0, on a virtual machine deployed on a Hyper-V host or on a VMware ESX host.

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
Specifies the highest percentage of the total resources of a single CPU on the host that a virtual machine can use at the same time.

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
High. 2000. 
- VMware ESX.
Above Normal. 1500. 
- VMware ESX.
Normal (default). 1000. 
- VMware ESX.
Below Normal. 750. 
- VMware ESX.
Low. 500. 
- VMware ESX.
Custom 1 to 1000000. 
- Citrix XenServer.
1 to 65536, typical is 256.

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
Specifies the minimum percentage of the resources of a single CPU on the host to allocate to the virtual machine.
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
To get all CPU types that are available for use in virtual machines in a VMM environment, see the **Get-SCCPUType** cmdlet.

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
Specifies the checkpoint type.
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

### -ClearDRProtection
Indicates that this cmdlet resets the data recovery protection option.

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

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterNonPossibleOwner
Specifies a list of names of the non-possible cluster node owners for a specified virtual machine.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.Host]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterPreferredOwner
Specifies a list of names of the preferred cluster node owners for a particular virtual machine.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.Host]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CostCenter
Specifies the cost center for a virtual machine.
You can collect data about the allocation of virtual machines or resources allocated to virtual machines for your billing system.

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

### -Custom1
Specifies a custom property of the virtual machine.

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

### -Custom10
Specifies a custom property of the virtual machine.

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

### -Custom2
Specifies a custom property of the virtual machine.

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

### -Custom3
Specifies a custom property of the virtual machine.

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

### -Custom4
Specifies a custom property of the virtual machine.

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

### -Custom5
Specifies a custom property of the virtual machine.

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

### -Custom6
Specifies a custom property of the virtual machine.

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

### -Custom7
Specifies a custom property of the virtual machine.

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

### -Custom8
Specifies a custom property of the virtual machine.

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

### -Custom9
Specifies a custom property of the virtual machine.

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

### -DelayStartSeconds
Specifies the number of seconds to wait after the virtualization service starts before automatically starting a virtual machine.

This delay staggers the startup time of multiple virtual machines to help reduce the demand on physical computer resources.
A typical setting might be 30 to 60 seconds.
The maximum configurable delay for hosts is as follows: 

- Hyper-V.
1000000000 seconds (277777 hours) 
- VMware ESX.
65535 seconds (18 hours) 

This parameter does not apply to XenServer virtual machines.

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
Specifies a description for the virtual machine.

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
Specifies the number of disk input/output operations per second (IOPS) on the host that can be used by the virtual machine.

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
Specifies the percentage of memory above the current memory allocation of a virtual machine which the host should try to reserve as a buffer.
The default value is 20.

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
You can enable dynamic memory directly on a virtual machine, or on a template or hardware profile that is used to create virtual machines.
The default value is $False.

You can enable dynamic memory for a virtual machine only if that virtual machine is deployed on a host that runs Windows Server 2008 SP1 or a later version or if the virtual machine is stored in a library in a stopped state.
Hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots.
Enabling dynamic memory on a virtual machine stored in a library limits placement of that machine to hosts that run Windows Server 2008 SP1 or a later version.

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
Specifies the maximum amount of memory that a host can allocate to a virtual machine, if dynamic memory is enabled.
The default value is 65536.

You can enable dynamic memory for a virtual machine only if that virtual machine is deployed on a host that runs Windows Server 2008 SP1 or a later version or if the virtual machine is stored in a library in a stopped state.
Hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots.
Enabling dynamic memory on a virtual machine stored in a library limits placement of that machine to hosts that run Windows Server 2008 SP1 or a later version.

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
Specifies the minimum amount of memory that the host can allocate to a virtual machine if dynamic memory is enabled.
The default value is 65536.

You can enable dynamic memory for a virtual machine only if that virtual machine is deployed on a host that runs Windows Server 2008 SP1 or a later version or if the virtual machine is stored in a library in a stopped state.
Hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots.
Enabling dynamic memory on a virtual machine stored in a library limits placement of that machine to hosts that run Windows Server 2008 SP1 or a later version.

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

### -EnableBackup
Indicates whether this cmdlet enables the Volume Shadow Copy Service to back up a virtual machine.
The virtual machine must be deployed on a Hyper-V host.

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

### -EnableDataExchange
Indicates whether this cmdlet enables or disables the use of a key/value pair for the exchange of data between a virtual machine and the host operating system.
The virtual machine must be deployed on a Hyper-V host.

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

### -EnableHeartbeat
Indicates whether this cmdlet enables or disables the use of a heartbeat to monitor the health of a virtual machine.
A heartbeat is a signal emitted at set intervals.
The virtual machine must be deployed on a Hyper-V host.

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

### -EnableOperatingSystemShutdown
Indicates whether this cmdlet enables or disables shut down of the operating system on a virtual machine managed by VMM from Hyper-V management interfaces on the host.
The virtual machine must be deployed on a Hyper-V host.

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

### -EnableTimeSync
Indicates whether this cmdlet enables or disables synchronizing the system time of a virtual machine with the system time of the operating system that runs on the host.
The virtual machine must be deployed on a Hyper-V host.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: EnableTimeSynchronization

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether this cmdlet enables or disables the virtual machine.

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

### -FirstBootDevice
Specifies the device on which a boot is first tried.

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

### -HighlyAvailable
Indicates whether a virtual machine is put on a Hyper-V host that is part of a host cluster.
Configure this setting on a virtual machine, or on a template or hardware profile that is used to create virtual machines.

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

### -InstallVirtualizationGuestServices
Indicates whether this cmdlet installs virtualization guest services on a Windows-based virtual machine.
The default value is $False, and VMM installs the appropriate virtualization guest service automatically.

For a virtual machine on a Hyper-V host, the virtualization guest service is called Integration Components or VMGuest.iso.
For a virtual machine on a XenServer host, the virtualization guest service is called Citrix Tools for Virtual Machines or xs-tools.iso.
Virtual machines on a VMware ESX host do not use a virtualization guest service.

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
Specifies the name of a variable for job progress.

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
Specifies the amount of random access memory (RAM), in megabytes (MB), on the host that is allocated to a virtual machine.
The default value is 512 MB.
For a virtual machine on which dynamic memory is enabled, specify the startup memory value.
The maximum assignable host memory is as follows: 

- Hyper-V.
Up to 65536 MB RAM per virtual machine
- VMware ESX Server 3.0.x Up to 16384 MB RAM per virtual machine
- VMware ESX Server 3.5.x.
Up to 65532 MB RAM per virtual machine
- Citrix XenServer.
Up to 32265 MB RAM per virtual machine

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
Specifies the maximum amount of memory, in megabytes, that the host allows each virtual NUMA node.

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
Specifies the priority for allocating memory to a virtual machine, relative to other virtual machines on the same host.
The host allocates more memory to a virtual machine that has a higher value than a virtual machine with a lower setting.
For a host that runs Windows Server 2008 R2 SP1 or a later version, the following are defaults: 

- Low.
0
- Normal.
5000
- High.
10,000
- Custom.
10,000

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
Specifies a value, as a string, that represents the maximum possible monitor resolution of a virtual video adapter.
Valid values are: 

- 1024x768 
- 1280x1024 
- 1600x1200 
- 1920x1200 

The default value is 1280x1024.

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
Specifies the name of the virtual machine.

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
Specifies the amount of bandwidth, in megabits per second (Mbps), on the host network that a virtual machine can use.

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
Indicates whether this cmdlet enables or disables the BIOS value for NumLock on the virtual machine.
The virtual machine must be deployed on a Hyper-V host.

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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To list the names of all available operating systems in VMM, use the **Get-SCOperatingSystem** cmdlet.

```yaml
Type: OperatingSystem
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Owner
Specifies the owner of a virtual machine as a valid domain user account.

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

### -QuotaPoint
Specifies a quota that limits the number of virtual machines self-service users can deploy.

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
Indicates that this cmdlet removes one or more specified capability profile objects.

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

### -RemoveFromCloud
Indicates that this cmdlet removes the association a virtual machine has to a cloud.

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

### -RemoveSelfServiceUserRole
Indicates whether this cmdlet removes the specified self-service user role from the permission list of the virtual machine.

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

### -RunAsSystem
Indicates that a virtual machine runs under the local system account.

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

### -RunAsUserCredential
Specifies the guest account as which the virtual machine runs.

For enhanced security, create a special account that has limited permissions.
The minimum permissions are as follows: 

- .vmc file.
Read data, write data, run file 
- .vmc folder.
List folder, write/create file to save virtual machine state 
- .vhd file.
Read data, read attributes, read extended attributes, write data 
- .vnc file.
Run file, read data, read attributes, read if the virtual machine  connects to a virtual network 

This parameter does not apply to virtual machines that Hyper-V, VMware ESX, or Citrix XenServer host.

```yaml
Type: PSCredential
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
Indicates whether this cmdlet enables secure starting.

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

### -StartAction
Specifies the behavior of a virtual machine when the virtualization service starts. 
Valid values are: 

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

### -StopAction
Specifies the behavior of the virtual machine when the virtualization service stops.
Valid values are: 

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

### -Tag
Specifies a word or phrase to associate to the virtual machine.
You can search for all objects that have the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

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

### -UseHardwareAssistedVirtualization
Indicates whether hardware-assisted virtualization is used if it is available.

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

### -UserRole
Specifies a user role object.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: SelfServiceUserRole

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
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMShieldingData
Specifies a **VMShieldingData** object.

```yaml
Type: KeyFile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMwareResourcePool
Specifies a VMware resource pool.
This cmdlet assigns a virtual machine deployed on a VMware ESX host or a private cloud to the resource pool that this parameter specifies.

```yaml
Type: VmwResourcePool
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
Indicates whether to enable the Microsoft Synthetic 3D Virtual Video Adapter for the virtual machine.
You can enable the Virtual Video Adapter directly on a virtual machine, or on a template or hardware profile that is used to create virtual machines.

You can enable the Microsoft Synthetic 3D Virtual Video Adapter for a virtual machine only if that virtual machine is deployed on a host that runs Windows Server 2008 R2 SP1, or a later version, that have the Remote Desktop Services role and Remote Desktop Virtual Graphics role service installed, or if the virtual machine is stored in a library in a stopped state.
Hardware changes to a stored virtual machine can only be made if the virtual machine does not have snapshots.
Enabling the Microsoft Synthetic 3D Virtual Video Adapter on a virtual machine stored in a library limits placement of that machine to hosts that run Windows Server 2008 R2 SP1, or a later version, that have the Remote Desktop Services role and Remote Desktop Virtual Graphics role service installed.

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

### VirtualMachine
This cmdlet returns a **VirtualMachine** object.

## NOTES
* This cmdlet requires a VMM virtual machine object, which can be retrieved by using the **Get-SCVirtualMachine** cmdlet.

## RELATED LINKS

[Get-SCCPUType](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCPUType.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Save-SCVirtualMachine.md)

[Set-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md)

[Set-SCVirtualFloppyDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDrive.md)

[Set-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapter.md)

[Set-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualScsiAdapter.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

