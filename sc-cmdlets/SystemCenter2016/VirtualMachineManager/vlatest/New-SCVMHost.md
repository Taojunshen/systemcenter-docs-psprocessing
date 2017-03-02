---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 502C89EA-1026-4A77-9888-C46989674945
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCVMHost

## SYNOPSIS
Creates a VMM host from a physical computer by using the properties defined in a host profile.

## SYNTAX

### LegacySkipBMCPowerControl (Default)
```
New-SCVMHost [-VMMServer <ServerConnection>] [-Description <String>] -ComputerName <String>
 -VMHostProfile <PhysicalComputerProfile> -SMBiosGuid <Guid> [-VMHostGroup <HostGroup>] [-IPAddress <String>]
 [-LogicalNetwork <LogicalNetwork>] [-Subnet <String>] [-BypassADMachineAccountCheck]
 [-ManagementAdapterMACAddress <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### LegacyUseBMCPowerControl
```
New-SCVMHost [-VMMServer <ServerConnection>] [-Description <String>] -ComputerName <String>
 -VMHostProfile <PhysicalComputerProfile> -SMBiosGuid <Guid> [-VMHostGroup <HostGroup>] [-IPAddress <String>]
 [-LogicalNetwork <LogicalNetwork>] [-Subnet <String>] [-BypassADMachineAccountCheck]
 [-ManagementAdapterMACAddress <String>] -BMCAddress <String> -BMCRunAsAccount <RunAsAccount>
 [-BMCPort <UInt32>] -BMCProtocol <OutOfBandManagementType>
 [-BMCCustomConfigurationProvider <ConfigurationProvider>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### UseHostConfig
```
New-SCVMHost [-VMMServer <ServerConnection>] -VMHostConfig <PhysicalComputerConfig> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMHost** cmdlet creates a Virtual Machine Manager (VMM) host from a physical computer by using the properties defined in a host profile.
The physical computer must have an out-of-band controller.

Before you create a host, ensure that a PXE server has been added to VMM, a host profile has been created, and any needed driver files have been added to the library.
Note: The PXE server you add to VMM must be in the same subnet as the physical computers that you want to convert to managed Hyper-V hosts.

For more information about the types of hosts supported by VMM, type `Get-Help Add-SCVMHost -Detailed`.

## EXAMPLES

### Example 1: Create a host from a physical computer by using a DHCP-based host profile
```
PS C:\> $BMCRAA = Get-SCRunAsAccount -Name "BMCRunAsAcct"
PS C:\> $NewPhysicalComputer = Find-SCComputer -BMCAddress "10.10.0.1" -BMCRunAsAccount $BMCRAA -BMCProtocol "IPMI"
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "HostGroup01"
PS C:\> $HostProfile = Get-SCVMHostProfile -Name "HostProfile01"
PS C:\> New-SCVMHost -VMHostGroup $HostGroup -VMHostProfile $HostProfile -ComputerName "NewHost01" -BMCAddress $NewPhysicalComputer.BMCAddress -BMCRunAsAccount $BMCRAA -BMCProtocol "IPMI" -SMBIOSGUID $NewPhysicalComputer.SMBIOSGUID -ManagementAdapterMACAddress "00-1D-D8-B7-1C-00" -LogicalNetwork "LogicalNetwork01" -Subnet "192.168.0.1/24" -IPAddress "192.168.0.91"
```

The first command gets the Run As account object named BMCRunAsAcct and stores the object in the $BMCRAA variable.

The second command discovers the physical computer with the IP address of 10.10.0.1 using the Run As account supplied in $BMCRAA.
It then stores the physical computer in the $NewPhysicalComputer variable.

The third command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The fourth command gets the host profile object named HostProfile01 and stores the object in the $HostProfile variable.
HostProfile01 is configured to obtain an IP address through the DHCP service.

The last command creates a host from the physical computer stored in $NewPhysicalComputer using the host profile stored in $HostProfile, and names it NewHost01.

### Example 2: Create a host from a physical computer by using a static IP-based host profile
```
PS C:\> $BMCRAA = Get-SCRunAsAccount -Name "BMCRunAsAcct"
PS C:\> $NewPhysicalComputer = Find-SCComputer -BMCAddress "10.10.0.1" -BMCRunAsAccount $BMCRAA -BMCProtocol "IPMI"
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "HostGroup01"
PS C:\> $HostProfile = Get-SCVMHostProfile -Name "HostProfile02"
PS C:\> New-SCVMHost -VMHostGroup $HostGroup -VMHostProfile $HostProfile -BMCAddress $NewPhysicalComputer.BMCAddress -BMCRunAsAccount $BMCRAA -BMCProtocol "IPMI" -SMBIOSGUID $NewPhysicalComputer.SMBIOSGUID -ComputerName "NewHost02" -ManagementAdapterMACAddress "00-18-8B-0A-4D-76" -LogicalNetwork "LogicalNetwork01" -Subnet "192.168.1.1/24" -IPAddress "192.168.1.101"
```

The first command gets the Run As account object named BMCRunAsAccount and stores the object in the $BMCRAA variable.

The second command discovers the computer with the address 10.10.0.1, using the Run As account stored in $BMCRAA, and then stores the computer in the $NewPhysicalComputer variable.

The third command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The fourth command gets the host profile object named HostProfile02 and stores the object in the $HostProfile variable.
HostProfile02 is configured to allocate a static IP address.

The last command creates a host from the physical computer stored in $NewPhysicalComputer using the host profile stored in $HostProfile, gives it the name NewHost02, and configures the MAC address, IPAddress, and subnet.

### Example 3: Redeploy an existing host with a new host profile
```
PS C:\> $BMCRaa = Get-SCRunAsAccount -Name "BMCRunAsAcct"
PS C:\> $OldHost = Get-SCVMHost "NewHost02"
PS C:\> $OldBMCIP = $OldHost.physicalmachine.BMCAddress
PS C:\> $OldBMCProtocol = $OldHost.physicalmachine.BMCType
PS C:\> $OldComputer = Find-SCComputer -BMCAddress $OldBMCIP -BMCRunAsAccount $BMCRAA -BMCProtocol $OldBMCProtocol
PS C:\> $OldGuid = $OldComputer.SMBIOSGUID
PS C:\> $OldAdapter = Get-SCVMHostNetworkAdapter -VMHost $OldHost
PS C:\> $OldMAC = $OldAdapter[0].macaddress
PS C:\> $OldRAA = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Remove-SCVMHost $OldHost -Credential $OldRAA
PS C:\> $NewHostGroup = Get-SCVMHostGroup -Name "HostGroup01"
PS C:\> $NewHostProfile = Get-SCVMHostProfile -Name "HostProfile02"
PS C:\> New-SCVMHost -VMHostGroup $NewHostGroup -VMHostProfile $NewHostProfile  -BMCAddress $OldBMCIP -BMCRunAsAccount $BMcRAA -BMCProtocol $OldBMCProtocol -SMBIOSGUID $OldGUID -ManagementAdapterMACAddress $OldMAC -ComputerName "Computer01" -LogicalNetwork "LogicalNetwork01" -Subnet "192.168.0.1/24" -IPAddress "192.168.0.93"
```

The first command gets the Run As account object named BMCRunAsAccount and stores the object in the $BMCRaa variable.

The next eight commands save properties from the host that you are going to redeploy.

The tenth command removes the old host from VMM.

The eleventh command gets the host group object named New HostGroup01 and stores the object in the $NewHostGroup variable.

The twelfth command gets the host profile object named HostProfile02 and stores the object in the $NewHostProfile variable.

The last command redeploys the old host using the previous settings that identify the host, but to a new host gorup (stored in $NewHostGroup) and with updated profile settings (stored in $NewHostProfile).

## PARAMETERS

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

Note: By default, VMM uses an IP address or FQDN for the BMCAddress.
However, it is also possible to create a Windows PowerShell module that enables you to specify other types of addresses as the BMC address.

```yaml
Type: String
Parameter Sets: LegacyUseBMCPowerControl
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
You should use this parameter with the Custom BMCProtocol.

```yaml
Type: ConfigurationProvider
Parameter Sets: LegacyUseBMCPowerControl
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
Parameter Sets: LegacyUseBMCPowerControl
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCProtocol
Specifies, or updates, the protocol that VMM uses to communicate with the out-of-band baseboard management controller (BMC).
Valid values are: IPMI, SMASH, Custom.

A BMC (also known as a service processor or management controller) is a specialized controller on the motherboard of a server that acts an interface between the hardware and system management software.
If the motherboard of a physical machine includes a BMC, when the machine is plugged in (whether it is powered off or powered on, and whether or not an operating system is installed), information about system hardware and the state of that system hardware health is available.

Example format: `-BMCProtocol "Custom"`

Note: The Custom protocol requires that you use the *BMCCustomConfigurationProvider* parameter.

```yaml
Type: OutOfBandManagementType
Parameter Sets: LegacyUseBMCPowerControl
Aliases: 
Accepted values: None, IPMI, SMASH, Custom

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
Parameter Sets: LegacyUseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BypassADMachineAccountCheck
Indicates that this cmdlet reuses a computer account that already exists in Active Directory.
By default, **New-SCVMHost** checks Active Directory for an existing account with the specified name to prevent overwriting computer accounts.

```yaml
Type: SwitchParameter
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
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
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the VMM host.

```yaml
Type: String
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an IPv4 or IPv6 address.

```yaml
Type: String
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and VLANs that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
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
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
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
Windows gets SMBIOS data at system startup and makes that data available to programs.

```yaml
Type: Guid
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Specifies an IP subnet (IPv4 or IPv6) in Classless Inter-Domain Routing (CIDR) notation. 

- Example format for an IPv4 subnet: `192.168.0.1/24`
- Example format for an IPv6 subnet: `FD4A:29CD:184F:3A2C::/64`

Note: An IP subnet cannot overlap with any other subnet in a host group or child host groups.

```yaml
Type: String
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostConfig
Specifies a physical computer configuration object.

```yaml
Type: PhysicalComputerConfig
Parameter Sets: UseHostConfig
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
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostProfile
Specifies a virtual machine host profile object.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: LegacySkipBMCPowerControl, LegacyUseBMCPowerControl
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
* Requires a host profile object, which can be retrieved using the **Get-SCVMHostProfile** cmdlet.

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md)

[Find-SCComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Find-SCComputer.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Get-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostNetworkAdapter.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHost.md)

[Repair-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVMHost.md)

