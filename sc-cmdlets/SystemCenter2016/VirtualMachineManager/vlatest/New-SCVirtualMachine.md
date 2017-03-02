---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 12630103-E5C2-4045-8186-CACAA01FA449
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCVirtualMachine

## SYNOPSIS
Creates a virtual machine to be managed by VMM.

## SYNTAX

### NewVmFromVmCloud
```
New-SCVirtualMachine [-StartVM] -VM <VM> [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKeyString <String>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] -Cloud <Cloud>
 [-CapabilityProfile <CapabilityProfile>] [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization]
 [-StoreToLibrary] [-DelayStartSeconds <Int32>] [-SelfServiceRole <SelfServiceUserRole>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>]
 [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewVmFromVirtualDisk
```
New-SCVirtualMachine [-StartVM] -VirtualHardDisk <StandaloneVirtualHardDisk> [-StartAction <VMStartAction>]
 [-StopAction <VMStopAction>] [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>]
 [-Generation <Int32>] [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] -VMHost <Host> -Path <String> [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization]
 [-DelayStartSeconds <Int32>] [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-RecoveryPointObjective <Int32>] [-ProtectionProvider <ProtectionProvider>]
 [-ReplicationGroup <ReplicationGroup>] [-BlockDynamicOptimization <Boolean>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-JobGroup <Guid>]
 [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewVmFromHWProfile
```
New-SCVirtualMachine [-StartVM] [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-Generation <Int32>]
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] -VMHost <Host> -Path <String> [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization]
 [-DelayStartSeconds <Int32>] [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-RecoveryPointObjective <Int32>] [-ProtectionProvider <ProtectionProvider>]
 [-ReplicationGroup <ReplicationGroup>] [-BlockDynamicOptimization <Boolean>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-JobGroup <Guid>]
 [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewVmFromVmConfig
```
New-SCVirtualMachine [-StartVM] [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] -VMConfiguration <BaseVMConfiguration>
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] [-VMShieldingData <KeyFile>] [-Cloud <Cloud>] [-CapabilityProfile <CapabilityProfile>]
 [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization] [-StoreToLibrary] [-DelayStartSeconds <Int32>]
 [-SelfServiceRole <SelfServiceUserRole>] [-BlockDynamicOptimization <Boolean>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-GuestOSProfile <GuestOSProfile>]
 [-FullName <String>] [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-GuiRunOnceCommands <String[]>] [-TimeZone <Int32>] [-MergeAnswerFile <Boolean>]
 [-LocalAdministratorCredential <VMMCredential>] [-Domain <String>] [-DomainJoinCredential <VMMCredential>]
 [-Workgroup <String>] [-AnswerFile <Script>] [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices]
 [-ReturnImmediately] [-LinuxDomainName <String>] [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### NewVmFromTemplate
```
New-SCVirtualMachine [-StartVM] -VMTemplate <Template> [-StartAction <VMStartAction>]
 [-StopAction <VMStopAction>] [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>]
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] [-VMShieldingData <KeyFile>] -VMHost <Host> -Path <String> [-UseLocalVirtualHardDisk]
 [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>] [-HighlyAvailable <Boolean>]
 [-DRProtectionRequired <Boolean>] [-RecoveryPointObjective <Int32>] [-ProtectionProvider <ProtectionProvider>]
 [-ReplicationGroup <ReplicationGroup>] [-BlockDynamicOptimization <Boolean>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-GuestOSProfile <GuestOSProfile>]
 [-FullName <String>] [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-GuiRunOnceCommands <String[]>] [-TimeZone <Int32>] [-MergeAnswerFile <Boolean>]
 [-LocalAdministratorCredential <VMMCredential>] [-Domain <String>] [-DomainJoinCredential <VMMCredential>]
 [-Workgroup <String>] [-AnswerFile <Script>] [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices]
 [-ReturnImmediately] [-LinuxDomainName <String>] [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### NewVmFromVm
```
New-SCVirtualMachine [-StartVM] -VM <VM> [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKeyString <String>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] -VMHost <Host> -Path <String>
 [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>]
 [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewStoredVmFromVirtualDisk
```
New-SCVirtualMachine -VirtualHardDisk <StandaloneVirtualHardDisk> [-StartAction <VMStartAction>]
 [-StopAction <VMStopAction>] [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>]
 [-Generation <Int32>] [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] -LibraryServer <LibraryServer> -SharePath <String> [-UseLocalVirtualHardDisk]
 [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>]
 [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewStoredVmFromVm
```
New-SCVirtualMachine -VM <VM> [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKeyString <String>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] -LibraryServer <LibraryServer>
 -SharePath <String> [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>]
 [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>]
 [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>]
 [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>] [-CPUCount <Byte>]
 [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>]
 [-CPUPerVirtualNumaNodeMaximum <Byte>] [-MemoryPerVirtualNumaNodeMaximumMB <Int32>]
 [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUCyclesReservePercent <UInt16>]
 [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-JobGroup <Guid>]
 [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewVmFromVmConfigScaleOut
```
New-SCVirtualMachine [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>]
 -VMConfigurationScaleOut <BaseVMConfiguration> [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKeyString <String>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] [-UseLocalVirtualHardDisk]
 [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>]
 [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewVmFromComputerTierScaleOut
```
New-SCVirtualMachine [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] -ComputerTier <ComputerTier>
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] [-UseLocalVirtualHardDisk] [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>]
 [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>]
 [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>]
 [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>] [-CPUCount <Byte>]
 [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>] [-HardwareProfile <HardwareProfile>]
 [-CPUPerVirtualNumaNodeMaximum <Byte>] [-MemoryPerVirtualNumaNodeMaximumMB <Int32>]
 [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUCyclesReservePercent <UInt16>]
 [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-ComputerName <String>] [-JobGroup <Guid>]
 [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NewStoredVmFromHardwareProfile
```
New-SCVirtualMachine [-StartAction <VMStartAction>] [-StopAction <VMStopAction>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-Generation <Int32>]
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-Owner <String>]
 [-UserRole <UserRole>] -LibraryServer <LibraryServer> -SharePath <String> [-UseLocalVirtualHardDisk]
 [-UseDiffDiskOptimization] [-DelayStartSeconds <Int32>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-HardwareProfile <HardwareProfile>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>]
 [-CPUCyclesReservePercent <UInt16>] [-CPUCyclesLimitPercent <UInt16>] [-DynamicMemoryMinimumMB <Int32>]
 [-NumaIsolationRequired <Boolean>] [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>]
 [-JobGroup <Guid>] [-SkipInstallVirtualizationGuestServices] [-ReturnImmediately] [-LinuxDomainName <String>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualMachine** cmdlet creates a virtual machine that Virtual Machine Manager (VMM) manages.
You can create a virtual machine from the following sources: 

- A stopped virtual machine deployed on a host. 
- A virtual machine stored in the VMM library. 
- A virtual machine template. 
- A virtual hard disk that already contains an operating system.
You can create a virtual machine from an existing hard disk that contains a third-party operating system, such as Linux.
- A blank virtual hard disk.

New in System Center 2016, you can create a virtual machine by using a differencing disk.
For more information about differencing disks, see **New-SCVirtualDiskDrive**.

When you deploy a new virtual machine to a Hyper-V host, you can specify a location for the virtual machine files, or use the default path: \<C\>:\ProgramData\Microsoft\Windows\Hyper-V.
When you deploy a virtual machine on a VMware ESX host or Citrix XenServer host, there is no default path.
Specify a path.

As an alternative to the current cmdlet, you can create a virtual machine by using the following cmdlets:  

- **New-SCP2V**.
This cmdlet creates a virtual machine from an existing physical computer.
This is called a P2V conversion.
For more information, type: `Get-Help New-SCP2V`.
- **New-SCV2V** creates a virtual machine from an existing virtual machine, such as a virtual machine created in VMWare.
This is called a V2V conversion).
For more information, type: `Get-Help New-SCV2V`.

## EXAMPLES

### Example 1: Create a virtual machine from a virtual hard disk and deploy it on a host
```
PS C:\> $VHD = Get-SCVirtualHardDisk -Name "Blank Disk - Large" 
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> New-SCVirtualMachine -Name "VM01" -VirtualHardDisk $VHD -VMHost $VMHost -Path "C:\VirtualMachinePath" -RunAsynchronously
```

The first command gets the virtual hard disk object named Blank Disk - Large from the VMM library, and stores that object in the $VHD variable.

The second command gets the host object named VMHost01, and stores that object in the $VMHost variable.

The last command creates a virtual machine named VM01 from the virtual hard disk stored in $VHD.
The command deploys the new virtual machine in C:\VirtualMachinePath on the host named VMHost01.
The command specifies the *RunAsynchronously* parameter.
The command returns control to the shell immediately, before the command finishes.

### Example 2: Create a virtual machine from a virtual machine template and deploy it on a host
```
PS C:\> $VMTemplate = Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "WindowsServer2008R2"}
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com"
PS C:\> New-SCVirtualMachine -VMTemplate $VMTemplate -Name "VM02" -VMHost $VMHost -Path "C:\VirtualMachinePath" -RunAsynchronously -ComputerName "Server01" -FullName "Elisa Daugherty" -OrgName "Contoso" -ProductKey "XXXXX-XXXXX-XXXXX-XXXXX-XXXXX"
```

The first command gets the virtual machine template object named WindowsServer2008R2, and stores that object in the $Template variable.

The second command gets the host object named VMHost02, and stores that object in the $VMHost variable.

The final command creates a virtual machine from the virtual machine template stored in $Template.
The command names the virtual machine VM02.
It deploys the virtual machine on host VMHost02 and stores the virtual machine files at C:\VirtualMachinePath.
The final command customizes the following properties: the computer name for the virtual machine, the name of the person to whom the virtual machine is registered, the organization name, and the product key.
The command specifies the *RunAsynchronously* parameter.
The command returns control to the shell immediately, before the command finishes.

### Example 3: Create a virtual machine by cloning an existing virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> if($VM.Status -eq "PowerOff"){New-SCVirtualMachine -Name "VM03" -VM $VM -VMHost $VMHost -Path "C:\VirtualMachinePath" -RunAsynchronously}
```

The first command gets the virtual machine object named VM03, and stores that object in the $VM variable.

The second command gets the host object named VMHost03, and stores that object in the $VMHost variable.

The final command checks whether virtual machine VM01 is in a powered off state.
If the virtual machine is powered off, the command creates a virtual machine named VM03 from VM01 and deploys the new virtual machine on VMHost03 in C:\VirtualMachinePath.

### Example 4: Create a virtual machine from a virtual machine stored in the library
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost04"
PS C:\> $VM = Get-SCVirtualMachine -Name "StoredVM01" | where {$_.LibraryServer.Name -eq "LibServer01.Contoso.com"} | where {$_.Location -eq "\\LibServer01.Consoso.com\MSSCVMMLibrary\StoredVM01"}
PS C:\> New-SCVirtualMachine -VM $VM -Name "VM04" -Description "New virtual machine from virtual machine stored in Library" -Owner "Contoso\ElisaDaugherty" -VMHost $VMHost -Path "C:\VirtualMachinePath" -RunAsynchronously -StartAction NeverAutoTurnOnVM -StopAction SaveVM -MemoryMB 1024
```

The first command gets the host object named VMHost04, and stores that object in the $VMHost variable.

The second command gets the virtual machine object named StoredVM01 from the specified path on library server LibServer01, and stores the virtual machine object in the $VM variable.

The last command creates a virtual machine named VM04 from StoredVM01 that has 1024 MB of memory.
The command deploys it at the specified path.
The command also specifies a description and owner, and specifies that the start action for the virtual machine is set to never turn on automatically and that the stop action is to save the virtual machine.

### Example 5: Create a highly available virtual machine
```
PS C:\> $JobGuid = [System.Guid]::NewGuid().ToString()
PS C:\> $VMName = "HAVM01"
PS C:\> New-SCVirtualNetworkAdapter -JobGroup $JobGuid -PhysicalAddressType Dynamic -VLANEnabled $False 
PS C:\> New-SCVirtualDVDDrive -JobGroup $JobGuid -Bus 1 -LUN 0 
PS C:\> New-SCHardwareProfile -Owner "Contoso\ElisaDaugherty" -Name "HWProfile02" -CPUCount 1 -MemoryMB 512 -HighlyAvailable $True -NumLock $False -BootOrder "CD", "IdeHardDrive", "PxeBoot", "Floppy" -LimitCPUFunctionality $False -JobGroup $JobGuid
PS C:\> New-SCVirtualDiskDrive -IDE -Bus 0 -LUN 0 -JobGroup $JobGuid -Size 40960 -Dynamic -Filename "HAVM01_disk_1.vhd" 
PS C:\> $VMHost = Get-SCVMHost | where {$_.Name -eq "VMMHANode02.Contoso.com"}
PS C:\> $HardwareProfile = Get-SCHardwareProfile | where {$_.Name -eq "HWProfile02"}
PS C:\> $OperatingSystem = Get-SCOperatingSystem | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Datacenter"}
PS C:\> New-SCVirtualMachine -Name $VMName -Description "" -VMMServer "VMMServer01.Contoso.com" -Owner "Contoso\ElisaDaugherty" -VMHost $VMHost -Path "R:\" -HardwareProfile $HardwareProfile -JobGroup $JobGuid -OperatingSystem $OperatingSystem -RunAsynchronously -StartAction NeverAutoTurnOnVM -StopAction SaveVM
```

The first command creates a GUID string, and stores it in the $VMGuid variable.
This GUID is a job group ID that functions as an identifier that groups subsequent commands that include this identifier into a single job group.

The second command stores the string HAVM01 in the $VMName variable.
This string is the name of the new virtual machine.

The third command creates a virtual network adapter that has a dynamic MAC address and has VLAN disabled.
Because the command specifies the *JobGroup* parameter, the network adapter is not created until just before the current cmdlet runs.

The fourth command creates an IDE virtual DVD drive connected to the second channel and the first slot.
Because the command specifies the *JobGroup* parameter, the virtual DVD drive is not created until just before the current cmdlet runs.

The fifth command creates a hardware profile and specifies values for the profile name, owner, CPU count, memory, and bootorder.
The command disables NumLock, and also limited CPU functionality.
Limited CPU is not needed because this is virtual machine doesl not run an older operating system.
This command designates the virtual machine as highly available.
Because the command specifies the *JobGroup* parameter, the hardware profile is not created until just before the current cmdlet runs..

The sixth command creates an IDE virtual disk drive with a storage capacity of 4 GB on the first channel and first slot.
Because the command specifies the *JobGroup* parameter, the new virtual disk drive is not created until just before the current cmdlet runs.

The seventh command gets a virtual machine host object named VMMHANode02, and stores that object in the $VMHost variable.
This host is one node of a host cluster that is managed by VMM.

The eighth command gets the hardware profile object named HWProfile02, which was created in the fifth command, and stores that object in the $HardwareProfile variable.

The ninth command gets an operating system object by name, and stores the object in the $OperatingSystem variable.

The final command creates a new highly available virtual machine named HAVM01 by using the objects created and obtained in the previous commands.
The command also specifies the *Path* parameter to specify the location to store the virtual machine.
This location must be a cluster-migratable LUN.
Additionally, the command specifies that the virtual machine is not started automatically when the host starts and that the virtual machine is put into a saved state when the virtualization service stops.

### Example 6: Use an existing VHD file on the destination host to create a new virtual machine from a template
```
PS C:\> $JobGroupID = [Guid]::NewGuid().ToString()
PS C:\> $VMTemplate = Get-SCVMTemplate | where {$_.Name -eq "VMTemplate01"}
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost06.Contoso.com"
PS C:\> Move-SCVirtualHardDisk -IDE -BUS 0 -LUN 0 -Path "L:\OS.VHD" -JobGroup $JobGroupID
PS C:\> New-SCVirtualMachine -Name "VM06" -Path "L:\" -VMTemplate $VMTemplate -VMHost $VMHost -JobGroup $JobGroupID -UseLocalVirtualHardDisk
```

The first command generates a GUID, and stores it in the $JobGroupID variable.

The second command gets the virtual machine template object named VMTemplate01, and stores that object in the $Template variable.
In this example, VMTemplate01 has a virtual disk drive on IDE Bus 0 LUN 0 that contains a virtual hard disk.

The third command gets the host object named VMHost06, and stores that object in the $VMHost variable.

The fourth command connects the specified virtual hard disk to the first slot (0) of the primary channel (0) on the virtual IDE controller on the virtual machine instead of the default virtual hard disk in the template.
The virtual hard disk stored at L:\OS.VHD contains the operating system that runs on the virtual machine.
Additionally, this command uses the *JobGroup* parameter to specify that it will not run until the **New-SCVirtualMachine** cmdlet triggers the commands in the *JobGroup* parameter to run.

The final command triggers all commands that contain the $JobGroupID variable to run.
The command creates the new virtual machine named VM06 from the template stored in $VMTemplate.
The command deploys the virtual machine on the host in $VMHost.
The command stores the virtual machine in the root directory of the L: drive.
The *UseLocalVirtualHardDisk* parameter specifies that the command uses an existing hard disk on the host instead of copying a VHD from the library.
Therefore, the virtual hard disk associated with the virtual disk drive on the template is replaced with the virtual hard disk drive that exists on the host, L:\OS.VHD.
As a result, both the virtual machine and its operating system are stored on the L: drive on the host.

### Example 7: Use an existing VHD on the destination host to create a virtual machine from a template, and move another VHD to the new virtual machine
```
PS C:\> $JobGroupID = [guid]::NewGuid()
PS C:\> $VMTemplate = Get-SCVMTemplate | where {$_.Name -eq "VMTemplate01"}
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost07.Contoso.com"
PS C:\> $VHD = Get-SCVirtualHardDisk -All | where {$_.Name -eq "Other.Vhd"}
PS C:\> Move-SCVirtualHardDisk -IDE -BUS 0 -LUN 0 -Path "L:\OS.VHD" -JobGroup $JobGroupID
PS C:\> New-SCVirtualDiskDrive -VirtualHardDisk $VHD -IDE -BUS 0 -LUN 1 -Path "R:\" -Filename "Other.Vhd" -JobGroup $JobGroupID
PS C:\> New-SCVirtualMachine -Name "VM07" -Path "D:\VirtualMachinePath" -VMTemplate $VMTemplate -VMHost $VMHost -JobGroup $JobGroupID -UseLocalVirtualHardDisk
```

The first three commands are identical to the first three commands in the previous example.
In this example, VMTemplate01 has a virtual disk drive on IDE Bus 0 and LUN 0 that contains a virtual hard disk.

The fourth command gets the virtual hard disk object named Other.VHD.
The **Get-SCVirtualHardDisk** cmdlet can retrieve virtual hard disk objects from a virtual machine, from a template, or from a stand-alone file stored in the VMM library.
Specifying the *All* parameter retrieves a full list of all the subordinate objects independent of the parent object.
In this case, the command retrieves all the available virtual hard disk objects, and then selects Other.VHD.

The fifth command connects the specified virtual hard disk to the first slot (0) of the primary channel (0) on the virtual IDE controller on the virtual machine instead of the default virtual hard disk in the template.
The virtual hard disk stored at L:\OS.VHD contains the operating system that will start on the virtual machine.
Additionally, this command specifies the *JobGroup* parameter to specify that it does not run until the current cmdlet triggers the commands in the *JobGroup* list to run.

The sixth command creates a virtual disk drive object and attaches the virtual hard disk object stored in $VHD to IDE Bus 0 and LUN 1 on the new drive.
The command specifies the *Path* parameter to store the virtual hard disk object in $VHD in the root directory of the R drive on the virtual machine, and it specifies that its name is Other.VHD.
Additionally, this command uses the JobGroup parameter to specify that it will not run until the last command triggers the commands in the JobGroup list to run.

The last command triggers all commands that contain the $JobGroupID variable to run.
The command creates the virtual machine named VM07 from the template stored in $VMTemplate.
The command deploys the virtual machine on the host specified in $VMHost.
The command stores the virtual machine in the D:\VirtualMachinePath folder.
The *UseLocalVirtualHarddisk* parameter specifies that the commmand uses an existing hard disk on the host instead of copying a VHD from the library.
Therefore, the virtual hard disk associated with the virtual disk drive on the template is replaced with the virtual hard disk drive that exists on the host, L:\OS.VHD.
As a result, the path of the virtual machine is D:\VirtualMachinePath\VM07, the path of the operating system is L:\OS.VHD, and the path of the other virtual hard disk is R:\Other.VHD.

### Example 8: Create a Linux-based virtual machine from a virtual machine template and deploy it on a host
```
PS C:\> $VMTemplate = Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com" | Where-Object {$_.Name -eq "CentOSConfigurable"}
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com"
PS C:\> $Cred = Get-Credential
PS C:\> New-SCVirtualMachine -VMTemplate $VMTemplate -Name "MyCentOSVM" -RunAsynchronously -ComputerName "MyCentOSVM" -LinuxDomainName "Contoso.com" -LocalAdministratorCredential $Cred -VMHost $VMhost -Path "C:\VirtualMachinePath"
```

The first command gets the virtual machine template object named CentOSConfigurable, and stores that object in the $Template variable.

The second command gets the host named VMHost02, and stores that object in the $VMHost variable.

The third command gets a credential, and stores that object in the $Cred variable.
This credential is for the root account.

The final command creates a virtual machine from the virtual machine template stored in $Template.
The command name the virtual machine MyCentOSVM.
It deploys the virtual machine on the host named VMHost02 and stores its files at C:\VirtualMachinePath.
The final command customizes the following properties: the computer name for the virtual machine, the Linux dnsdomainname, and the root account password.

## PARAMETERS

### -AnswerFile
Specifies a script object stored in the VMM library to use as an answer file.
The name of the answer file script depends on the operating system that you want to install on a virtual machine: 

- Sysprep.inf.
Windows XP, Windows Server 2000, or Windows Server 2003 
- Unattend.xml.
Windows Vista, Windows 7, or Windows Server 2008

```yaml
Type: Script
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: SysPrepFile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AutomaticCriticalErrorAction
Specifies the action to take when the VM encounters a critical error, and exceeds the timeout duration specified by the *AutomaticCriticalErrorActionTimeout* parameter.
The acceptable values for this parameter are: Pause and None.

```yaml
Type: UInt16
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromVmConfig, NewVmFromTemplate
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromVmConfig, NewVmFromTemplate
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromVmConfig, NewVmFromTemplate
Aliases: ExcludeFromPRO

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
Up to four CPUs per virtual machine for any supported guest operating system, except one CPU on a virtual machine that runs Windows NT 4.0. 
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

### -CPUCyclesLimitPercent
Specifies the limit of CPU cycles as a percentage.

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

### -CPUCyclesReservePercent
Specifies the reserve CPU cycles as a percentage.

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
To retrieve a list of all CPU types that are available for use in virtual machines in a VMM environment, see the **Get-SCCPUType** cmdlet.

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
Parameter Sets: NewVmFromVmCloud, NewVmFromVmConfig
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromVmConfig, NewVmFromTemplate
Aliases: 
Accepted values: Disabled, Production, ProductionOnly, Standard

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
Parameter Sets: NewVmFromVmCloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Cloud
Parameter Sets: NewVmFromVmConfig
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: 

- FQDN (fully qualified domain name) 
- IPv4 or IPv6 address 
- NetBIOS name

```yaml
Type: String
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate, NewVmFromComputerTierScaleOut
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerTier
Specifies a computer tier object.

```yaml
Type: ComputerTier
Parameter Sets: NewVmFromComputerTierScaleOut
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DRProtectionRequired
This parameter is reserved for future use.

```yaml
Type: Boolean
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate
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

### -Domain
Specifies an FQDN for an Active Directory domain.

```yaml
Type: String
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: JoinDomain

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainJoinCredential
Specifies the user name and password of an account that has permission to join a computer to the domain.
We recommend that you use a limited rights account joining computers to the domain.
This includes both virtual and physical computers.

You can use the current parameter to specify credentials on a **VMHostProfile** for joining a physical host computer to the domain, or to specify credentials, on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine, for joining a virtual machine to the domain.

```yaml
Type: VMMCredential
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: JoinDomainCredential

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

### -FullName
Specifies the name of the person in whose name this cmdlet registers a virtual machine.

```yaml
Type: String
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Generation
Specifies a value for the generation of the new virtual machine.

```yaml
Type: Int32
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewStoredVmFromVirtualDisk, NewStoredVmFromHardwareProfile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GuestOSProfile
Specifies a guest operating system profile object.

```yaml
Type: GuestOSProfile
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GuiRunOnceCommands
Specifies an array of commands to add to the **\[GuiRunOnce\]** section of an unattended answer file.
Use single quotation marks around each string enclosed in double quotation marks. 

Example format: `-GuiRunOnceCommands '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"', '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"'`

For information about how Windows PowerShell uses quotation marks, type `Get-Help about_Quoting_Rules`.

```yaml
Type: String[]
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
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
Configure this setting on a virtual machine, or on a template or hardware profile that is used to create virtual machines.

```yaml
Type: Boolean
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate
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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: NewStoredVmFromVirtualDisk, NewStoredVmFromVm, NewStoredVmFromHardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LinuxAdministratorSSHKey
Specifies the public key file for a Linux SSH Key.

```yaml
Type: SSHKey
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxAdministratorSSHKeyString
Specifies a Linux administrator SSH key as a string.

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

### -LinuxDomainName
Specifies an FQDN for Linux operating system specialization.

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

### -LocalAdministratorCredential
Specifies the user name and password for the Local Administrator account or Linux root account for a Linux-compatible Guest Operating System profile).

This cmdlet specifies these credentials on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine overrides any existing Administrator password.

```yaml
Type: VMMCredential
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: AdminPasswordCredential

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

### -MergeAnswerFile
Indicates whether this cmdlet merges the answer file together with guest operating system settings.
The default value is $True.
VMM console uses this parameter.
Do not specify this parameter.

```yaml
Type: Boolean
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
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
Specifies the name of the new virtual machine.

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationName
Specifies the name of the organization for the person in whose name this cmdlet registers the virtual machine.

```yaml
Type: String
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: OrgName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Path
Specifies the destination path for the new virtual machine.

```yaml
Type: String
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate, NewVmFromVm
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductKey
Specifies a product key.
The product key is a 25-digit number that identifies the product license.
A product key can be used to register VMM or an operating system to be installed on a virtual machine or host.

```yaml
Type: String
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReturnImmediately
Indicates that control is returned to the calling process immediately, before the job is created.

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

### -SecureBootEnabled


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

### -SelfServiceRole
Specifies the self-service role that has permission to access the virtual machine.

```yaml
Type: SelfServiceUserRole
Parameter Sets: NewVmFromVmCloud, NewVmFromVmConfig
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePath
Specifies a path of a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path.

```yaml
Type: String
Parameter Sets: NewStoredVmFromVirtualDisk, NewStoredVmFromVm, NewStoredVmFromHardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipInstallVirtualizationGuestServices
Indicates that this cmdlet does not install virtualization guest services on the virtual machine.
The default value is $False, and VMM installs the appropriate virtualization guest service automatically.

For a virtual machine on a Hyper-V host, the virtualization guest service is called Integration Components or VMGuest.iso.
For a virtual machine on a XenServer host, the virtualization guest service is called Citrix Tools for Virtual Machines or xs-tools.iso.
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

### -StartVM
Indicates that the virtual machine starts when it arrives at the destination host.

```yaml
Type: SwitchParameter
Parameter Sets: NewVmFromVmCloud, NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromVmConfig, NewVmFromTemplate, NewVmFromVm
Aliases: 

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
- ShutdownGuestOS.

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

### -StoreToLibrary
Indicates that this cmdlet stores the virtual machine in the VMM library.

```yaml
Type: SwitchParameter
Parameter Sets: NewVmFromVmCloud, NewVmFromVmConfig
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeZone
Specifies a number that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see [Microsoft Time Zone Index Values](http://go.microsoft.com/fwlink/?LinkId=120935) (`http://go.microsoft.com/fwlink/?LinkId=120935`) on the Microsoft Developer Network.
If you do not specify a time zone, the default time zone is the same time zone setting that is on the virtual machine host.

```yaml
Type: Int32
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDiffDiskOptimization
Indicates that this cmdlet uses differencing disk optimization.

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

### -UseLocalVirtualHardDisk
Indicates that this cmdlet verifies that the VHD files that this cmdlet must have to create the virtual machine exist and are stored on the destination host.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: UseLocalVirtualHardDisks

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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: NewVmFromVmCloud, NewVmFromVm, NewStoredVmFromVm
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
Parameter Sets: NewVmFromVmConfig
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConfigurationScaleOut
Specifies a virtual machine configuration object that is used when scaling out a service.

```yaml
Type: BaseVMConfiguration
Parameter Sets: NewVmFromVmConfigScaleOut
Aliases: ScaleOutVMConfiguration

Required: True
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
Parameter Sets: NewVmFromVirtualDisk, NewVmFromHWProfile, NewVmFromTemplate, NewVmFromVm
Aliases: Host

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

### -VMShieldingData
Specifies a **VMShieldingData** object.

```yaml
Type: KeyFile
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object that this cmdlet uses to create virtual machines.

```yaml
Type: Template
Parameter Sets: NewVmFromTemplate
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: StandaloneVirtualHardDisk
Parameter Sets: NewVmFromVirtualDisk, NewStoredVmFromVirtualDisk
Aliases: 

Required: True
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

### -Workgroup
Specifies the name of the workgroup to which to join the virtual machine.
You can use this parameter to override the existing value on a template or on a guest operating system profile.

```yaml
Type: String
Parameter Sets: NewVmFromVmConfig, NewVmFromTemplate
Aliases: JoinWorkgroup

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
* This cmdlet requires a VMM virtual hard disk object, virtual machine template object, or virtual machine object. To obtain such an object, use the **Get-SCVirtualHardDisk**, **Get-SCVMTemplate**, or **Get-SCVirtualMachine** cmdlet.

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Get-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md)

[Get-SCCPUType](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCPUType.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDisk.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCV2V](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCV2V.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Save-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

