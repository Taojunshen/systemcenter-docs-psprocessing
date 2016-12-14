---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCRunAsAccount.md
schema: 2.0.0
ms.assetid: 056AB857-513A-4DA2-9938-2C2552666F5C
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Find-SCComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Find-SCComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Find-SCComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Find-SCComputer

## SYNOPSIS
Searches for computers by querying Active Directory, and returns the computer objects.

## SYNTAX

### SearchComputersByNameFilter (Default)
```
Find-SCComputer [-VMMServer <ServerConnection>] [-ComputerNameFilter <String>] -Domain <String>
 -Credential <VMMCredential> [-ExcludeVMMHost] [-ExcludeVMMLibrary] [-ExcludeVMs] [-FindHyperVHost]
 [-DiscoveryID <Guid>] [-RunAsynchronously] [-JobVariable <String>] [<CommonParameters>]
```

### ValidateComputer
```
Find-SCComputer [-VMMServer <ServerConnection>] [-ComputerName] <String> [-Credential <VMMCredential>]
 [-ExcludeVMMHost] [-ExcludeVMMLibrary] [-DiscoveryID <Guid>] [-RunAsynchronously] [<CommonParameters>]
```

### SearchComputersByADQuery
```
Find-SCComputer [-VMMServer <ServerConnection>] -Domain <String> -ADSearchFilter <String>
 -Credential <VMMCredential> [-ExcludeVMMHost] [-ExcludeVMMLibrary] [-ExcludeVMs] [-FindHyperVHost]
 [-DiscoveryID <Guid>] [-RunAsynchronously] [-JobVariable <String>] [<CommonParameters>]
```

### SearchBMCByIPAddressRange
```
Find-SCComputer [-VMMServer <ServerConnection>] -IPAddressRangeStart <String> -IPAddressRangeEnd <String>
 -BMCProtocol <OutOfBandManagementType> [-BMCCustomConfigurationProvider <ConfigurationProvider>]
 [-BMCPort <Int32>] -BMCRunAsAccount <RunAsAccount> [-All] [-DiscoveryID <Guid>] [-RunAsynchronously]
 [-JobVariable <String>] [<CommonParameters>]
```

### SearchBMCByIPSubnet
```
Find-SCComputer [-VMMServer <ServerConnection>] -Subnet <String> -BMCProtocol <OutOfBandManagementType>
 [-BMCCustomConfigurationProvider <ConfigurationProvider>] [-BMCPort <Int32>] -BMCRunAsAccount <RunAsAccount>
 [-All] [-DiscoveryID <Guid>] [-RunAsynchronously] [-JobVariable <String>] [<CommonParameters>]
```

### ValidateBMC
```
Find-SCComputer [-VMMServer <ServerConnection>] -BMCAddress <String> -BMCProtocol <OutOfBandManagementType>
 [-BMCCustomConfigurationProvider <ConfigurationProvider>] [-BMCPort <Int32>] -BMCRunAsAccount <RunAsAccount>
 [-SMBiosGuid <Guid>] [-DeepDiscovery] [-DiscoveryID <Guid>] [-RunAsynchronously] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Find-SCComputer** cmdlet searches for one or more computers by querying Active Directory, and returns the computer objects. 

You can use this cmdlet to query Active Directory for computers based on specified criteria, or a combination of criteria, including: 



- The fully qualified domain name (FQDN) of a computer.

- All or part of the computer name.

- The name of a domain.

- All computers except hosts managed by Virtual Machine Manager (VMM). 

- All computers except library servers managed by VMM.

- Only Hyper-V hosts.

- Bare-metal computers that have out-of-band controllers.

Note: If you add a new computer, such as a host or library server, located in an Active Directory domain to VMM and then immediately run the **Discover-Computer** cmdlet, the cmdlet might not immediately discover the new computer when it searches Active Directory.
This delay may occur because data about the new computer might not have replicated yet across the Active Directory domain.
If you are a Domain Administrator, you can use the Active Directory Sites and Services console to force the data to replicate immediately.

## EXAMPLES

### Example 1: Search for computers in a specific domain that meet the specified criteria
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "Host Computer Account 01"
PS C:\> Find-SCComputer -ComputerNameFilter "host" -Domain "Contoso.com" -FindHyperVHosts -ExcludeVMMHost -RunAsAccount $RunAsAccount
```

The first command gets the Run As account object named Host Computer Account 01 and stores the object in the $RunAsAccount variable.

The second command queries Active Directory and returns a list of Hyper-V computer objects for computers that are located in the Contoso.com domain, that have a name starting with "host", and that are not managed by VMM.
As this command is processed, $RunAsAccount provides credentials to **Find-SCComputer**.

Note: When you use **Find-SCComputer** with the *Domain* parameter, you must specify the fully qualified domain name.

### Example 2: Search for a specific computer by name and validate its properties in Active Directory
```
PS C:\>Find-SCComputer -ComputerName "VMHost01.Contoso.com"
```

This command uses the fully qualified domain name (FQDN) of the computer named VMHost01 to find this computer in Active Directory, returns the computer object, and displays the computer object properties to the user.

### Example 3: Search for all computers in the specified domain that are not a VMM library server
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "Host Computer Account 01"
PS C:\> Find-SCComputer -ComputerNameFilter "vmm" -Domain "Contoso.com" -ExcludeVMMLibrary -RunAsAccount $RunAsAccount
```

The first command gets the Run As account object named Host Computer Account 01 and stores the object in the $RunAsAccount variable.

The second command queries Active Directory for all computers in the Contoso.com domain that include "vmm" in the computer name except for VMM library servers.
As this command is processed, $RunAsAccount provides credentials to **Find-SCComputer**.

### Example 4: Find all unmanaged computers in the specified domain by using an Active Directory query
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "Host Computer Account 01"
PS C:\> Find-SCComputer -ADSearchFilter "(&(sAMAccountType=805306369)(name=Test0*)(objectCategory=computer)(objectClass=computer)(operatingSystem=Windows\20Server\202008\20R2*))" -Domain "Contoso.com" -ExcludeVMMLibrary -ExcludeVMMHost -RunAsAccount $RunAsAccount
```

The first command gets the Run As account object named Host Computer Account 01 and stores the object in the $RunAsAccount variable.

The second command queries Active Directory for all computers in the Contoso.com domain that meet the query criteria: any Windows Server 2008 R2 computer with a name that starts with Test0 but which are not VMM library servers or VMM hosts.
As this command is processed, $RunAsAccount provides credentials to **Find-SCComputer**.

### Example 5: Find bare-metal computers that have out-of-band controllers that are within a specific network range
```
PS C:\>$BMCRunAsAccount = Get-SCRunAsAccount "BMC Account 01"
PS C:\> Find-SCComputer -BMCAddress "10.10.0.1" -BMCRunAsAccount $BMCRunAsAccount -BMCProtocol "IPMI"
```

The first command gets the Run As account object named BMC Account 01 and stores the object in the $BMCRunAsAccount variable.

The second command scans the network for a physical computer with the specified BMCAddress.
As this command is processed, $BMCRunAsAccount provides credentials to **Find-SCComputer**.

### Example 6: Perform deep discovery on a physical machine with bare-metal computer support
```
PS C:\>$BMCRunAsAccount = Get-SCRunAsAccount "BMC Account 01"
PS C:\> $MyComputer01 = Find-SCComputer -BMCAddress "10.10.0.1" -BMCRunAsAccount $BMCRunAsAccount -BMCProtocol "IPMI" 
PS C:\> $MyComputer01 = Find-SCComputer -DeepDiscovery -BMCAddress $MyComputer01.BMCAddress -BMCRunAsAccount $BMCRunAsAccount -BMCProtocol "IPMI" -SMBIOSGUID $MyComputer01.SMBIOSGUID
PS C:\> $MyComputer01
```

The first command gets the Run As account object named BMC Account 01 and stores the object in the $BMCRunAsAccount variable.

The second command scans the network for a physical computer with the specified BMCAddress.
As this command is processed, $BMCRunAsAccount provides credentials to **Find-SCComputer**.

The third command performs the deep discovery on the computer object and returns the physical machine object to $MyComputer01 variable.

The last command displays the properties of the computer object stored in the $MyComputer01 variable.

## PARAMETERS

### -ADSearchFilter
Defines an Active Directory query for discovery.
Use this parameter to specify a query that contains Active Directory domain information and search filters. 



Example format: `-ADSearchFilter``"(&(sAMAccountType=805306369)(name=katarina*)(objectCategory=computer)(objectClass =computer)(operatingSystem=Windows\20Server*))"`

```yaml
Type: String
Parameter Sets: SearchComputersByADQuery
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.

```yaml
Type: SwitchParameter
Parameter Sets: SearchBMCByIPAddressRange, SearchBMCByIPSubnet
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



Example IPv4 format:       `-BMCAddress "10.0.0.21"`

Example Ipv6 format:       `-BMCAddress "2001:4898:2a:3:657b:9c7a:e1f0:6829"`

Example FQDN format:       `-BMCAddress "Computer01.Contoso.com"`

Example NetBIOS format:    `-BMCAddress "Computer01"`

Note: By default, VMM uses an IP address or FQDN for the BMC Address.
However, it is also possible to create a PowerShell module that enables you to specify other types of addresses as the BMC address.

```yaml
Type: String
Parameter Sets: ValidateBMC
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCCustomConfigurationProvider
Specifies, or updates, a configuration provider object for a baseboard management controller (BMC).
A configuration provider is a plug-in to VMM that translates VMM PowerShell commands to API calls that are specific to a type of baseboard management controller.
This parameter should be used with the Custom BMCProtocol.

```yaml
Type: ConfigurationProvider
Parameter Sets: SearchBMCByIPAddressRange, SearchBMCByIPSubnet, ValidateBMC
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
Type: Int32
Parameter Sets: SearchBMCByIPAddressRange, SearchBMCByIPSubnet, ValidateBMC
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
Parameter Sets: SearchBMCByIPAddressRange, SearchBMCByIPSubnet, ValidateBMC
Aliases: 
Accepted values: IPMI, SMASH, Custom

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCRunAsAccount
Specifies the Run As account to use with the baseboard management controller (BMC) device.

```yaml
Type: RunAsAccount
Parameter Sets: SearchBMCByIPAddressRange, SearchBMCByIPSubnet, ValidateBMC
Aliases: 

Required: True
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
-  NetBIOS name

```yaml
Type: String
Parameter Sets: ValidateComputer
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerNameFilter
Specifies the partial or full name of a computer that the cmdlet will try to discover in Active Directory. 



Example format: `-ComputerNameFilter "host"`

```yaml
Type: String
Parameter Sets: SearchComputersByNameFilter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of Restart-SCJob, has permission to complete a restarted task.

For more information about the PSCredential object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: SearchComputersByNameFilter, SearchComputersByADQuery
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: VMMCredential
Parameter Sets: ValidateComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeepDiscovery
Indicates that deep discovery is used for the specified computer.

```yaml
Type: SwitchParameter
Parameter Sets: ValidateBMC
Aliases: 

Required: False
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

### -Domain
Specifies a fully qualified domain name (FQDN) for an Active Directory domain. 



Example format: `-Domain "Domain01.Corp.Contoso.com"`

```yaml
Type: String
Parameter Sets: SearchComputersByNameFilter, SearchComputersByADQuery
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeVMMHost
Excludes virtual machine hosts currently managed by VMM.

```yaml
Type: SwitchParameter
Parameter Sets: SearchComputersByNameFilter, ValidateComputer, SearchComputersByADQuery
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeVMMLibrary
Excludes library servers currently managed by VMM.

```yaml
Type: SwitchParameter
Parameter Sets: SearchComputersByNameFilter, ValidateComputer, SearchComputersByADQuery
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeVMs
Excludes virtual machines.

```yaml
Type: SwitchParameter
Parameter Sets: SearchComputersByNameFilter, SearchComputersByADQuery
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FindHyperVHost
Searches for computers running Windows Server 2008 or later on which the Hyper-V server role is enabled.

```yaml
Type: SwitchParameter
Parameter Sets: SearchComputersByNameFilter, SearchComputersByADQuery
Aliases: FindHyperVHosts

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressRangeEnd
Specifies the last IP address in a range of IP addresses.
Use with the *IPAddressRangeStart* parameter.

```yaml
Type: String
Parameter Sets: SearchBMCByIPAddressRange
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressRangeStart
Specifies the first IP address in a range of IP addresses.
Use with the *IPAddressRangeEnd* parameter.

```yaml
Type: String
Parameter Sets: SearchBMCByIPAddressRange
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

```yaml
Type: String
Parameter Sets: SearchComputersByNameFilter, SearchComputersByADQuery, SearchBMCByIPAddressRange, SearchBMCByIPSubnet, ValidateBMC
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

### -SMBiosGuid
Specifies the System Management BIOS globally unique identifier (SMBIOS GUID) for a physical computer that is associated with a record for that physical computer in VMM.

SMBIOS defines data structures and access methods that enable a user or application to store and retrieve information about hardware on this computer, such as the name of the system, manufacturer, or the system BIOS version.
Windows operating systems retrieve SMBIOS data at system startup and make that data available to programs.

```yaml
Type: Guid
Parameter Sets: ValidateBMC
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies an IP subnet (IPv4 or IPv6) in Classless Inter-Domain Routing (CIDR) notation. 



Example format for an IPv4 subnet: `192.168.0.1/24`

Example format for an IPv6 subnet: `FD4A:29CD:184F:3A2C::/64`

Note: An IP subnet cannot overlap with any other subnet in a host group or child host groups.

```yaml
Type: String
Parameter Sets: SearchBMCByIPSubnet
Aliases: 

Required: True
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
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Computer
This cmdlet returns a **Computer** object.

## NOTES

## RELATED LINKS

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCRunAsAccount.md)

