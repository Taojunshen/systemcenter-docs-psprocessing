---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E5A78A88-8D7B-417B-B934-69AD6EA613C6
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMHost

## SYNOPSIS
Modifies properties of a virtual machine host.

## SYNTAX

```
Set-SCVMHost [-VMHost] <Host> [-BMCAddress <String>] [-BMCRunAsAccount <RunAsAccount>] [-BMCPort <UInt32>]
 [-BMCProtocol <OutOfBandManagementType>] [-BMCCustomConfigurationProvider <ConfigurationProvider>]
 [-ManagementAdapterMACAddress <String>] [-SMBiosGuid <Guid>] [-KeyProtectionServerUrl <String>]
 [-AttestationServerUrl <String>] [-CodeIntegrityPolicy <CodeIntegrityPolicy>]
 [-ApplyLatestCodeIntegrityPolicy] [-BypassMaintenanceModeCheck] [-MaintenanceHost <Boolean>]
 [-AvailableForPlacement <Boolean>] [-Description <String>] [-OverrideHostGroupReserves <Boolean>]
 [-CPUPercentageReserve <UInt16>] [-NetworkPercentageReserve <UInt16>] [-DiskSpaceReserveMB <UInt64>]
 [-MaxDiskIOReservation <UInt64>] [-MemoryReserveMB <UInt64>] [-VMPaths <String>] [-BaseDiskPaths <String>]
 [-RemoteConnectEnabled <Boolean>] [-RemoteConnectPort <UInt32>] [-SecureRemoteConnectEnabled <Boolean>]
 [-RemoteConnectCertificatePath <String>] [-RemoveRemoteConnectCertificate] [-EnableLiveMigration <Boolean>]
 [-LiveMigrationMaximum <UInt32>] [-LiveStorageMigrationMaximum <UInt32>] [-UseAnyMigrationSubnet <Boolean>]
 [-MigrationSubnet <String[]>] [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-VMHostManagementCredential <VMMCredential>]
 [-NumaSpanningEnabled <Boolean>] [-FibreChannelWorldWidePortNameMinimum <String>]
 [-FibreChannelWorldWidePortNameMaximum <String>] [-FibreChannelWorldWideNodeName <String>]
 [-IsDedicatedToNetworkVirtualizationGateway <Boolean>] [-JobGroup <Guid>] [-Custom1 <String>]
 [-Custom2 <String>] [-Custom3 <String>] [-Custom4 <String>] [-Custom5 <String>] [-Custom6 <String>]
 [-Custom7 <String>] [-Custom8 <String>] [-Custom9 <String>] [-Custom10 <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMHost** cmdlet modifies one or more properties of a virtual machine host managed by Virtual Machine Manager (VMM).
Settings that you can modify with the **Set-SCVMHost** cmdlet are summarized as follows:

Availability as a Host for Virtual Machines

You can specify whether a host is currently considered by the VMM placement process as a candidate on which to place virtual machines.

Host Reserve Settings

You can configure the following host reserve settings: 

- Percentage of CPU usage to set aside for use by the host. 
- Amount of disk space (MB) to set aside for use by the host. 
- Maximum number of disk I/O operations per second (IOPS) to set aside for use by the host. 
- Amount of memory (MB) to set aside for use by the host. 
- Percentage of network capacity to set aside for use by the host.

The VMM placement process will not recommend placing a virtual machine on a host unless the resource requirements of the virtual machine can be met without using the host reserves.
If you do not specify reserve settings, VMM uses default settings.

Virtual Machine Paths

You can specify, as a set of default paths, locations on a host where virtual machine files can be stored.

Credential for Managing Hosts in a Perimeter Network or Non-Trusted Domain

You can specify the password for an account used to manage Hyper-V hosts that are located in a perimeter network or in a non-trusted domain.

Remote Connection Settings

You can configure remote connection settings for Hyper-V hosts (VMConnect) that enable users to connect to virtual machines remotely.
This setting does not apply to virtual machines on VMware ESX hosts.

## EXAMPLES

### Example 1: Make a host available for placement
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01" 
PS C:\> Set-SCVMHost -VMHost $VMHost -AvailableForPlacement $True
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command makes VMHost01 available as a host for virtual machines.
Setting the *AvailableForPlacement* parameter to True enables the VMM placement process to evaluate this host as a possible candidate on which to deploy virtual machines.

### Example 2: Enable remote connections on a Hyper-V host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01" 
PS C:\> Set-SCVMHost -VMHost $VMHost -RemoteConnectEnabled $True -RemoteConnectPort 5900
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command enables remote connections on VMHost01 and sets the port used for remote connections to 5900.

Enabling remote connections on a Hyper-V host allows users to remotely access and manage their virtual machines on the host.

### Example 3: Update the virtual machine paths for a host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01" 
PS C:\> Set-SCVMHost -VMHost $VMHost -VMPaths "C:\ProgramData\Microsoft\Windows\Hyper-V|D:\VirtualMachinePath"
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command updates the VMPaths property for the host stored in $VMHost by adding the path D:\VirtualMachinePath to the list of virtual machine paths on that host.

### Example 4: Update the resource reserves for a host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01" 
PS C:\> Set-SCVMHost -VMHost $VMHost -CPUPercentageReserve 40 -DiskSpaceReserveMB 2048 -MaxDiskIOReservation 500 -MemoryReserveMB 1024 -NetworkPercentageReserve 40
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command updates the specified properties for VMHost01.

### Example 5: Update the bare-metal computer username and password for a specified physical host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02"
PS C:\> $BMCRAA = Get-SCRunAsAccount -Name "BMCCreds"
PS C:\> Set-SCVMHost $VMHost -BMCRunAsAccount $BMCRAA
PS C:\> Read-SCVMHost -VMHost $VMHost -RefreshOutOfBandProperties
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command gets the Run As account object named BMCCreds and stores the object in the $BMCRAA variable.

The third command updates the host stored in $VMHost with the new Run As account stored in $BMCRAA.

The last command refreshes the host stored in $VMHost using its out-of-band interface, which updates the Run As account for the host.

### Example 6: Update the certificates for XenServer hosts in a cluster
```
PS C:\> $VMHost = Get-VMHost -ComputerName "XenHost01" 
PS C:\> $Cert = Get-SCCertificate -Computername $VMHost.Name 
PS C:\> Set-SCVMHost -VMHost $VMHost -Certificate $Cert -EnableSecureMode $True
```

The first command gets the host object named XenHost01 and stores the object in the $VMhost variable.

The second gets the certificate object for XenHost01 and stores the object in the $Certificate variable.

The last command uses the certificate supplied in $Cert to enable VMM to communicate with XenHost01 in secure mode.

## PARAMETERS

### -ApplyLatestCodeIntegrityPolicy
Indicates that this cmdlet causes the host to update its HVCI policy using the file location stored in *CodeIntegrityPolicyPath*.

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

### -AttestationServerUrl
Specifies the URL of the attestation server.

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

### -AvailableForPlacement
Indicates whether the VMM placement process will consider this host or this volume on a host to be eligible as a possible location on which to deploy virtual machines.
If this parameter is set to $False, you can choose to deploy virtual machines on this host or volume anyway.
The default value is $True.
This parameter does not apply to VMware ESX hosts.

When you use this parameter with network adapters, if set to $False, then placement does not consider the logical networks configured on this network adapter to determine if the host is suitable for connecting a virtual machine.

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

### -BMCAddress
Specifies, or updates, the out-of-band baseboard management controller (BMC) address for a specific physical machine.
This might be an IP address, the fully qualified domain name (FQDN), or the DNS prefix (which is usually the same name as the NetBIOS name).

Typically, the BMC address and its connection to the network are separate from the IP address associated with a standard network adapter.
Alternatively, some computers do use a standard network adapter to provide a single address for the BMC and for the network adapter.
However, the BMC address has a unique port and is thus uniquely identifiable on the network.

- Example IPv4 format:       `-BMCAddress "10.0.0.21"`
- Example Ipv6 format:       `-BMCAddress "2001:4898:2a:3:657b:9c7a:e1f0:6829"`
- Example FQDN format:       `-BMCAddress "Computer01.Contoso.com"`
- Example NetBIOS format:    `-BMCAddress "Computer01"`

Note: By default, VMM uses an IP address or FQDN for the *BMCAddress*.
However, it is also possible to create a Windows PowerShell module that enables you to specify other types of addresses as the BMC address.

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

### -BMCCustomConfigurationProvider
Specifies, or updates, a configuration provider object for a baseboard management controller (BMC).
A configuration provider is a plug-in to VMM that translates VMM PowerShell commands to API calls that are specific to a type of BMC.
Use this parameter with the Custom *BMCProtocol*.

```yaml
Type: ConfigurationProvider
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCPort
Specifies, or updates, the out-of-band baseboard management controller (BMC) port for a specific physical machine.
A BMC port is also known as a service processor port.
Example default ports are 623 for IPMI and 443 for SMASH over WS-Man.

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

### -BMCProtocol
Specifies, or updates, the protocol that VMM uses to communicate with the out-of-band baseboard management controller (BMC).
Valid values are: 

- IPMI
- SMASH
- Custom

A BMC (also known as a service processor or management controller) is a specialized controller on the motherboard of a server that acts an interface between the hardware and system management software.
If the motherboard of a physical machine includes a BMC, when the machine is plugged in (whether it is powered off or powered on, and whether or not an operating system is installed), information about system hardware and the state of that system hardware health is available. 

Example format: `-BMCProtocol "Custom"`

Note: The Custom protocol requires that you use the *BMCCustomConfigurationProvider* parameter.

```yaml
Type: OutOfBandManagementType
Parameter Sets: (All)
Aliases: 
Accepted values: None, IPMI, SMASH, Custom

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCRunAsAccount
Specifies the Run As account to use with the baseboard management controller (BMC) device.

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

### -BaseDiskPaths
Specifies the paths to base disks.

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

### -BypassMaintenanceModeCheck
Indicates that Code Integrity policy gets applied to the host even if the host is not in maintenance mode.
By default, applying Code Integrity policy fails if the host is not in maintenance mode.

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

### -CPUPercentageReserve
Specifies the percentage of CPU to reserve for the use of the operating system on the physical host computer.
If you do not use this parameter to specify the reserve, the default setting for the host group is used: 10 percent.
The VMM placement process will not recommend that a virtual machine be placed on a host unless its resource requirements can be met without using host reserves.

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

### -CodeIntegrityPolicy
Specifies the Code Integrity policy to be used to restrict the software that can run on the host.

```yaml
Type: CodeIntegrityPolicy
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Custom1
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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
Specifies a custom property on a virtual machine host.

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

### -Description
Specifies a description for the Host object.

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

### -DiskSpaceReserveMB
Specifies the amount of disk space, in megabytes (MB), to reserve for the use of the operating system on the physical host computer.
If you do not use this parameter to specify the reserve, the default setting of 100 MB is used for the host group.
The VMM placement process will not recommend that a virtual machine be placed on a host unless its resource requirements can be met without using host reserves.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLiveMigration
Indicates whether live migration is enabled on the host.

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

### -FibreChannelWorldWideNodeName
Specifies the Fibre Channel world-wide node name.

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

### -FibreChannelWorldWidePortNameMaximum
Specifies the maximum value of the Fibre Channel world-wide port name range.

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

### -FibreChannelWorldWidePortNameMinimum
Specifies the minimum value of the Fibre Channel world-wide port name range.

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

### -IsDedicatedToNetworkVirtualizationGateway
Indicates whether the host is dedicated to a network virtualization gateway.

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

### -KeyProtectionServerUrl
Specifies the URL for the Key Protection Server (KPS).

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

### -LiveMigrationMaximum
Specifies the maximum number of simultaneous live migrations.

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

### -LiveStorageMigrationMaximum
Specifies the maximum number of simultaneous live storage migrations.

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

### -MaintenanceHost
This parameter is obsolete.
Use *AvailableForPlacement* instead.

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

### -ManagementAdapterMACAddress
Specifies the MAC address of the physical network adapter on the computer that is to be used by the VMM server to communicate with this host.

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

### -MaxDiskIOReservation
Specifies the maximum disk I/O per second (IOPS) on the physical host computer.
If you do not use this parameter to specify the reserve, the default setting of 10000 is used for the host group.
The VMM placement process will not recommend that a virtual machine be placed on a host unless its resource requirements can be met without using host reserves.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryReserveMB
Specifies the amount of memory, in megabytes (MB), to reserve for the use of the host operating system on the physical host computer.
If you do not use this parameter to specify the reserve, the default setting of 256 MB is used for the host group.
The VMM placement process will not recommend that a virtual machine be placed on a host unless its resource requirements can be met without using host reserves.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationAuthProtocol
Specifies the authorization protocol used for migration.
The acceptable values for this parameter are: CredSSP, Kerberos.

```yaml
Type: MigrationAuthProtocolType
Parameter Sets: (All)
Aliases: 
Accepted values: CredSSP, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationPerformanceOption
Specifies the migration performance option type.
The acceptable values for this parameter are:

- Standard
- UseCompression
- UseSmbTransport

```yaml
Type: MigrationPerformanceOptionType
Parameter Sets: (All)
Aliases: 
Accepted values: Standard, UseCompression, UseSmbTransport

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationSubnet
Specifies an array of subnets to use for migration.

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

### -NetworkPercentageReserve
Specifies the percentage of network capacity to reserve for the use of the host operating system on the physical host computer.
If you do not use this parameter to specify the reserve, the default setting of 10 percent is used for the host group.
The VMM placement process will not recommend that a virtual machine be placed on a host unless its resource requirements can be met without using host reserves.

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

### -NumaSpanningEnabled
Indicates whether NUMA spanning is enabled.

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

### -OverrideHostGroupReserves
Indicates, when set to $True, that the host reserve settings from the parent host group are overridden by the provided settings.

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

### -RemoteConnectCertificatePath
This parameter is obsolete.

```yaml
Type: String
Parameter Sets: (All)
Aliases: VMRCCertificatePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteConnectEnabled
Enables, when set to $True, a connection on a host server that lets users connect to their virtual machines remotely.
This parameter only applies to virtual machines on Hyper-V hosts.
It is not applicable to virtual machines on VMware ESX hosts or Citrix XenServer hosts.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: VMRCEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteConnectPort
Specifies a default value for the TCP port to use when a remote user connects to a virtual machine.
Typically, the default port for a Hyper-V host is 2179.
This parameter does not apply to VMware ESX hosts or Citrix XenServer hosts.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: VMRCPort

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveRemoteConnectCertificate
This parameter is obsolete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: RemoveVMRCCertificate

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

### -SMBiosGuid
Specifies the System Management BIOS globally unique identifier (SMBIOS GUID) for a physical computer that is associated with a record for that physical computer in VMM.
SMBIOS defines data structures and access methods that enable a user or application to store and retrieve information about hardware on this computer, such as the name of the system, manufacturer, or the system BIOS version.
Windows operating systems retrieve SMBIOS data at system startup and make that data available to programs.

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

### -SecureRemoteConnectEnabled
This parameter is obsolete.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SecureVMRCEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAnyMigrationSubnet
Indicates whether any subnet can be used for migration.

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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostManagementCredential
This parameter is obsolete.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: PerimeterNetworkHostCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMPaths
Specifies a set of default paths (as strings separated by the pipeline operator) on a host where virtual machine files can be stored.

Example format: `-VMPaths "C:\Folder1|C:\Folder2|C:\Folder3"`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Host
This cmdlet returns a **Host** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md)

[Get-SCCertificate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCertificate.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVMHost.md)

