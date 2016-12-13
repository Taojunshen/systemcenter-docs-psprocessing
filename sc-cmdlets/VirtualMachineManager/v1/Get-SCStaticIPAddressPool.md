---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostGroup.md
schema: 2.0.0
ms.assetid: FC9E10E4-4FFE-4A4F-A308-2F0BFAC3034C
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStaticIPAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStaticIPAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStaticIPAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStaticIPAddressPool

## SYNOPSIS
Gets static IP address pools.

## SYNTAX

### All (Default)
```
Get-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-IPAddress <String>] [-IPv4] [-IPv6]
 [[-Name] <String>] [-IsMulticast] [-Subnet <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByLogicalNetworkDefinition
```
Get-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-IPAddress <String>] [-IPv4] [-IPv6]
 -LogicalNetworkDefinition <LogicalNetworkDefinition> [[-Name] <String>] [-IsMulticast] [-Subnet <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByVMSubnet
```
Get-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-IPAddress <String>] [-IPv4] [-IPv6]
 -VMSubnet <VMSubnet> [[-Name] <String>] [-IsMulticast] [-Subnet <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByHostGroup
```
Get-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-IPAddress <String>] [-IPv4] [-IPv6]
 [[-Name] <String>] [-IsMulticast] [-Subnet <String>] -VMHostGroup <HostGroup> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByCloud
```
Get-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-IPAddress <String>] [[-Name] <String>]
 [-IsMulticast] [-Subnet <String>] -Cloud <Cloud> [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### ById
```
Get-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-IPAddress <String>] [[-Name] <String>]
 [-IsMulticast] [-Subnet <String>] -ID <Guid> [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStaticIPAddressPool** cmdlet gets one or more Virtual Machine Manager (VMM) static IP address pools.

## EXAMPLES

### Example 1: Get all available IPv4 IP address pools for a subnet
```
PS C:\>Get-SCStaticIPAddressPool -IPv4 -Subnet "10.0.0.0/24"
```

This command gets the static IP address pool for the specified IPv4 subnet address.

### Example 2: Get all IPv4 IP address pools for a host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> Get-SCStaticIPAddressPool -IPv4 -VMHostGroup $HostGroup
```

The first command gets the host group that has the path All Hosts\HostGroup02\Production, and then stores that group in the $HostGroup variable.

The second command gets the static IPv4 IP address pools for the host group stored in $HostGroup.

## PARAMETERS

### -Cloud
Specifies a private cloud object in which this cmdlet gets address pools.

```yaml
Type: Cloud
Parameter Sets: ByCloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the unique ID for an address pool that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an IPv4 or IPv6 address.

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

### -IPv4
Indicates that an IPv4 address is needed.

```yaml
Type: SwitchParameter
Parameter Sets: All, ByLogicalNetworkDefinition, ByVMSubnet, ByHostGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6
Indicates that an IPv6 address is needed.

```yaml
Type: SwitchParameter
Parameter Sets: All, ByLogicalNetworkDefinition, ByVMSubnet, ByHostGroup
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
Parameter Sets: ByLogicalNetworkDefinition
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the address pool that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### -Subnet
Specifies an IP subnet in Classless Inter-Domain Routing (CIDR) notation.
You can specify either IPv4 or IPv6 addresses.

An IP subnet cannot overlap with any other subnet in a host group or child host groups.

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

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: ByHostGroup
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StaticIPAddressPool
This cmdlet returns a **StaticIPAddressPool** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

[New-SCStaticIPAddressPool](xref:VirtualMachineManager/v1/New-SCStaticIPAddressPool.md)

[Remove-SCStaticIPAddressPool](xref:VirtualMachineManager/v1/Remove-SCStaticIPAddressPool.md)

[Set-SCStaticIPAddressPool](xref:VirtualMachineManager/v1/Set-SCStaticIPAddressPool.md)

