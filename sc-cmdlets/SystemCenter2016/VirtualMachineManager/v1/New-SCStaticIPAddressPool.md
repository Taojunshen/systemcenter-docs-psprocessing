---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalNetwork.md
schema: 2.0.0
ms.assetid: 76378267-52CF-4E89-A806-0130F1EE3422
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCStaticIPAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCStaticIPAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCStaticIPAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStaticIPAddressPool

## SYNOPSIS
Creates a static IP address pool.

## SYNTAX

### ByLogicalNetworkDefinition
```
New-SCStaticIPAddressPool [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -Subnet <String> [-Vlan <Int32>] [-VIPAddressSet <String>] [-IPAddressRangeStart <String>]
 [-IPAddressRangeEnd <String>] [-IPAddressReservedSet <String>] [-DNSSuffix <String>]
 [-EnableNetBIOS <Boolean>] -LogicalNetworkDefinition <LogicalNetworkDefinition> [-DNSServer <String[]>]
 [-WINSServer <String[]>] [-DNSSearchSuffix <String[]>] [-PxeServerAddress <String[]>]
 [-DefaultGateway <DefaultGateway[]>] [-NetworkRoute <SubnetNetworkRoute[]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### ByVMSubnet
```
New-SCStaticIPAddressPool [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -Subnet <String> [-VIPAddressSet <String>] [-IPAddressRangeStart <String>] [-IPAddressRangeEnd <String>]
 [-IPAddressReservedSet <String>] [-DNSSuffix <String>] [-EnableNetBIOS <Boolean>] -VMSubnet <VMSubnet>
 [-DNSServer <String[]>] [-WINSServer <String[]>] [-DNSSearchSuffix <String[]>] [-PxeServerAddress <String[]>]
 [-DefaultGateway <DefaultGateway[]>] [-NetworkRoute <SubnetNetworkRoute[]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### ByMulticastSwitch
```
New-SCStaticIPAddressPool [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -Subnet <String> [-IsMulticast] [-IPAddressRangeStart <String>] [-IPAddressRangeEnd <String>]
 [-IPAddressReservedSet <String>] -LogicalNetworkDefinition <LogicalNetworkDefinition> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStaticIPAddressPool** cmdlet creates a Virtual Machine Manager (VMM) static IP address pool.
A static IP address pool can be associated with one or more host groups.

## EXAMPLES

### Example 1: Create a static IP address pool
```
PS C:\>$HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $LogNet = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> $LogNetDef = Get-SCLogicalNetworkDefinition -VMHostGroup $HostGroup -LogicalNetwork $LogNet -Name "Logical Network Definition 01"
PS C:\> $DefaultGateway = New-SCDefaultGateway -IPAddress "10.0.0.1" -Metric 10
PS C:\> New-SCStaticIPAddressPool -LogicalNetworkDefinition $LogNetDef -Name "Production IP Address Pool" -Description "This IP address pool is used for LOB Apps in production" -Subnet "10.0.0.0/24" -IPAddressRangeStart "10.0.0.10" -IPAddressRangeEnd "10.0.0.99" -IPAddressReservedSet "10.0.0.25-10.0.0.35, 10.0.0.38" -VIPAddressSet "10.0.0.95-10.0.0.99" -DNSSuffix "domain.contoso.com" -DNSSearchSuffix domain1.contoso.com, domain2.contoso.com -DNSServer "10.0.0.1", "10.0.0.2" -WINSServer "10.0.0.1", "10.0.0.2" -DefaultGateway $DefaultGateway -EnableNetBIOS $True
```

The first command gets the host group that has the path All Hosts\HostGroup02\Production, and then stores that group it in the $HostGroup variable.

The second command gets the logical network named LogicalNetwork01, and stores that network in the $LogNet variable.

The third command gets the logical network definition named Logical Network Definition 01 for the host group stored in the $HostGroup variable.

The fourth command creates a default gateway, and then stores it in the $DefaultGateway variable.

The last command creates a static IP address pool that has the specified values.

## PARAMETERS

### -DNSSearchSuffix
Specifies an array of strings that are appended to a host name to resolve a DNS address.

```yaml
Type: String[]
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DNSServer
Specifies an array of IP addresses of DNS servers.
Valid formats are: IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DNSSuffix
Specifies the default DNS suffix associated with an adapter.

```yaml
Type: String
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultGateway
Specifies an array of default gateway objects.

```yaml
Type: DefaultGateway[]
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the address pool.

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

### -EnableNetBIOS
Indicates whether to enable NetBIOS over TCP/IP for an adapter.

```yaml
Type: Boolean
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
Aliases: 

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
Parameter Sets: (All)
Aliases: 

Required: False
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressReservedSet
Specifies a set of IP addresses in an IP subnet that is reserved for other use.

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

### -IsMulticast
Indicates that the IP address is a multicast address or that the IP address pool contains a multicast IP address range.

```yaml
Type: SwitchParameter
Parameter Sets: ByMulticastSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -LogicalNetworkDefinition
Specifies a logical network definition that contains the subnet that the IP address pool serves as specified by the *Subnet* parameter.
A logical network definition is also referred to as a network site.

```yaml
Type: LogicalNetworkDefinition
Parameter Sets: ByLogicalNetworkDefinition, ByMulticastSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name for the address pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkRoute
Specifies an array of network routes.

```yaml
Type: SubnetNetworkRoute[]
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
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
To obtain a user role, use the Get-SCUserRole cmdlet.
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

### -PxeServerAddress
Specifies a list of PXE Server IP Addresses.

```yaml
Type: String[]
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
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

### -Subnet
Specifies an IP subnet in Classless Inter-Domain Routing (CIDR) notation.
You can specify either IPv4 or IPv6 addresses.

An IP subnet cannot overlap with any other subnet in a host group or child host groups.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VIPAddressSet
Specifies a set of IP addresses in an IP subnet that is reserved for configuring virtual IPs (VIPs) in load balancers.

```yaml
Type: String
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
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

### -VMSubnet
Specifies a virtual machine subnet.

To obtain a **VMSubnet** object, use the Get-SCVMSubnet cmdlet.

```yaml
Type: VMSubnet
Parameter Sets: ByVMSubnet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vlan
Specifies a virtual local area network (VLAN).

```yaml
Type: Int32
Parameter Sets: ByLogicalNetworkDefinition
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WINSServer
Specifies an array of IP addresses of Windows Internet Name Service (WINS) servers.
Valid formats are: IPv4 and IPv6 addresses.

```yaml
Type: String[]
Parameter Sets: ByLogicalNetworkDefinition, ByVMSubnet
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

## NOTES

## RELATED LINKS

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalNetwork.md)

[Get-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalNetworkDefinition.md)

[Get-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCStaticIPAddressPool.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHostGroup.md)

[New-SCDefaultGateway](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCDefaultGateway.md)

[Remove-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCStaticIPAddressPool.md)

[Set-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCStaticIPAddressPool.md)

