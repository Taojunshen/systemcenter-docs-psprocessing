---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8A4C00A4-8F9C-41DA-824D-752EE2B0ED8B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCVMHost

## SYNOPSIS
Adds a computer as a virtual machine host.

## SYNTAX

### DomainJoined (Default)
```
Add-SCVMHost [-VMHostGroup <HostGroup>] [-VMMServer <ServerConnection>] [-ComputerName] <String>
 [-MaintenanceHost <Boolean>] [-AvailableForPlacement <Boolean>] [-Description <String>]
 [-CPUPercentageReserve <UInt16>] [-NetworkPercentageReserve <UInt16>] [-DiskSpaceReserveMB <UInt64>]
 [-MaxDiskIOReservation <UInt64>] [-MemoryReserveMB <UInt64>] [-VMPaths <String>] [-BaseDiskPaths <String>]
 [-RemoteConnectEnabled <Boolean>] [-RemoteConnectPort <UInt32>] [-EnableLiveMigration <Boolean>]
 [-LiveMigrationMaximum <UInt32>] [-LiveStorageMigrationMaximum <UInt32>] [-UseAnyMigrationSubnet <Boolean>]
 [-MigrationSubnet <String[]>] [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-Reassociate <Boolean>]
 -Credential <VMMCredential> [-IsDedicatedToNetworkVirtualizationGateway <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### XenServerHost
```
Add-SCVMHost [-VMHostGroup <HostGroup>] [-VMMServer <ServerConnection>] [-ComputerName] <String>
 [-MaintenanceHost <Boolean>] [-AvailableForPlacement <Boolean>] [-TCPPort <UInt32>]
 [-Certificate <ClientCertificate>] [-Description <String>] [-CPUPercentageReserve <UInt16>]
 [-NetworkPercentageReserve <UInt16>] [-DiskSpaceReserveMB <UInt64>] [-MaxDiskIOReservation <UInt64>]
 [-MemoryReserveMB <UInt64>] [-VMPaths <String>] [-BaseDiskPaths <String>] [-RemoteConnectEnabled <Boolean>]
 [-RemoteConnectPort <UInt32>] [-EnableLiveMigration <Boolean>] [-LiveMigrationMaximum <UInt32>]
 [-LiveStorageMigrationMaximum <UInt32>] [-UseAnyMigrationSubnet <Boolean>] [-MigrationSubnet <String[]>]
 [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-XenServerHost] [-EnableSecureMode <Boolean>]
 [-Reassociate <Boolean>] -Credential <VMMCredential> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ESXHost
```
Add-SCVMHost [-VMHostGroup <HostGroup>] -VirtualizationManager <VirtualizationManager>
 [-VMMServer <ServerConnection>] [-ComputerName] <String> [-MaintenanceHost <Boolean>]
 [-AvailableForPlacement <Boolean>] [-TCPPort <UInt32>] [-Certificate <ClientCertificate>]
 [-SshTcpPort <UInt32>] [-SshPublicKey <ClientSshPublicKey>] [-SshPublicKeyFile <String>]
 [-Description <String>] [-CPUPercentageReserve <UInt16>] [-NetworkPercentageReserve <UInt16>]
 [-DiskSpaceReserveMB <UInt64>] [-MaxDiskIOReservation <UInt64>] [-MemoryReserveMB <UInt64>]
 [-VMPaths <String>] [-BaseDiskPaths <String>] [-RemoteConnectEnabled <Boolean>] [-RemoteConnectPort <UInt32>]
 [-EnableLiveMigration <Boolean>] [-LiveMigrationMaximum <UInt32>] [-LiveStorageMigrationMaximum <UInt32>]
 [-UseAnyMigrationSubnet <Boolean>] [-MigrationSubnet <String[]>]
 [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-Reassociate <Boolean>]
 -Credential <VMMCredential> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### PerimeterNetwork
```
Add-SCVMHost [-VMHostGroup <HostGroup>] [-VMMServer <ServerConnection>] [-ComputerName] <String>
 [-MaintenanceHost <Boolean>] [-AvailableForPlacement <Boolean>] [-Description <String>]
 [-CPUPercentageReserve <UInt16>] [-NetworkPercentageReserve <UInt16>] [-DiskSpaceReserveMB <UInt64>]
 [-MaxDiskIOReservation <UInt64>] [-MemoryReserveMB <UInt64>] [-VMPaths <String>] [-BaseDiskPaths <String>]
 [-RemoteConnectEnabled <Boolean>] [-RemoteConnectPort <UInt32>] [-EnableLiveMigration <Boolean>]
 [-LiveMigrationMaximum <UInt32>] [-LiveStorageMigrationMaximum <UInt32>] [-UseAnyMigrationSubnet <Boolean>]
 [-MigrationSubnet <String[]>] [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-PerimeterNetworkHost]
 [-Reassociate <Boolean>] -SecurityFile <String> -EncryptionKey <PSCredential> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NonTrustedDomain
```
Add-SCVMHost [-VMHostGroup <HostGroup>] [-VMMServer <ServerConnection>] [-ComputerName] <String>
 [-MaintenanceHost <Boolean>] [-AvailableForPlacement <Boolean>] [-Description <String>]
 [-CPUPercentageReserve <UInt16>] [-NetworkPercentageReserve <UInt16>] [-DiskSpaceReserveMB <UInt64>]
 [-MaxDiskIOReservation <UInt64>] [-MemoryReserveMB <UInt64>] [-VMPaths <String>] [-BaseDiskPaths <String>]
 [-RemoteConnectEnabled <Boolean>] [-RemoteConnectPort <UInt32>] [-EnableLiveMigration <Boolean>]
 [-LiveMigrationMaximum <UInt32>] [-LiveStorageMigrationMaximum <UInt32>] [-UseAnyMigrationSubnet <Boolean>]
 [-MigrationSubnet <String[]>] [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-NonTrustedDomainHost]
 [-Reassociate <Boolean>] -Credential <VMMCredential> [-IsDedicatedToNetworkVirtualizationGateway <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Clustered
```
Add-SCVMHost -VMHostCluster <HostCluster> [-VMMServer <ServerConnection>] [-ComputerName] <String>
 [-MaintenanceHost <Boolean>] [-AvailableForPlacement <Boolean>] [-TCPPort <UInt32>]
 [-Certificate <ClientCertificate>] [-Description <String>] [-CPUPercentageReserve <UInt16>]
 [-NetworkPercentageReserve <UInt16>] [-DiskSpaceReserveMB <UInt64>] [-MaxDiskIOReservation <UInt64>]
 [-MemoryReserveMB <UInt64>] [-VMPaths <String>] [-BaseDiskPaths <String>] [-RemoteConnectEnabled <Boolean>]
 [-RemoteConnectPort <UInt32>] [-EnableLiveMigration <Boolean>] [-LiveMigrationMaximum <UInt32>]
 [-LiveStorageMigrationMaximum <UInt32>] [-UseAnyMigrationSubnet <Boolean>] [-MigrationSubnet <String[]>]
 [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-EnableSecureMode <Boolean>]
 [-Reassociate <Boolean>] -Credential <VMMCredential> [-IsDedicatedToNetworkVirtualizationGateway <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVMHost** cmdlet adds one or more computers as virtual machine hosts to Virtual Machine Manager (VMM).
A virtual machine host is a physical computer managed by VMM whose role is to host one or more virtual machines.

Virtual Machine Host Support in System Center 2016 - VMM

From the perspective of networking and domains, the types of hosts that System Center 2016 - VMM supports include: 

- Domain-joined Windows host.
The host can be located in either a trusted or untrusted domain. 
- Perimeter network Windows host.
A non-domain-joined Windows host can be managed in the same way as a perimeter network Windows host that is located in a domain. 
- A VMware ESX host.
ESX hosts do not use Windows Active Directory domains. 
- A Citrix XenServer host.
XenServer hosts are managed in the same way whether or not they are configured to use Windows Active Directory.

From the perspective of virtualization platform and operating system, the types of hosts that System Center 2016 - VMM supports include: 

- Hyper-V hosts.
A server running Windows Server 2008 or later with the Hyper-V role enabled. 
- VMware ESX hosts.
A VMware ESX host running proprietary software, including a hypervisor, that is managed by a VMware vCenter Server running Windows. 
- Citrix XenServer hosts.
A Citrix XenServer server running proprietary software, including a hypervisor.

System Center 2016 - VMM manages these three types of hosts, even though each host type implements virtualization in a different way.
The following sections describe each type of host in more detail.
You can review Preparing your environment for System Center 2016 - Virtual Machine Managerhttp://go.microsoft.com/fwlink/?LinkId=799436 in the Microsoft TechNet library at http://go.microsoft.com/fwlink/?LinkId=799436.

Before You Add a Hyper-V Host

- Review Managing Hyper-V hosts and host clusters with VMMhttp://go.microsoft.com/fwlink/?LinkID=799438 in the Microsoft TechNet library at http://go.microsoft.com/fwlink/?LinkID=799438. 
- The **Add-SCVMHost** cmdlet enables the Hyper-V server role for you, but you must first configure the Virtualization option in the BIOS manually.

Before You Add a Windows-Based Perimeter Network Host

To manage a Windows-based host in a perimeter network: 

- Install the VMM agent locally on the perimeter network host. 
- When you run VMM Setup and choose the option indicating that this host is on a perimeter network, the wizard prompts you to: 
   -- Provide an encryption key for the security file. 
    -- Specify where you want to store the security file. 
- After you have installed the local agent, obtain the security file from the folder in which it is stored.
The default location is C:\Program Files\Microsoft System Center 2016\Virtual Machine Manager, and the name of the security file is SecurityFile.txt
- Copy the security file to a location that is accessible to the computer on which a VMM console is installed. 
- When you use **Add-SCVMHost** to add the perimeter network host, you must specify the same encryption key and point to the local security file by using the *EncryptionKey* and *SecurityFile* parameters.
Followng is an example format for these parameters: 

`-SecurityFile "C:\SecurityFile.txt" -EncryptionKey $Key`

Example 2 outlines the cmdlets to use to add a perimeter network host.

Before You Add a VMware ESX Host

- Review System Requirements for System Center Technical Previewhttp://go.microsoft.com/fwlink/?LinkID=799442 in the Microsoft TechNet Library at http://go.microsoft.com/fwlink/?LinkID=799442.

Before You Add a Citrix XenServer Host

- Review System Requirements for System Center Technical Previewhttp://go.microsoft.com/fwlink/?LinkId=799442 in the Microsoft TechNet library at http://go.microsoft.com/fwlink/?LinkId=799442.

## EXAMPLES

### Example 1: Add a host in the same domain as the VMM server
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "RunAsAcct01"
PS C:\> Add-SCVMHost "VMHost01.Contoso.com" -Description "This is a new host" -RemoteConnectEnabled $True -RemoteConnectPort 5900 -Credential $RunAsAccount
```

The first command gets the Run As account object named HostComputer RunAsAccount and stores the object in the $RunAsAccount variable.The required credentials for this operation are either a local Administrator account or a domain account with administrator rights on the computer that you want to add as a host.

The second command adds the host object named VMHost01 in the Contoso domain to VMM as a managed host, specifies a description, enables remote connections, and specifies that TCP port 5900 will be used for remote connections to VMHost01.
As the last command is processed, $RunAsAccount provides credentials to **Add-SCVMHost**.

### Example 2: Add a host located in a perimeter network to VMM
```
PS C:\> $Key = Get-SCCredential
PS C:\> Add-SCVMHost "VMHost02" -Description "This is my new perimeter network host" -RemoteConnectEnabled $FALSE -PerimeterNetworkHost -SecurityFile "C:\SecurityFile.txt" -EncryptionKey $Key
```

The first command prompts you for a user name and password and stores the credentials in $Key.
The user name can be any user name, but the password must be the same encryption key that was used when the VMM agent was installed on this computer.
The VMM agent must be installed locally on a computer located in a perimeter network by choosing the local agent option when you run Setup.
You specify the encryption key for the security file on the Security File Folder page of the System Center Virtual Machine Manager Agent Setup wizard.

The second command adds a host object that represents the computer named VMHost02 to the VMM database as a managed host.
The command adds a description, disables remote connections, and specifies that this host is located in a perimeter network.
This command uses the credentials stored in $Key to decrypt the contents of SecurityFile.txt (which, in this example, is located at C:\\) and then uses the contents of SecurityFile.txt to authenticate the new host.

### Example 3: Add a host located in a non-trusted domain to VMM
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount02"
PS C:\> Add-SCVMHost "VMHost03.NonTrustedDomain.com" -VMMServer "VMMServer01.Contoso.com" -NonTrustedDomainHost -Credential $RunAsAccount
```

The first command gets the Run As account object named RunAsAccount02 and stores the object in the $RunAsAccount variable.
The required credentials for this operation are an account with administrator rights to add a host located in the non-trusted domain to the VMM server in the Contoso.com domain.

The second command adds VMHost03, located in a domain that is not trusted by Contoso.com, to the VMM database as a managed host.
As this command is processed, $RunAsAccont provides credentials to **Add-SCVMHost**.

### Example 4: Add a VMware ESX host to VMM
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup02"
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "ESX Host Computer Acct"
PS C:\> $VirtMgr = Get-SCVirtualizationManager -ComputerName "VirtMgrServer02.Contoso.com"
PS C:\> Add-SCVMHost -ComputerName "ESXHost01.Contoso.com" -Credential $RunAsAccount -VirtualizationManager $VirtMgr -VMHostGroup $HostGroup
```

The first command gets the host group object named HostGroup02 and stores the object in the $HostGroup variable.

The second command gets the Run As account object named ESX Host Computer Acct and stores the object in the $RunAsAccount variable.

The third command gets the virtualization manager object named VirtMgrServer02 and stores the object in the $VirtMgr variable.

The last command adds ESX Host01 to HostGroup02.
The command provides the credentials in the form of a Run As account stored in $RunAsAccount, which is required to add this host to VMM.

### Example 5: Add a Citrix XenServer host to VMM
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup04"
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "XenServer Run As Acct"
PS C:\> $Certificate = Get-SCCertificate -ComputerName "XenServerHost01.Contoso.com"
PS C:\> Add-SCVMHost -ComputerName "XenServerHost01.Contoso.com" -Credential $RunAsAccount -VMHostGroup $HostGroup -XenServerHost -Certificate $Certificate -EnableSecureMode $True -TCPPort 5989
```

The first command gets the host group object named HostGroup04 and stores the object in the $HostGroup variable.

The second command gets the Run As account object named XenServer Host Computer Acct and stores the object in the $RunAsAccount variable.
The required credentials for this operation are an account with root credentials on the XenServer host.

The third command gets the certificate object for XenServerHost01 and stores the object in the $Certificate variable.

The last command adds a XenServer as a host to HostGroup04 in VMM and provides the credentials in the form of a Run As account stored in $RunAsAccount, which is required to add this host to VMM.

## PARAMETERS

### -AvailableForPlacement
Indicates whether the VMM placement process will consider this host or this volume on a host to be eligible as a possible location on which to deploy virtual machines.
If this parameter is set to $False, you can choose to deploy virtual machines on this host or volume anyway.
The default value is True.
This parameter does not apply to VMware ESX hosts.

When you specify this parameter with network adapters, if set to $False, then placement will not consider the logical networks configured on this network adapter to determine if the host is suitable for connecting a virtual machine.

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

### -Certificate
Specifies a security certificate object.

```yaml
Type: ClientCertificate
Parameter Sets: XenServerHost, ESXHost, Clustered
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

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

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

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: DomainJoined, XenServerHost, ESXHost, NonTrustedDomain, Clustered
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the host.

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

If you do not use this parameter to specify the reserve, the default setting for the host group is used: 100 MB.
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

### -EnableSecureMode
Indicates whether VMM communicates with VMware ESX hosts and Citrix XenServer hosts in secure mode.
The default value is $True.

```yaml
Type: Boolean
Parameter Sets: XenServerHost, Clustered
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKey
Specifies credentials to be used as an encryption key when you add a Hyper-V host located in a perimeter network to VMM.

Example format: `-SecurityFile "C:\SecurityFile.txt" -EncryptionKey $Key`

```yaml
Type: PSCredential
Parameter Sets: PerimeterNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsDedicatedToNetworkVirtualizationGateway
Indicates whether the host is dedicated to a network virtualization gateway.

```yaml
Type: Boolean
Parameter Sets: DomainJoined, NonTrustedDomain, Clustered
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

### -MaxDiskIOReservation
Specifies the maximum disk I/O per second (IOPS) on the physical host computer.

If you do not use this parameter to specify the reserve, the default setting for the host group is used: 10000.
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

If you do not use this parameter to specify the reserve, the default setting for the host group is used: 256 MB.
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
Valid values are: CredSSP, Kerberos.

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
Valid values are: 

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

### -NonTrustedDomainHost
Indicates that the host to be added to VMM belongs to a non-trusted domain.

```yaml
Type: SwitchParameter
Parameter Sets: NonTrustedDomain
Aliases: 

Required: True
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

### -PerimeterNetworkHost
Indicates that this host is located in a perimeter network.

```yaml
Type: SwitchParameter
Parameter Sets: PerimeterNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reassociate
Reassociates a host currently managed by one VMM server with another VMM server.

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

### -SecurityFile
Specifies the path to a file that contains the certificate and credentials to use for authentication of a Hyper-V host located in a perimeter network.

This parameter does not apply to VMware ESX hosts or Citrix XenServer hosts.

Example format: `-SecurityFile "C:\SecurityFile.txt" -EncryptionKey $Key`

```yaml
Type: String
Parameter Sets: PerimeterNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshPublicKey
Specifies the public key used by Secure Shell (SSH) communications.

```yaml
Type: ClientSshPublicKey
Parameter Sets: ESXHost
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshPublicKeyFile
Specifies the path to the public key file for establishing a secured SSH channel with the target hosts.

```yaml
Type: String
Parameter Sets: ESXHost
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshTcpPort
Specifies the TCP port number used by the SSH protocol.

```yaml
Type: UInt32
Parameter Sets: ESXHost
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TCPPort
Specifies a numeric value that represents a TCP port.

```yaml
Type: UInt32
Parameter Sets: XenServerHost, ESXHost, Clustered
Aliases: 

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

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: Clustered
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: DomainJoined, XenServerHost, ESXHost, PerimeterNetwork, NonTrustedDomain
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

### -VirtualizationManager
Specifies a virtualization manager object managed by VMM.

```yaml
Type: VirtualizationManager
Parameter Sets: ESXHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -XenServerHost
Indicates that the specified host is a Citrix XenServer host.

```yaml
Type: SwitchParameter
Parameter Sets: XenServerHost
Aliases: 

Required: True
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

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md)

[Get-SCCertificate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCertificate.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualizationManager.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md)

[New-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHost.md)

[Repair-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVMHost.md)

