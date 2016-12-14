---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLibraryServer.md
schema: 2.0.0
ms.assetid: F6728178-56D9-468F-8F6E-5C57D3384C93
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMTemplate

## SYNOPSIS
Creates a virtual machine template used to create virtual machines managed by VMM.

## SYNTAX

### NewTemplateFromNothing (Default)
```
New-SCVMTemplate [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>] [-VMMServer <ServerConnection>]
 [-ApplicationProfile <ApplicationProfile>] [-SQLProfile <SQLProfile>] [-Generation <Int32>]
 [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>] [-AnswerFile <Script>]
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKey <SSHKey>]
 [-LinuxAdministratorSSHKeyString <String>] [-LinuxDomainName <String>] [-RecoveryPointObjective <Int32>]
 [-ProtectionProvider <ProtectionProvider>] [-ReplicationGroup <ReplicationGroup>] [-Shielded <Boolean>]
 [-NoCustomization] [-Name] <String> [-Description <String>] [-Owner <String>] [-UserRole <UserRole>]
 [-HardwareProfile <HardwareProfile>] [-GuestOSProfile <GuestOSProfile>] [-MemoryMB <Int32>]
 [-DynamicMemoryEnabled <Boolean>] [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>]
 [-MemoryWeight <Int32>] [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>]
 [-MonitorMaximumResolution <String>] [-CPUCount <Byte>] [-CPUType <ProcessorType>]
 [-CPURelativeWeight <Int32>] [-CapabilityProfile <CapabilityProfile>] [-HAVMPriority <UInt32>]
 [-CPUPerVirtualNumaNodeMaximum <Byte>] [-MemoryPerVirtualNumaNodeMaximumMB <Int32>]
 [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUReserve <UInt16>] [-CPUMaximumPercent <Int32>]
 [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>] [-AutomaticCriticalErrorAction <UInt16>]
 [-AutomaticCriticalErrorActionTimeout <Int32>] [-CheckpointType <CheckpointType>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures] [-Domain <String>]
 [-DomainJoinCredential <VMMCredential>] [-Workgroup <String>] [-AutoLogonCredential <RunAsAccount>]
 [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] -JobGroup <Guid>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### FromVHD
```
New-SCVMTemplate [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-ApplicationProfile <ApplicationProfile>] [-SQLProfile <SQLProfile>] [-Generation <Int32>]
 [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>] [-AnswerFile <Script>]
 [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKey <SSHKey>]
 [-LinuxAdministratorSSHKeyString <String>] [-LinuxDomainName <String>] [-RecoveryPointObjective <Int32>]
 [-ProtectionProvider <ProtectionProvider>] [-ReplicationGroup <ReplicationGroup>] [-Shielded <Boolean>]
 -VirtualHardDisk <StandaloneVirtualHardDisk> [-NoCustomization] [-Name] <String> [-Description <String>]
 [-Owner <String>] [-UserRole <UserRole>] [-HardwareProfile <HardwareProfile>]
 [-GuestOSProfile <GuestOSProfile>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-CapabilityProfile <CapabilityProfile>] [-HAVMPriority <UInt32>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUReserve <UInt16>]
 [-CPUMaximumPercent <Int32>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-AutomaticCriticalErrorAction <UInt16>] [-AutomaticCriticalErrorActionTimeout <Int32>]
 [-CheckpointType <CheckpointType>] [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>]
 [-FullName <String>] [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures] [-Domain <String>]
 [-DomainJoinCredential <VMMCredential>] [-Workgroup <String>] [-AutoLogonCredential <RunAsAccount>]
 [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### FromTemplate
```
New-SCVMTemplate [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-ApplicationProfile <ApplicationProfile>] [-SQLProfile <SQLProfile>] [-GuiRunOnceCommands <String[]>]
 [-MergeAnswerFile <Boolean>] [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-LinuxAdministratorSSHKeyString <String>] [-LinuxDomainName <String>]
 [-RecoveryPointObjective <Int32>] [-ProtectionProvider <ProtectionProvider>]
 [-ReplicationGroup <ReplicationGroup>] -VMTemplate <Template> [-Name] <String> [-Description <String>]
 [-Owner <String>] [-UserRole <UserRole>] [-HardwareProfile <HardwareProfile>]
 [-GuestOSProfile <GuestOSProfile>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-CapabilityProfile <CapabilityProfile>] [-HAVMPriority <UInt32>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUReserve <UInt16>]
 [-CPUMaximumPercent <Int32>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures] [-Domain <String>]
 [-DomainJoinCredential <VMMCredential>] [-Workgroup <String>] [-AutoLogonCredential <RunAsAccount>]
 [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SSHKeyFile
```
New-SCVMTemplate [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-ApplicationProfile <ApplicationProfile>] [-SQLProfile <SQLProfile>] [-GuiRunOnceCommands <String[]>]
 [-MergeAnswerFile <Boolean>] [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKey <SSHKey>] [-LinuxDomainName <String>] [-RecoveryPointObjective <Int32>]
 [-ProtectionProvider <ProtectionProvider>] [-ReplicationGroup <ReplicationGroup>] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] [-HardwareProfile <HardwareProfile>]
 [-GuestOSProfile <GuestOSProfile>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-CapabilityProfile <CapabilityProfile>] [-HAVMPriority <UInt32>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUReserve <UInt16>]
 [-CPUMaximumPercent <Int32>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures] [-Domain <String>]
 [-DomainJoinCredential <VMMCredential>] [-Workgroup <String>] [-AutoLogonCredential <RunAsAccount>]
 [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SSHKeyString
```
New-SCVMTemplate [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-ApplicationProfile <ApplicationProfile>] [-SQLProfile <SQLProfile>] [-GuiRunOnceCommands <String[]>]
 [-MergeAnswerFile <Boolean>] [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>]
 [-LinuxAdministratorSSHKeyString <String>] [-LinuxDomainName <String>] [-RecoveryPointObjective <Int32>]
 [-ProtectionProvider <ProtectionProvider>] [-ReplicationGroup <ReplicationGroup>] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] [-HardwareProfile <HardwareProfile>]
 [-GuestOSProfile <GuestOSProfile>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-CapabilityProfile <CapabilityProfile>] [-HAVMPriority <UInt32>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUReserve <UInt16>]
 [-CPUMaximumPercent <Int32>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures] [-Domain <String>]
 [-DomainJoinCredential <VMMCredential>] [-Workgroup <String>] [-AutoLogonCredential <RunAsAccount>]
 [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### FromVM
```
New-SCVMTemplate [-HighlyAvailable <Boolean>] [-DRProtectionRequired <Boolean>]
 [-ApplicationProfile <ApplicationProfile>] [-SQLProfile <SQLProfile>] [-GuiRunOnceCommands <String[]>]
 [-MergeAnswerFile <Boolean>] [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>]
 [-LinuxDomainName <String>] [-RecoveryPointObjective <Int32>] [-ProtectionProvider <ProtectionProvider>]
 [-ReplicationGroup <ReplicationGroup>] -VM <VM> [-BootVirtualHardDisk <VirtualHardDisk>] [-SkipRearm]
 [-LibraryServer <LibraryServer>] [-SharePath <String>] [-NoCustomization] [-Name] <String>
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] [-HardwareProfile <HardwareProfile>]
 [-GuestOSProfile <GuestOSProfile>] [-MemoryMB <Int32>] [-DynamicMemoryEnabled <Boolean>]
 [-DynamicMemoryMaximumMB <Int32>] [-DynamicMemoryBufferPercentage <Int32>] [-MemoryWeight <Int32>]
 [-VirtualVideoAdapterEnabled <Boolean>] [-MonitorMaximumCount <Int32>] [-MonitorMaximumResolution <String>]
 [-CPUCount <Byte>] [-CPUType <ProcessorType>] [-CPURelativeWeight <Int32>]
 [-CapabilityProfile <CapabilityProfile>] [-HAVMPriority <UInt32>] [-CPUPerVirtualNumaNodeMaximum <Byte>]
 [-MemoryPerVirtualNumaNodeMaximumMB <Int32>] [-VirtualNumaNodesPerSocketMaximum <Byte>] [-CPUReserve <UInt16>]
 [-CPUMaximumPercent <Int32>] [-DynamicMemoryMinimumMB <Int32>] [-NumaIsolationRequired <Boolean>]
 [-SecureBootEnabled <Boolean>] [-SecureBootTemplate <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures] [-Domain <String>]
 [-DomainJoinCredential <VMMCredential>] [-Workgroup <String>] [-AutoLogonCredential <RunAsAccount>]
 [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMTemplate** cmdlet creates a virtual machine template that administrators or self-service users can use to create virtual machines managed by Virtual Machine Manager (VMM).
A template stores hardware configuration and guest operating system information so that a specific template can be used repeatedly to create new virtual machines.
The **New-SCVMTemplate** cmdlet stores the new template object in the VMM library.

You can create a template based on an existing virtual hard disk, an existing template, or from a virtual machine currently deployed on a virtual machine host.
If you specify no parameters, VMM creates a default template object.

VMM Template Requirements


This section describes the requirements for creating a template in VMM. 



- Template from VHD.
If you create a template from a virtual hard disk (VHD), the VHD must meet the following requirements: 



     -- Operating system.
You must install a supported Windows operating system on the virtual hard disk before you use it to create the template.
For information about supported operating systems, see Operating Systems Compatibility for System Center Technical Previewhttps://technet.microsoft.com/en-us/library/dn997307(v=sc.16).aspx in the TechNet library at https://technet.microsoft.com/en-us/library/dn997307(v=sc.16).aspx. 



     -- SysPrep.
You must run the System Preparation tool (Sysprep.exe) on the VHD to ensure that every copy of the operating system is unique when you distribute it to multiple virtual machines.
You can find Sysprep.exe installed on your Windows Server 2008 or later computer at its default location: C:\Windows\System32\sysprep\. 



     -- Local Administrator Password.
The local Administrator password of the guest operating system on a VHD that will be used to create a new template must be blank before you run Sysprep.exe on the virtual hard disk.
A blank local Administrator password is required to enable you to have the option to specify the local Administrator password when you customize the guest operating system on the template. 



- Template from a Virtual Machine.
If you create a template from a virtual machine, the virtual machine will be destroyed during the process of converting it to a template.
If you want to keep the virtual machine and also use it to create a template, you can clone the virtual machine before you create the template.
For information about how to clone a virtual machine, see New-SCVirtualMachine.



- Template for Self-Service Users.
If a self-service user role includes permission to use a template, the self-service user cannot change any hardware profile settings.
The only settings that a self-service user can change when using a template to create a virtual machine are computer name and, if the user has appropriate privileges, password and product ID number.

VMM Support for Customizable or Non-Customizable Templates


If you specify the *NoCustomization* parameter with the **New-SCVMTemplate** cmdlet, you do not need to add a guest operating system profile to the template as you create the template.
Without a guest operating system profile, VMM will not require Sysprep to run within the guest operating system when a virtual machine that is created by using this template is deployed on a host.

One possible scenario is that you have a manually sysprepped virtual hard disk that contains a non-Windows operating system (or that contains an operating system that VMM cannot automatically sysprep) and have embedded an answer file in that virtual hard disk that contains the appropriate settings for that operating system.
You can use the **New-SCVMTemplate** cmdlet to create a template from this virtual hard disk and specify that the template does not allow customization of the guest operating system.
To do so, use the *NoCustomization* parameter when you create the new template.

In another scenario, you might import a VMware-based template that contains a Windows-based operating system into VMM.
By default, VMM imports a VMware-based template as customizable if VMM knows how to customize the guest operating system.
Otherwise, the template is imported as non-customizable (this is true, for example, for Linux guest operating systems).
If you want to create a non-customizable Windows-based template from this imported, customizable VMware-based template, you can use **New-SCVMTemplate** to create a new template, point to the disks that are attached to the imported template, and then specify the *NoCustomization* parameter on the new template.

## EXAMPLES

### Example 1: Create a virtual machine template from a virtual hard disk
```
PS C:\>$OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "64-bit Edition of Windows Server 2008 R2 Datacenter"}
PS C:\> $VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "VHD01.vhd" -and $_.LibraryServer.Name -eq "LibServer01.Contoso.com" }
PS C:\> New-SCVMTemplate -Name "VMTemplate01" -VirtualHardDisk $VHD -OperatingSystem $OS -NoCustomization
```

The first command gets the specified operating system object (64-bit edition of Windows Server 2008 R2 Datacenter) and stores the object in the $OS variable.

The second command gets the virtual hard disk object named VHD01 from the VMM library on LibServer01 and stores the object in the $VHD variable.

The last command creates a virtual machine template named VMTemplate01 from VHD01 and specifies the name of the operating system.
No customization is made to the operating system.

Note: This example assumes that VHD01 is a SysPrepped virtual hard disk on which the 64-bit edition of the Windows Server 2008 R2 Datacenter operating system is installed.
You can install virtualization guest services on the virtual machine, or VMM will install them automatically when the virtual machine is deployed on a Windows-based host.

### Example 2: Create a virtual machine template from an existing virtual machine
```
PS C:\>$LibraryServer = Get-SCLibraryServer | where {$_.Name -eq "LibServer01.Contoso.com"}
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01" | where {$_.VMHost.Name -eq "VMHost02.Contoso.com"}
PS C:\> $OperatingSystem = Get-SCOperatingSystem | where {$_.Name -eq "64-bit Edition of Windows Server 2008 R2 Enterprise"}
PS C:\> New-SCVMTemplate -Name "VMTemplate02" -RunAsynchronously -VM $VM -Owner "Contoso\ReneeLo" -LibraryServer $LibraryServer -SharePath "\\LibServer01.Contoso.com\MSSCVMMLibrary" -OperatingSystem $OperatingSystem -NoCustomization
```

The first command gets the library server object named LibServer01 and stores the object in the $LibraryServer variable.

The second command gets the virtual machine object named VM01 deployed on VMHost02 and stores the object in the $VM variable.

Note: VM01, which is the virtual machine that will be converted to a template, will be destroyed during the conversion process.
If you want to retain the virtual machine used to create a template, you can use the New-SCVirtualMachine cmdlet to clone the virtual machine before you create the template.

The third command gets the specified operating system object (Windows Server 2008 R2 Enterprise) and stores the object in the $OS variable.

The last command creates a virtual machine template named VMTemplate02 from virtual machine VM01.
It specifies the owner of the new template, the library server and share where you want to store the new template, and the name of the operating system, without any customization to the operating system.
The *RunAsynchronously* parameter returns control to the shell immediately before the command completes.

### Example 3: Create a virtual machine template from a virtual hard disk with specified characteristics
```
PS C:\>$JobGroupId01 = [Guid]::NewGuid().ToString()
PS C:\> $LogNet = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> New-SCVirtualNetworkAdapter -JobGroup $JobGroupID01 -MACAddressType Dynamic -LogicalNetwork $LogNet 
PS C:\> New-SCVirtualSCSIAdapter -JobGroup $JobGroupID01 -AdapterID 6 -Shared $False
PS C:\> New-SCVirtualDVDDrive -JobGroup $JobGroupID01 -Bus 1 -LUN 0 
PS C:\> New-SCHardwareProfile -Name "TempHWProfile" -Owner "Contoso\ReneeLo" -Description "Temporary hardware profile used to create a VM Template" -MemoryMB 512 -JobGroup $JobGroupID01
PS C:\> $JobGroupId02 = [Guid]::NewGuid().ToString()
PS C:\> $VHD = Get-SCVirtualHardDisk | where {$_.Location -eq "\\VMHost01Share\VHDs\Template.vhd"} | where {$_.HostName -eq "VMHost01.Contoso.com"}
PS C:\> New-SCVirtualDiskDrive -IDE -Bus 0 -LUN 0 -JobGroup $JobGroupID02 -VirtualHardDisk $VHD 
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "TempHWProfile" }
PS C:\> $OS = Get-SCOperatingSystem | where {$_.Name -eq "64-bit Edition of Windows Server 2008 R2 Enterprise"} 
PS C:\> New-SCVMTemplate -Name "NewTemplate03" -Owner "Contoso\ReneeLo" -HardwareProfile $HWProfile -JobGroup $JobGroupID02 -ComputerName "*" -JoinWorkgroup "WORKGROUP" -OperatingSystem $OS -RunAsynchronously
```

The first command generates a globally unique identifier (GUID) and stores the GUID string in variable $JobGroupID01.
The job group ID functions as an identifier that groups subsequent commands that include $JobGroupID01 into a single job group.

The second command gets the logical network object named LogicalNetwork01 and stores the object in the $LogNet variable.

The third command creates a virtual network adapter and uses the *JobGroup* parameter to indicate that the network adapter is not created until just before the New-SCHardwareProfile cmdlet runs.
The New-SCVirtualNetworkAdapter cmdlet sets the MAC address type to dynamic and specifies that the new virtual network adapter will connect to the logical network stored in $LogNet.

The fourth command creates a virtual SCSI adapter and uses the *JobGroup* parameter to indicate that the SCSI adapter is not created until just before the **New-SCHardwareProfile** cmdlet runs.
The New-SCVirtualScsiAdapter cmdlet sets the adapter ID to 6 and sets the *Shared* parameter to $False so that the adapter is not shared, as would be necessary if you wanted to use it in guest clustering.

The fifth command creates a virtual DVD drive and uses the *JobGroup* parameter to specify that the DVD drive is not created until just before the **New-SCHardwareProfile** cmdlet runs.
The New-SCVirtualDVDDrive cmdlet specifies Bus 1 and LUN 0 to attach the virtual DVD drive to Secondary Channel (0) on the IDE bus.

The sixth command creates a hardware profile named TempHWProfile, sets the owner to Contoso\ReneeLo, specifies a description and that the amount of memory on the host that a virtual machine created by using this template will use is 512 MB.
The **New-SCHardwareProfile** cmdlet uses the JobGroup parameter to specify that all preceding commands that include variable $JobGroupID01 will run just before **New-SCHardwareProfile** creates the new hardware profile.
After **New-SCVirtualNetworkAdapter**, **New-SCVirtualSCSIAdapter**, and **New-SCVirtualDVDDrive** run, the resulting objects that are created are automatically associated with the new hardware profile.

The seventh command generates a new GUID and stores it in $JobGroupID02.
This job group ID will be used to identify any subsequent commands that include this ID and will delay running those commands until just before the last command that specifies $JobGroupID02 runs.

The eighth command uses the Get-SCVirtualHardDisk cmdlet to get the virtual hard disk object named Template.vhd, VHDs on VMHost01 and stores the object in the $VHD variable.

The ninth command creates a new virtual disk drive and attaches the virtual hard disk stored in $VHD (Template.vhd) to this new virtual disk drive.
The command specifies Bus 0 and LUN 0 on the IDE Bus so that Template.vhd will be attached to the first slot (0) of the Primary Channel (0) on the IDE bus of the new virtual disk drive.
The command uses the *JobGroup* parameter to specify that the new virtual disk drive is not created until just before the **New-SCVMTemplate** cmdlet runs in the last command.

The tenth command gets the hardware profile object that represents the hardware profile named TempHWProfile from the VMM library and stores the object in the $HWProfile variable.

The eleventh command gets the specified operating system object (64-bit Edition of Windows Server 2008 R2 Enterprise) and stores the object in the $OS variable.

The last command creates a virtual machine template named NewTemplate03, sets the owner to Contoso\ReneeLo, specifies that this template will use the hardware profile named TempHWProfile, sets the computer name to be randomly generated (indicated by the asterisk *), and specifies that any virtual machine created by using this template will be joined to the workgroup called WORKGROUP.
The **New-SCVMTemplate** cmdlet uses the *JobGroup* parameter to specify that all preceding commands that include variable $JobGroupID02 run before **New-SCVMTemplate** creates the new template.
After **Add-SCVirtualHardDisk** runs, the resulting virtual hard disk object that is created is automatically associated with the new template.

### Example 4: Create a virtual machine template with the DRProtectionRequired parameter set to $True
```
PS C:\>$OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "Windows Server 2016"}
PS C:\> $VHDX = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "VHDX01.vhdx" -and $_.LibraryServer.Name -eq "LibServer01.Contoso.com" }
PS C:\> New-SCVMTemplate -Name "VMTemplate04" -VirtualHardDisk $VHDX -OperatingSystem $OS -DRProtectionRequired $True
```

The first command gets the operating system named Windows Server 2016 and stores it in the $OS variable.

The second command gets the virtual hard disk object named VHDX01 from the VMM library and stores the object in the $VHDX variable.

The last command creates a virtual machine template named VMTemplate04 that requires DR protection for the virtual machines created from this template.

### Example 5: Create a customizable Linux virtual machine template from a virtual hard disk
```
PS C:\>$OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "CentOS Linux 6 (64 bit)"}
PS C:\> $VHD = Get-SCVirtualHardDisk -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "LinuxVHD01.vhd" -and $_.LibraryServer.Name -eq "LibServer01.Contoso.com" }
PS C:\> New-SCVMTemplate -Name "LinuxVMTemplate01" -VirtualHardDisk $VHD -OperatingSystem $OS
```

The first command gets the specified operating system object (CentOS Linux 6 (64 bit)) and stores the object in the $OS variable.

The second command gets the virtual hard disk object named LinuxVHD01 from the VMM library on LibServer01 and stores the object in the $VHD variable.

The last command creates a virtual machine template named LinuxVMTemplate01 from LinuxVHD01 and specifies the name of the operating system.

## PARAMETERS

### -AnswerFile
Specifies a script object stored in the Virtual Machine Manager (VMM) library to use as an answer file.
The name of the answer file script depends on the operating system that you want to install on a virtual machine: 

- Sysprep.inf.
Windows XP, Windows Server 2000, or Windows Server 2003
- Unattend.xml.
Windows Vista, Windows 7, or Windows Server 2008

```yaml
Type: Script
Parameter Sets: (All)
Aliases: SysPrepFile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoLogonCount
Specifies the number of times that Windows should automatically log the administrator specified in the answer file on to the console session.

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

### -AutoLogonCredential
Specifies the Run As account contained in the answer file that Windows uses to log on to the console session when automatic administrator logon is enabled.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticCriticalErrorAction
Specifies the action to take when the virtual machine encounters a critical error, and exceeds the timeout duration specified by the *AutomaticCriticalErrorActionTimeout* parameter.
The acceptable values for this parameter are: Pause and None.

```yaml
Type: UInt16
Parameter Sets: NewTemplateFromNothing, FromVHD
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
Parameter Sets: NewTemplateFromNothing, FromVHD
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BootVirtualHardDisk
Specifies the virtual hard disk that contains the operating system file to use when you create a new template.

```yaml
Type: VirtualHardDisk
Parameter Sets: FromVM
Aliases: 

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

### -CPUMaximumPercent
Specifies the highest percentage of the total resources of a single CPU on the host that can be used by a specific virtual machine at any given time. 



Example:  `-CPUMaximumPercent 80` (to specify 80 per cent)

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
Type: UInt16
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
Parameter Sets: NewTemplateFromNothing, FromVHD
Aliases: 
Accepted values: Disabled, Production, ProductionOnly, Standard

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

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

### -Description
Specifies a description for the virtual machine template.

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

### -DisableAutoLogon
Indicates that this cmdlet disables automatic administrator logon.

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

### -Domain
Specifies a fully qualified domain name (FQDN) for an Active Directory domain. 


Example format: `-Domain "Domain01.Corp.Contoso.com"`

```yaml
Type: String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: JoinDomainCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainJoinOrganizationalUnit
Specifies the organizational unit to which the computer is joined during an unattended mini-setup.

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
Enables, when set to $True, dynamic memory for virtual machines.
You can enable dynamic memory directly on a virtual machine, or on a template or hardware profile that will be used to create virtual machines.
The default value is False.

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

### -FullName
Specifies the name of the person in whose name a virtual machine is registered.

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
Parameter Sets: NewTemplateFromNothing, FromVHD
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GuiRunOnceCommands
Specifies an array of commands to add to the **\[GuiRunOnce\]** section of an unattended answer file.
Use single quotation marks around each string enclosed in double quotation marks. 

Example format: 
`-GuiRunOnceCommands '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"', '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"'`

For information about how Windows PowerShell uses quotation marks, type `Get-Help about_Quoting_Rules`.

```yaml
Type: String[]
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighlyAvailable
Indicates whether to place a virtual machine on a Hyper-V host that is part of a host cluster.
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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: NewTemplateFromNothing
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: FromVHD, FromTemplate, FromVM
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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: FromVM
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxAdministratorSSHKey
Specifies the public key file for a Linux SSH Key.

```yaml
Type: SSHKey
Parameter Sets: NewTemplateFromNothing, FromVHD, FromTemplate, SSHKeyFile
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
Parameter Sets: NewTemplateFromNothing, FromVHD, FromTemplate, SSHKeyString
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxDomainName
Specifies a fully qualified domain name (FQDN) to be used in conjunction with Linux operating system specialization. 



Example format: `-LinuxDomainName "Domain01.Corp.Contoso.com"`

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
Specifies the user name and password for the Local Administrator account (or Linux root account in the case of a Linux compatible Guest Operating System profile).

Specifying credentials on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine overrides any existing Administrator password.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: AdminPasswordCredential

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

For a host running Windows Server 2008 R2 SP1 or later, 5000 = Normal, 10000 = High, 0 = Low, 1 to 10000 = Custom.

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

The default value is  1280x1024.

Example format: `-MonitorMaximumResolution "1600x1200"`

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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoCustomization
Specifies that guest operating system settings on this template cannot be customized.

```yaml
Type: SwitchParameter
Parameter Sets: NewTemplateFromNothing, FromVHD, FromVM
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

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To list the names of all available operating systems in VMM, type `Get-SCOperatingSystem`.

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
Specifies the name of the organization for the person in whose name a virtual machine is registered.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OrgName

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

### -ProductKey
Specifies a product key.
The product key is a 25-digit number that identifies the product license.
A product key can be used to register VMM or an operating system to be installed on a virtual machine or host.

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

### -RemoveDomainJoinOrganizationalUnit
Removes the organizational unit (OU) that the computer joined during setup.

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

### -RemoveServerFeatures
Removes all server roles and features from a template.

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

### -SQLProfile
Specifies a SQL Server profile object.

```yaml
Type: SQLProfile
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

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path. 


Example format: `-SharePath "\\\\LibServer01\LibShare"`

```yaml
Type: String
Parameter Sets: FromVM
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Shielded
Indicates whether the object is shielded.

```yaml
Type: Boolean
Parameter Sets: NewTemplateFromNothing, FromVHD
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipRearm
Skips running the Windows Software Licensing Rearm program.
This program restores the Windows operating system to its original, out-of-box licensing state.

Important: Refer to your licensing agreements with regard to activation and the Rearm program.
Using this parameter might violate your licensing agreements.

```yaml
Type: SwitchParameter
Parameter Sets: FromVM
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeZone
Specifies a number (an index) that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see Microsoft Time Zone Index Valueshttp://go.microsoft.com/fwlink/?LinkId=120935  at http://go.microsoft.com/fwlink/?LinkId=120935.
If no time zone is specified, the default time zone used for a virtual machine is the same time zone setting that is on the virtual machine host. 


Example format to specify the GMT Standard Time zone: `-TimeZone 085`

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

### -UnattendSettings
Specifies a key/value pair consisting of **String**, **String**.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
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

### -VM
Specifies a virtual machine object.

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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: NewTemplateFromNothing
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
Parameter Sets: FromTemplate
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
Parameter Sets: FromVHD
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
Enables, when set to $True, the Microsoft Synthetic 3D Virtual Video Adapter for virtual machines.
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

### -Workgroup
Specifies on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine the name of the workgroup to which you want to join a virtual machine.
You can use this parameter to override the existing value on a template or on a guest operating system profile.

```yaml
Type: String
Parameter Sets: (All)
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

### Template
This cmdlet returns a **Template** object.

## NOTES

## RELATED LINKS

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLibraryServer.md)

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalNetwork.md)

[Get-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCOperatingSystem.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualHardDisk.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMTemplate.md)

[New-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCHardwareProfile.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualDiskDrive.md)

[New-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualDVDDrive.md)

[New-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualNetworkAdapter.md)

[New-SCVirtualScsiAdapter](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVirtualScsiAdapter.md)

[Remove-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMTemplate.md)

[Set-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMTemplate.md)

