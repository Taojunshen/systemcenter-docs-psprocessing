---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 22AD5906-D307-457D-8F4A-C9A34DED4E65
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostRating.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostRating.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostRating.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVMHostRating

## SYNOPSIS
Calculates the placement rating for one or more hosts managed by VMM on which you might want to deploy a specific virtual machine.

## SYNTAX

### FromVMHostGroups
```
Get-SCVMHostRating [-HighlyAvailable <Boolean>] [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>]
 [-DiskPriority <UInt16>] [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>]
 [-PlacementGoal <EnginePlacementGoals>] [-ReplicationGroup <ReplicationGroup>] -VMHostGroup <HostGroup[]>
 [-VMMServer <ServerConnection>] -VM <VM> [-VMName <String>] [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-RunAsynchronously] [-DiscoveryID <Guid>]
 [-JobVariable <String>] [-ReturnFirstSuitableHost] [<CommonParameters>]
```

### FromVMClouds
```
Get-SCVMHostRating [-HighlyAvailable <Boolean>] [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>]
 [-DiskPriority <UInt16>] [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>]
 [-PlacementGoal <EnginePlacementGoals>] -Cloud <Cloud[]> [-VMMServer <ServerConnection>] -VM <VM>
 [-VMName <String>] [-IsMigration] [-IsCloudOnlyRating] [-CPUExpectedUtilizationPercent <UInt16>]
 [-NetworkUtilizationExpectedMbps <Int32>] [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### FromVMHosts
```
Get-SCVMHostRating [-HighlyAvailable <Boolean>] [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>]
 [-DiskPriority <UInt16>] [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>]
 [-PlacementGoal <EnginePlacementGoals>] [-ReplicationGroup <ReplicationGroup>] -VMHost <Host[]>
 [-VMMServer <ServerConnection>] -VM <VM> [-VMName <String>] [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-RunAsynchronously] [-DiscoveryID <Guid>]
 [-JobVariable <String>] [-ReturnFirstSuitableHost] [<CommonParameters>]
```

### NewVMHostGroupsTemplate
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -VMHostGroup <HostGroup[]> [-VMMServer <ServerConnection>]
 -VMTemplate <Template> -DiskSpaceGB <UInt16> -VMName <String> [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-VirtualizationPlatform <VirtualizationPlatform>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMCloudsConfig
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -Cloud <Cloud[]> [-VMMServer <ServerConnection>]
 -VMConfiguration <BaseVMConfiguration> [-DiskSpaceGB <UInt16>] [-IsMigration] [-IsCloudOnlyRating]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-VirtualizationPlatform <VirtualizationPlatform>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMHosts
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -VMHost <Host[]> [-VMMServer <ServerConnection>]
 -HardwareProfile <HardwareProfile> -DiskSpaceGB <UInt16> -VMName <String> [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-LUNCountRequirement <UInt32>]
 [-VirtualizationPlatform <VirtualizationPlatform>] [-JobGroup <Guid>] [-OperatingSystem <OperatingSystem>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMHostGroups
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -VMHostGroup <HostGroup[]> [-VMMServer <ServerConnection>]
 -HardwareProfile <HardwareProfile> -DiskSpaceGB <UInt16> -VMName <String> [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-LUNCountRequirement <UInt32>]
 [-VirtualizationPlatform <VirtualizationPlatform>] [-JobGroup <Guid>] [-OperatingSystem <OperatingSystem>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMClouds
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -Cloud <Cloud[]> [-VMMServer <ServerConnection>]
 -HardwareProfile <HardwareProfile> -DiskSpaceGB <UInt16> -VMName <String> [-IsMigration] [-IsCloudOnlyRating]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-LUNCountRequirement <UInt32>]
 [-VirtualizationPlatform <VirtualizationPlatform>] [-JobGroup <Guid>] [-OperatingSystem <OperatingSystem>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMHostsTemplate
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -VMHost <Host[]> [-VMMServer <ServerConnection>] -VMTemplate <Template>
 -DiskSpaceGB <UInt16> -VMName <String> [-IsMigration] [-CPUExpectedUtilizationPercent <UInt16>]
 [-NetworkUtilizationExpectedMbps <Int32>] [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath]
 [-VirtualizationPlatform <VirtualizationPlatform>] [-RunAsynchronously] [-DiscoveryID <Guid>]
 [-JobVariable <String>] [-ReturnFirstSuitableHost] [<CommonParameters>]
```

### NewVMCloudsTemplate
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -Cloud <Cloud[]> [-VMMServer <ServerConnection>] -VMTemplate <Template>
 -DiskSpaceGB <UInt16> -VMName <String> [-IsMigration] [-IsCloudOnlyRating]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-VirtualizationPlatform <VirtualizationPlatform>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMHostsConfig
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -VMHost <Host[]> [-VMMServer <ServerConnection>]
 -VMConfiguration <BaseVMConfiguration> [-DiskSpaceGB <UInt16>] [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-VirtualizationPlatform <VirtualizationPlatform>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

### NewVMHostGroupsConfig
```
Get-SCVMHostRating [-RequireGuardedHost <Boolean>] [-CPUPriority <UInt16>] [-DiskPriority <UInt16>]
 [-MemoryPriority <UInt16>] [-NetworkPriority <UInt16>] [-PlacementGoal <EnginePlacementGoals>]
 [-ReplicationGroup <ReplicationGroup>] -VMHostGroup <HostGroup[]> [-VMMServer <ServerConnection>]
 -VMConfiguration <BaseVMConfiguration> [-DiskSpaceGB <UInt16>] [-IsMigration]
 [-CPUExpectedUtilizationPercent <UInt16>] [-NetworkUtilizationExpectedMbps <Int32>]
 [-DiskIOExpectedCountPerSecond <Int32>] [-UseDefaultPath] [-VirtualizationPlatform <VirtualizationPlatform>]
 [-RunAsynchronously] [-DiscoveryID <Guid>] [-JobVariable <String>] [-ReturnFirstSuitableHost]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostRating** cmdlet calculates the placement rating for one or more hosts managed by Virtual Machine Manager (VMM) on which you might want to deploy a specific virtual machine.

The rating indicates the suitability of a computer to serve as a host for a virtual machine that requires a specific hardware configuration.
The rating can be computed by individual host, for an array of hosts, or for each host that belongs to a specific host group or set of host groups.

When you run the **Get-SCVMHostRating** cmdlet, VMM returns an **SCVMHostRating** object for each of the specified hosts based on the hardware configuration that you want on the virtual machine.
You can also specify additional placement options in order to modify how the ratings are calculated.

If you supply multiple host objects or an array of host objects to **Get-SCVMHostRating**, VMM gathers information about the host objects from the VMM database.
To produce a host rating, VMM then compares the running state of the virtual machine against the database information.
This operation does not guarantee migration compatibility of the virtual machine with a target host.

If you supply a single host object that is running Windows Server 2008 R2 or later, VMware, or Citrix XenServer to **Get-VMHostRating**, the cmdlet performs a direct validation of the running state of the virtual machine against the target host.
Performing a direct validation ensures migration compatibility of the virtual machine.
When performing the direct validation, the command might take several seconds to complete.

## EXAMPLES

### Example 1: Calculate host ratings for a specific server as a possible host for an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com" 
PS C:\> $HostRating = Get-SCVMHostRating -VM $VM -VMHost $VMHost
PS C:\> $HostRating
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The third command returns the placement rating for VMHost02 that indicates its suitability as a host for VM01 and stores the rating information in the $HostRating variable.

The last command displays the host ratings stored in $HostRating to the user.

Note: Because the example supplies a single host object to **Get-SCVMHostRating**, if the host is running Windows Server 2008 R2 or later, VMware, or XenServer, it performs a direct validation of the running state of the virtual machine against the target host to ensure migration compatibility of the virtual machine.

### Example 2: Calculate host ratings for each server in a host group as a possible host for an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $VMHostGroup = Get-SCVMHostGroup -Name "HostGroup02" 
PS C:\> $HostRatings = Get-SCVMHostRating -VM $VM -VMHostGroup $VMHostGroup
PS C:\> $HostRatings
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets the host group object that named HostGroup02 and stores the object in the $VMHostGroup variable.

The third command returns the placement ratings for all hosts in the specified host group and indicates the suitability of each host in that host group as a host for VM02.
The command stores the rating information in $HostRatings.

The last command displays the host ratings stored in $HostRating to the user.

Note: Because the preceding example supplies multiple host objects to **Get-SCVMHostRating**, it does not perform a direct validation of the virtual machine against the hosts to produce host ratings.
To ensure migration compatibility, you should perform a direct validation by running the **Get-SCVMHostRating** cmdlet on each potential target host individually.

### Example 3: Calculate host ratings for each server in a host group as a possible host for a new virtual machine
```
PS C:\> $VMHostGroup = Get-SCVMHostGroup -Name "HostGroup03"
PS C:\> $HWProfile = Get-SCHardwareProfile | where {$_.Name -eq "HWProfile01"}
PS C:\> $HostRatings = Get-SCVMHostRating -VMHostGroup $VMHostGroup -HardwareProfile $HWProfile -DiskSpaceGB 20 -VMName "VM03" -CPUPriority 8 -MemoryPriority 5 -DiskPriority 3 -NetworkPriority 1 
PS C:\> $HostRatings
```

The first command gets the host group object named HostGroup03 and stores the object in the $VMHostGroup variable.

The second command gets the hardware profile object named HWProfile01 and stores the object in the $HWProfile variable.

The third command returns the placement ratings for all hosts in the specified host group for a new virtual machine and stores the placement ratings in $HostRatings.
Before determining the host ratings, this command modifies the priorities for various factors by using the following parameters to specify these values: *DiskSpaceGB*, *CPUPriority*, *MemoryPriority*, *DiskPriority*, and *NetworkPriority*.
See the individual parameter descriptions for additional information.

The last command displays the host ratings stored in $HostRatings to the user.

Note: Because the preceding example supplies multiple host objects to **Get-SCVMHostRating**, it does not perform a direct validation of the virtual machine against the hosts to produce host ratings.
To ensure migration compatibility, you should perform a direct validation by running the **Get-SCVMHostRating** cmdlet on each potential target host individually.

### Example 4: Calculate host ratings for each host in an array as a possible host for a new virtual machine
```
PS C:\> $OS = Get-SCOperatingSystem | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Standard"}
PS C:\> $JobGroupID = [guid]::NewGuid()
PS C:\> New-SCVirtualDiskDrive -SCSI -Fixed -Bus 0 -Lun 2 -Size 10 -JobGroup $JobGroupID -FileName "TestDiskDrive"
PS C:\> $VMHosts = Get-SCVMHost 
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "HWProfile01" }
PS C:\> $HostRatings = Get-SCVMHostRating  -DiskSpaceGB 10 -HardwareProfile $HWProfile -VMHost $VMHosts -VMName "VM04" -OperatingSystem $OS -JobGroup $JobGroupID 
PS C:\> $HostRatings
```

The first command gets the operating system object that represents a 64-bit edition of Windows Server 2008 R2 Standard edition and stores the object in the $OS variable.

The second command generates a GUID and stores the GUID in $JobGroupID.
The job group ID functions as an identifier that groups subsequent commands into a single job group.

The third command creates a new virtual disk drive with the specified properties, but uses the job group ID to specify that the virtual disk drive is not created until just before the **Get-SCVMHostRating** cmdlet in the last command runs.

The fourth and fifth commands retrieve an array of host objects and a specific hardware profile object to pass into the **Get-VMHostRating** cmdlet in the next command.

The sixth command returns the placement ratings for all hosts in the specified host list and indicates the suitability of each host in that list for the new virtual machine with the specified characteristics.
The command stores the rating information in $HostRatings.

Before the **Get-SCVMHostRating** cmdlet returns the host ratings, the command uses the JobGroup parameter to run the **New-SCVirtualDiskDrive** command from the third command so that the **Get-SCVMHostRating** cmdlet includes the virtual disk drive and its settings when calculating placement ratings.

The last command displays the host ratings stored in $HostRatings to the user.

Note: Because the preceding example supplies an array of host objects to **Get-SCVMHostRating**, it does not perform a direct validation of the virtual machine against the hosts to produce host ratings.
To ensure migration compatibility, you should perform a direct validation by running the **Get-VMHostRating** cmdlet on each potential target host individually.

### Example 5: Calculate host ratings for a specific VMM management server as a possible host for an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM05"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost05.Contoso.com" 
PS C:\> $HostRating = Get-SCVMHostRating -VM $VM -VMHost $VMHost -CPUPriority 6 -DiskPriority 5 -MemoryPriority 4 -NetworkPriority 4 -PlacementGoal "Consolidate" 
PS C:\> $HostRating
```

The first command gets the virtual machine object named VM05 and stores the object in the $VM variable.

The second command gets the host object named VMHost05 and stores the object in the $VMHost variable.

The third command returns the placement rating for VMHost05 which indicates its suitability as a host for VM05 based on a particular set of customized priority ratings and based on consolidation as the placement goal (as opposed to the default, load balancing).
The command stores the rating information in $HostRating.

The last command displays the host rating stored in $HostRating to the user.

Note: Because the preceding example supplies a single host object to **Get-VMHostRating**, if the host is running Windows Server 2008 R2 or later, VMware, or XenServer, it performs a direct validation of the running state of the virtual machine against the target host to ensure migration compatibility of the virtual machine.

### Example 6: Calculate host ratings for a new virtual machine based on a specific virtual machine template
```
PS C:\> $VMTemplate = Get-SCVMTemplate | where {$_.Name -eq "VMTemplate01"}
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $HostRating = Get-SCVMHostRating -DiskSpaceGB 5 -VMTemplate $VMTemplate -VMHost $VMHost -VMName "VM06"
PS C:\> $HostRating
```

The first command gets the virtual machine template object named VMTemplate01 and stores the object in the $VMTemplate variable.

The second command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The third command returns the placement ratings for a new virtual machine if it were created by using VMTemplate01 and if it were to be placed on host VMHost01.
The command stores the ratings in $HostRating.

The last command displays the host ratings stored in $HostRating to the user.

Note: The *DiskSpaceGB* parameter is required even though the template might already have a virtual hard disk with a specified amount of disk space.
Requiring the *DiskSpaceGB* parameter ensures that a certain minumum amount of hard disk space is available on the host that can be used by the virtual machine.
If the amount of space specified for the virtual hard disk in the template is larger than the size specified by using the *DiskSpaceGB* parameter, the larger of the two sizes is taken into consideration when computing the host ratings.

Note: Because the preceding example supplies a single host object to Get-VMHostRating, if the host is running Windows Server 2008 R2 or later, VMware, or XenServer, it performs a direct validation of the running state of the virtual machine against the target host to ensure migration compatibility of the virtual machine.

### Example 7: Calculate host ratings for a specific host as a possible host for all virtual machines
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com" 
PS C:\> $VMs = Get-SCVirtualMachine
PS C:\> $RatingArray = @( ForEach ($VM in $VMs) {Get-VMHostRating -VM $VM -VMHost $VMHost} )
PS C:\> $RatingArray
```

The first command gets the host object that named VMHost02 and stores the host object in the $VMHost variable.

The second command gets all virtual machines objects in your environment and saves these objects in the $VMs object array.
If your environment has a very large number of virtual machines, you might want to use a filter to select a subset of virtual machines.

The third command returns the placement ratings for VMHost02 which indicate its suitability as a host for each of the virtual machine objects in $VMs and stores the rating information in $RatingArray.
For more information about the Windows PowerShell ForEach loop statement, type `Get-Help about_ForEach`.

The last command displays the ratings stored in $RatingArray for the user.

Note: This example computes the ratings for each virtual machine individually on a host.
If you want to place multiple virtual machines on a host, create a temporary hardware profile with the aggregated resource demands and pass it to **Get-SCVMHostRating**.

Note: Because the preceding example supplies a single host object to **Get-VMHostRating**, if the host is running Windows Server 2008 R2 or later, VMware, or XenServer, it performs a direct validation of the running state of the virtual machine against the target host to ensure migration compatibility of the virtual machine.

## PARAMETERS

### -CPUExpectedUtilizationPercent
Specifies the percent of CPU on the host that you expect this virtual machine to use.
This value is used only when VMM determines a suitable host for the virtual machine.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: ExpectedCPUUtilization

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUPriority
Specifies the relative importance of CPU utilization for a virtual machine on a host.
To make CPU utilization a higher priority relative to other factors (such as disk I/O performance, memory utilization, and network utilization), set this value to a higher number.
Valid values: 0 through 10.
Default value: 5.

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

### -Cloud
Specifies an array of private cloud objects.

```yaml
Type: Cloud[]
Parameter Sets: FromVMClouds, NewVMCloudsConfig, NewVMClouds, NewVMCloudsTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiscoveryID
For internal use only (not for use in your code).

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

### -DiskIOExpectedCountPerSecond
Specifies the number of disk input/output operations per second (IOPS) that you expect this virtual machine to use. 

Example format:  `-DiskIO 1500` (to specify 1500 IOPS)

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ExpectedDiskIO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskPriority
Specifies the relative importance of disk input/output (I/O) performance for a virtual machine on a host.
To make disk I/O performance a higher priority relative to other factors (such as CPU utilization, memory utilization, and network utilization), set this value to a higher number.
Valid values: 0 through 10.
Default value: 2.

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

### -DiskSpaceGB
Specifies the amount of hard disk space, in gigabytes (GB), on the host that can be used by a specific virtual machine. 


Example: `-DiskSpaceGB 20` (to specify 20 GB of disk space)

```yaml
Type: UInt16
Parameter Sets: NewVMHostGroupsTemplate, NewVMHosts, NewVMHostGroups, NewVMClouds, NewVMHostsTemplate, NewVMCloudsTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: UInt16
Parameter Sets: NewVMCloudsConfig, NewVMHostsConfig, NewVMHostGroupsConfig
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
Parameter Sets: NewVMHosts, NewVMHostGroups, NewVMClouds
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HighlyAvailable
Specifies whether to place a virtual machine on a Hyper-V host that is part of a host cluster.
Configure this setting on a virtual machine, or on a template or hardware profile that is used to create virtual machines.

```yaml
Type: Boolean
Parameter Sets: FromVMHostGroups, FromVMClouds, FromVMHosts
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsCloudOnlyRating
Indicates that the rating only applies to a private cloud.

```yaml
Type: SwitchParameter
Parameter Sets: FromVMClouds, NewVMCloudsConfig, NewVMClouds, NewVMCloudsTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsMigration
Indicates that a rating indicating a computer's suitability as a host to which to move a virtual machine will be calculated even if the source and destination host is the same computer.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: NewVMHosts, NewVMHostGroups, NewVMClouds
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

### -LUNCountRequirement
Specifies the number of LUNs required by a virtual machine when evaluating which computers are suitable hosts on which to deploy this virtual machine.

```yaml
Type: UInt32
Parameter Sets: NewVMHosts, NewVMHostGroups, NewVMClouds
Aliases: RequiredLunCount

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryPriority
Specifies the relative importance of memory utilization by a virtual machine on a host.
To make memory utilization a higher priority relative to other factors (such as CPU utilization, disk I/O performance, and network utilization), set this value to a higher number.
Valid Values: 0 through 10.
Default value: 8.

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

### -NetworkPriority
Specifies the relative importance of network utilization by a virtual machine on a host.
To make network utilization a higher priority relative to other factors (such as CPU utilization, disk I/O performance, and memory utilization), set this value to a higher number.
Valid values: 0 through 10.
Default value: 2.

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

### -NetworkUtilizationExpectedMbps
Specifies the amount of traffic, in megabits per second (Mbps), on the physical host's network that you expect this virtual machine to use.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: ExpectedNetworkUtilization

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To list the names of all available operating systems in VMM, type `Get-SCOperatingSystem`.

```yaml
Type: OperatingSystem
Parameter Sets: NewVMHosts, NewVMHostGroups, NewVMClouds
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PlacementGoal
Specifies the placement algorithm to use when VMM selects the most suitable host on which to deploy a virtual machine.
The acceptable values for this parameter are: LoadBalance, Consolidate.

Load balancing among hosts lets VMM minimize the processing load on any one host.
Consolidation lets VMM maximize resources by combining multiple low-utilization workloads on a single host.

```yaml
Type: EnginePlacementGoals
Parameter Sets: (All)
Aliases: 
Accepted values: LoadBalance, Consolidate

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
Parameter Sets: FromVMHostGroups, FromVMHosts, NewVMHostGroupsTemplate, NewVMCloudsConfig, NewVMHosts, NewVMHostGroups, NewVMClouds, NewVMHostsTemplate, NewVMCloudsTemplate, NewVMHostsConfig, NewVMHostGroupsConfig
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireGuardedHost
Specifies that the virtual machine needs to be placed on a Guarded host.

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

### -ReturnFirstSuitableHost
Indicates, when used in conjunction with **Get-SCVMHostRating** or Update-SCServiceConfiguration, that the Intelligent Placement engine returns the first suitable host per virtual machine to be placed and stops processing placement for that virtual machine.

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

### -UseDefaultPath
Specifies that only volumes for which a default path has been set on the host are evaluated as possible candidates for virtual machine placement.
If you omit this parameter or if no default paths are set on the host, all volumes are evaluated by the placement process.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: UseDefaultPaths

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
Parameter Sets: FromVMHostGroups, FromVMClouds, FromVMHosts
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMConfiguration
Specifies a virtual machine configuration object.

```yaml
Type: BaseVMConfiguration
Parameter Sets: NewVMCloudsConfig, NewVMHostsConfig, NewVMHostGroupsConfig
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies an array of virtual machine host objects.

```yaml
Type: Host[]
Parameter Sets: FromVMHosts, NewVMHosts, NewVMHostsTemplate, NewVMHostsConfig
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup[]
Parameter Sets: FromVMHostGroups, NewVMHostGroupsTemplate, NewVMHostGroups, NewVMHostGroupsConfig
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

### -VMName
Specifies the name of a virtual machine to be placed on a physical host server.
Use this parameter to verify that another virtual machine with the same name is not already deployed on that host.

```yaml
Type: String
Parameter Sets: FromVMHostGroups, FromVMClouds, FromVMHosts
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: NewVMHostGroupsTemplate, NewVMHosts, NewVMHostGroups, NewVMClouds, NewVMHostsTemplate, NewVMCloudsTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: NewVMHostGroupsTemplate, NewVMHostsTemplate, NewVMCloudsTemplate
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualizationPlatform
Specifies the virtualization platform of a virtual machine host managed by VMM.
The acceptable values for this parameter are:

- HyperV
- VMwareESX
- XENServer

```yaml
Type: VirtualizationPlatform
Parameter Sets: NewVMHostGroupsTemplate, NewVMCloudsConfig, NewVMHosts, NewVMHostGroups, NewVMClouds, NewVMHostsTemplate, NewVMCloudsTemplate, NewVMHostsConfig, NewVMHostGroupsConfig
Aliases: 
Accepted values: Unknown, VirtualServer, HyperV, VMWareVC, VMWareESX, XENServer

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

### VMHostRating
This cmdlet returns a **VMHostRating** object.

## NOTES

## RELATED LINKS

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHardwareProfile.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md)

