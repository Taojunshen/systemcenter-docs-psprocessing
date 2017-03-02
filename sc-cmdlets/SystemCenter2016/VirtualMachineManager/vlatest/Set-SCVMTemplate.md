---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DFAA8C94-DB50-4D9E-9FB0-60439673DEF9
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVMTemplate

## SYNOPSIS
Changes properties of a virtual machine template used in VMM.

## SYNTAX

### Default (Default)
```
Set-SCVMTemplate [-VMTemplate] <Template> [-ProductKey <String>] [-GuiRunOnceCommands <String[]>]
 [-LocalAdministratorCredential <VMMCredential>] [-MergeAnswerFile <Boolean>]
 [-DomainJoinCredential <VMMCredential>] [-AnswerFile <Script>] [-ApplicationProfile <ApplicationProfile>]
 [-SQLProfile <SQLProfile>] [-LinuxAdministratorSSHKey <SSHKey>] [-LinuxAdministratorSSHKeyString <String>]
 [-LinuxDomainName <String>] [-Owner <String>] [-OperatingSystem <OperatingSystem>] [-Enabled <Boolean>]
 [-HighlyAvailable <Boolean>] [-HAVMPriority <UInt32>] [-DRProtectionRequired <Boolean>]
 [-ReplicationGroup <ReplicationGroup>] [-SecureBootEnabled <Boolean>] [-NumLock <Boolean>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-TimeZone <Int32>] [-RemoveServerFeatures]
 [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-Domain <String>]
 [-Workgroup <String>] [-CapabilityProfile <CapabilityProfile>] [-RemoveCapabilityProfile]
 [-UserRole <UserRole>] [-JobGroup <Guid>] [-QuotaPoint <UInt32>] [-CostCenter <String>] [-Tag <String>]
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
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SingleVM
```
Set-SCVMTemplate [-VMTemplate] <Template> [-ProductKey <String>] [-GuiRunOnceCommands <String[]>]
 [-LocalAdministratorCredential <VMMCredential>] [-MergeAnswerFile <Boolean>]
 [-DomainJoinCredential <VMMCredential>] [-AnswerFile <Script>] [-ApplicationProfile <ApplicationProfile>]
 [-SQLProfile <SQLProfile>] [-LinuxAdministratorSSHKey <SSHKey>] [-LinuxAdministratorSSHKeyString <String>]
 [-LinuxDomainName <String>] [-Owner <String>] [-OperatingSystem <OperatingSystem>] [-Enabled <Boolean>]
 [-HighlyAvailable <Boolean>] [-HAVMPriority <UInt32>] [-DRProtectionRequired <Boolean>]
 [-ReplicationGroup <ReplicationGroup>] [-SecureBootEnabled <Boolean>] [-NumLock <Boolean>]
 [-CPULimitFunctionality <Boolean>] [-CPULimitForMigration <Boolean>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-TimeZone <Int32>] [-RemoveServerFeatures]
 [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-Domain <String>]
 [-Workgroup <String>] [-CapabilityProfile <CapabilityProfile>] [-RemoveCapabilityProfile]
 [-UserRole <UserRole>] [-Name <String>] [-JobGroup <Guid>] [-QuotaPoint <UInt32>] [-CostCenter <String>]
 [-Tag <String>] [-Custom1 <String>] [-Custom2 <String>] [-Custom3 <String>] [-Custom4 <String>]
 [-Custom5 <String>] [-Custom6 <String>] [-Custom7 <String>] [-Custom8 <String>] [-Custom9 <String>]
 [-Custom10 <String>] [-BlockDynamicOptimization <Boolean>] [-ClearDRProtection] [-Description <String>]
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
The **Set-SCVMTemplate** cmdlet changes one or more properties of a virtual machine template used in a Virtual Machine Manager (VMM) environment.

Properties that you can change include settings for the name of the template, its description, owner, organization name, time zone, operating system, and product key; BIOS boot order; CPU number and characteristics; the amount memory on the host that is assigned to a virtual machine; the amount of bandwidth on the host's network available to a virtual machine; whether a virtual machine created with this template will be highly available (i.e., deployed on a host that is part of a host cluster); values for domain or workgroup as well as domain credentials; a point quota that specifies how many new virtual machines self-service users can create; custom fields; and other options.

Changes that you make to a template affect only the template.
Changes do not affect any existing virtual machines that were previously created by using this template.

If you want to change the properties of a virtual disk drive, virtual floppy drive, virtual DVD drive, virtual network adapter, virtual SCSI adapter or virtual COM port associated with a specific template, you can use **Set-SCVirtualDiskDrive**, **Set-SCVirtualFloppyDrive**, **Set-SCVirtualDVDDrive**, **Set-SCVirtualNetworkAdapter**, **Set-SCVirtualScsiAdapter**, or **Set-SCVirtualCOMPort** cmdlets, respectively.

## EXAMPLES

### Example 1: Specify an amount of memory for an existing virtual machine template
```
PS C:\> $Template = Get-SCVMTemplate | where {$_.Name -eq "VMTemplate01"}
PS C:\> Set-SCVMTemplate -Template $Template -MemoryMB 1024
```

The first command gets the virtual machine template object named VMTemplate01 from the VMM library and stores the object in the $Template variable.

The second command changes the memory value for VMTemplate01 to 1024 MB.
This is the amount of memory on the host that a virtual machine created by using this template will use.

### Example 2: Specify a new owner for multiple highly available virtual machine templates
```
PS C:\> $VMTemplates = Get-SCVMTemplate | where {$_.IsHighlyAvailable}
PS C:\> ForEach ($VMTemplate in $VMTemplates) {Set-SCVMTemplate $VMTemplate -Owner "Contoso\NevenSokec"}
```

The first command gets all highly available virtual machine template objects and stores the objects in the $VMTemplates object array.

The second command uses a **ForEach** loop to specify a new owner for each of the templates in the $VMTemplates array.

For information about the standard PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

### Example 3: Specify a new owner for all virtual machine templates that have the same owner
```
PS C:\> Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com" | where {$_.Owner -eq "Contoso\PattiFuller"} | Set-SCVMTemplate -Owner "Contoso\AllieSloan"
```

This command gets all virtual machine template objects from the VMM library, selects only those objects whose owner is "Contoso\PattiFuller", and then passes each object to the **Set-SCVMTemplate** cmdlet, which changes the owner to Contoso|AllieSloan.

### Example 4: Enable Dynamic Memory for an existing virtual machine template
```
PS C:\> $VMTemplate = Get-SCVMTemplate | where {$_.Name -eq "VMTemplate04"}
PS C:\> Set-SCVMTemplate -VMTemplate $VMTemplate -DynamicMemoryEnabled $True -MemoryMB 1024 -DynamicMemoryMaximumMB 2048
```

The first command gets the virtual machine template object named VMTemplate04 from the VMM library and stores the object in the $VMTemplate variable.

The second command enables dynamic memory, changes the startup memory value for VMTemplate04 to 1024 MB (this is the amount of memory on the host that a virtual machine created by using this template is allocated upon startup), and sets the maximum memory value to 2048 MB (this is the maximum amount of memory that can be allocated to a virtual machine created by using this template).
A virtual machine using dynamic memory can only be deployed on a host that is running Windows Server 2008 R2 SP1 or later.

### Example 5: Specify the root password for an existing customizable Linux virtual machine template
```
PS C:\> $Template = Get-SCVMTemplate | where {$_.Name -eq "LinuxVMTemplate01"}
PS C:\> $Creds = Get-Credential
PS C:\> Set-SCVMTemplate -Template $Template -LocalAdministratorCredential $Creds
```

The first command gets the virtual machine template object named LinuxVMTemplate01 from the VMM library and stores the object in the $Template variable.

The second command gets a username (root) and password via the Get-Credential command and stores the result in the $Creds variable.

The last command sets the root account password to the password stored in the $Creds variable.

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
Specifies the number of times that Windows should automatically log the administrator denoted in the Answer File on to the console session.

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

### -ClearDRProtection
Indicates that this cmdlet resets the disaster recovery protection option.

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

### -CostCenter
Specifies the cost center for a virtual machine so that you can collect data about the allocation of virtual machines (or resources allocated to virtual machines) to make use of in your billing system.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Specifies a custom property on a virtual machine template.

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
Disables automatic administrator logon.

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
Indicates whether to enable dynamic memory for virtual machines.
You can enable dynamic memory directly on a virtual machine, or on a template or hardware profile that is used to create virtual machines.
The default value is False.

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

### -Enabled
Enables an object when set to $True, or disables an object when set to $False.
For example, if you want to upgrade software on a virtual machine template, you can disable the template object in the VMM library to temporarily prevent users from using that object.

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

### -GuiRunOnceCommands
Specifies an array of commands to add to the **\[GuiRunOnce\]** section of an unattended answer file.
Use single quotation marks around each string enclosed in double quotation marks. 

Example format: `-GuiRunOnceCommands '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"', '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"'`

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
Specifies a fully qualified domain name (FQDN) to use in conjunction with Linux operating system specialization.

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
Specifies the user name and password for the Local Administrator account (or Linux root account in the case of a Linux-compatible Guest Operating System profile).

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
Parameter Sets: SingleVM
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
Indicates whether to enable the BIOS value for NumLock on a template that is used to create virtual machines on a Hyper-V host.
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
Accept pipeline input: True (ByValue)
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

### -RemoveDomainJoinOrganizationalUnit
Indicates that this cmdlet removes the organizational unit that the computer joined during setup.

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
Indicates that this cmdlet removes all server roles and features from a template.

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

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
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

### -TimeZone
Specifies a number (an index) that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see [Microsoft Time Zone Index Values](http://go.microsoft.com/fwlink/?LinkId=120935) at `http://go.microsoft.com/fwlink/?LinkId=120935`.
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
Aliases: SelfServiceUserRole

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: (All)
Aliases: Template

Required: True
Position: 0
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
* Requires a VMM virtual machine template object, which can be retrieved by using the **Get-SCVMTemplate** cmdlet.

## RELATED LINKS

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[New-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMTemplate.md)

[Remove-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMTemplate.md)

