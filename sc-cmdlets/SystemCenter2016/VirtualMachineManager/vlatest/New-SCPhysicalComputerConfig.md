---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6CAA3842-1199-4C19-A7C1-F08B99D11941
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerConfig.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerConfig.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerConfig.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCPhysicalComputerConfig

## SYNOPSIS
Creates a computer configuration object.

## SYNTAX

### SkipBMCPowerControl
```
New-SCPhysicalComputerConfig -PhysicalComputerProfile <PhysicalComputerProfile> [-SMBiosGuid <Guid>]
 [-SkipBmcPowerControl] -PhysicalComputerNetworkAdapterConfig <PhysicalComputerNetworkAdapterConfig[]>
 [-VMMServer <ServerConnection>] [-Description <String>] -ComputerName <String> [-VMHostGroup <HostGroup>]
 [-BypassADMachineAccountCheck] [-BootDiskVolume <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### UseBMCPowerControl
```
New-SCPhysicalComputerConfig -PhysicalComputerProfile <PhysicalComputerProfile> [-SMBiosGuid <Guid>]
 -BMCAddress <String> -BMCRunAsAccount <RunAsAccount> [-BMCPort <Int32>] -BMCProtocol <OutOfBandManagementType>
 [-BMCCustomConfigurationProvider <ConfigurationProvider>]
 -PhysicalComputerNetworkAdapterConfig <PhysicalComputerNetworkAdapterConfig[]> [-VMMServer <ServerConnection>]
 [-Description <String>] -ComputerName <String> [-VMHostGroup <HostGroup>] [-BypassADMachineAccountCheck]
 [-BootDiskVolume <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### FromExistingComputer
```
New-SCPhysicalComputerConfig -PhysicalComputerProfile <PhysicalComputerProfile> [-BMCAddress <String>]
 [-BMCRunAsAccount <RunAsAccount>] [-BMCPort <Int32>] [-BMCProtocol <OutOfBandManagementType>]
 [-BMCCustomConfigurationProvider <ConfigurationProvider>]
 [-PhysicalComputerNetworkAdapterConfig <PhysicalComputerNetworkAdapterConfig[]>]
 [-VMMServer <ServerConnection>] [-Description <String>] [-ComputerName <String>] [-BootDiskVolume <String>]
 -Computer <ClientObject> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCPhysicalComputerConfig** cmdlet creates a computer configuration object that is used during the operating system customization process.

## EXAMPLES

### Example 1: Create a physical computer configuration
```
PS C:\> $Account = Get-SCRunaAsAccount -Name "BMCAdmin" 
PS C:\> $PhysicalComputerProfile = Get-SCPhysicalComputerProfile -ID "d1ce0773-4f50-4f12-a244-38a5a35c5326" 
PS C:\> $NetworkAdapters = New-SCPhysicalComputerNetworkAdapterConfig -UseDhcpForIPConfiguration -SetAsManagementNIC -SetAsPhysicalNetworkAdapter 
PS C:\> $HostGroup = Get-SCVMHostGroup -ID "0e3ba228-a059-46be-aa41-2f5cf0f4b96e" 
PS C:\> New-SCPhysicalComputerConfig -BMCAddress 10.0.0.21 -BMCPort 623 -BMCProtocol IPMI -BMCRunAsAccount $Account -ComputerName "Host01" -SMBiosGuid "4c4c4544-0039-4410-8042-c3c04f395031" -PhysicalComputerProfile $PhysicalComputerProfile -VMHostGroup $HostGroup -PhysicalComputerNetworkAdapterConfig $NetworkAdapters
```

The first command gets a Run As account object and stores it in the $Account variable.

The second command stores the physical computer profile that has the ID d1ce0773-4f50-4f12-a244-38a5a35c5326 in the $PhysicalComputerProfile variable.

The third command creates a physical computer network adapter configuration and stores in the $NetworkAdapters variable.

The fourth cmdlet stores the host group in the $HostGroup variable.

The final command creates a physical computer configuration.
The command specifies the values created in previous commands.

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

Note: By default, VMM uses an IP address or FQDN for the BMC address.
However, it is also possible to create a PowerShell module that enables you to specify other types of addresses as the BMC address.

```yaml
Type: String
Parameter Sets: UseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: FromExistingComputer
Aliases: 

Required: False
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
Parameter Sets: UseBMCPowerControl, FromExistingComputer
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
Parameter Sets: UseBMCPowerControl, FromExistingComputer
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
Parameter Sets: UseBMCPowerControl
Aliases: 
Accepted values: None, IPMI, SMASH, Custom

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: OutOfBandManagementType
Parameter Sets: FromExistingComputer
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
Parameter Sets: UseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: RunAsAccount
Parameter Sets: FromExistingComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BootDiskVolume
Specifies a physical hard disk object for a physical machine.

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

### -BypassADMachineAccountCheck
Indicates that this cmdlet will reuse a computer account that already exists in Active Directory.
By default, this cmdlet checks Active Directory for an existing account with the specified name to prevent overwriting computer accounts.

```yaml
Type: SwitchParameter
Parameter Sets: SkipBMCPowerControl, UseBMCPowerControl
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Computer
Specifies, or updates, the out-of-band baseboard management controller (BMC) address for a specific physical machine.
This might be an IP address, the fully qualified domain name (FQDN), or the DNS prefix (which is usually the same name as the NetBIOS name).

- Example IPv4 format:       `-BMCAddress "10.0.0.21"`
- Example Ipv6 format:       `-BMCAddress "2001:4898:2a:3:657b:9c7a:e1f0:6829"`
- Example FQDN format:       `-BMCAddress "Computer01.Contoso.com"`
- Example NetBIOS format:    `-BMCAddress "Computer01"`

Note: By default, VMM uses an IP address or FQDN for the BMC address.
However, it is also possible to create a PowerShell module that enables you to specify other types of addresses as the BMC address.

```yaml
Type: ClientObject
Parameter Sets: FromExistingComputer
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
- NetBIOS name

```yaml
Type: String
Parameter Sets: SkipBMCPowerControl, UseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: FromExistingComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the configuration object.

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

### -PhysicalComputerNetworkAdapterConfig
Specifies an array of **PhysicalComputerNetworkAdapterConfig** objects.

```yaml
Type: PhysicalComputerNetworkAdapterConfig[]
Parameter Sets: SkipBMCPowerControl, UseBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: PhysicalComputerNetworkAdapterConfig[]
Parameter Sets: FromExistingComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalComputerProfile
Specifies a profile that is used to deploy an operating system to a computer.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: (All)
Aliases: 

Required: True
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
Parameter Sets: SkipBMCPowerControl, UseBMCPowerControl
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipBmcPowerControl
Skips BMC information and deploys an operating system without powering the computer on or off by using its BMC interface.

```yaml
Type: SwitchParameter
Parameter Sets: SkipBMCPowerControl
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: SkipBMCPowerControl, UseBMCPowerControl
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PhysicalComputerConfig
This cmdlet returns a **PhysicalComputerConfig** object.

## NOTES

## RELATED LINKS

