---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BC20863C-DFBA-435C-BB66-1F3749A25718
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStaticIPAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStaticIPAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStaticIPAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStaticIPAddressPool

## SYNOPSIS
Modifies a static IP address pool that is associated with one or more hostgroups.

## SYNTAX

```
Set-SCStaticIPAddressPool [-VMMServer <ServerConnection>] [-StaticIPAddressPool] <StaticIPAddressPool>
 [-Name <String>] [-Description <String>] [-DNSSearchSuffix <String[]>] [-DNSServer <String[]>]
 [-PxeServerAddress <String[]>] [-DNSSuffix <String>] [-IPAddressRangeStart <String>]
 [-IPAddressRangeEnd <String>] [-IPAddressReservedSet <String>] [-VIPAddressSet <String>]
 [-EnableNetBIOS <Boolean>] [-DefaultGateway <DefaultGateway[]>] [-NetworkRoute <SubnetNetworkRoute[]>]
 [-WINSServer <String[]>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStaticIPAddressPool** cmdlet modifies a Virtual Machine Manager (VMM) static IP address pool.
A static IP address pool can be associated with one or more logical network definitions.

## EXAMPLES

### Example 1: Add DNS Servers to a static IP address pool
```
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $IPPool = Get-SCStaticIPAddressPool -IPv4 -Subnet "10.0.0.0/24" -VMHostGroup $HostGroup -Name "Production IP Address Pool"
PS C:\> $DNSServerIPAddress = $IPPool.DNSServers
PS C:\> $DNSServerIPAddress += "10.0.0.1"
PS C:\> Set-SCStaticIPAddressPool -StaticIPAddressPool $IPPool -DNSServer $DNSServerIPAddress
```

The first command gets the host group that has the path All Hosts\HostGroup02\Production, and stores that group in the $HostGroup variable.

The second command gets the static address pool named Production IP Address Pool for the host group stored in $HostGroup, using the IPv4 address for the specified subnet.
The command stores the pool in the $IPPool variable.

The third command gets the DNS server for the IP address pool stored in $IPPool, and then the fourth command adds an address to the address array stored in the $DNSServerIPAddress variable.

The last command updates the IP address pool stored in $IPPool with the address array stored in $DNSServerIPAddress.

## PARAMETERS

### -DNSSearchSuffix
Specifies an array of strings that are appended to a host name to resolve a DNS address.

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

### -DNSServer
Specifies an array of IP addresses of DNS servers.
Valid formats are: IPv4 and IPv6 addresses.

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

### -DNSSuffix
Specifies the default DNS suffix associated with an adapter.

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

### -DefaultGateway
Specifies an array of default gateway objects.

```yaml
Type: DefaultGateway[]
Parameter Sets: (All)
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
Parameter Sets: (All)
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

### -Name
Specifies the name for the address pool.

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

### -NetworkRoute
Specifies an array of network routes.

```yaml
Type: SubnetNetworkRoute[]
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
Specifies an array of PXE Server IP addresses.

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

### -StaticIPAddressPool
Specifies the static IP address pool that this cmdlet modifies.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VIPAddressSet
Specifies a set of IP addresses in an IP subnet that is reserved for configuring virtual IPs (VIPs) in load balancers.

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

### -WINSServer
Specifies an array of IP addresses of Windows Internet Name Service (WINS) servers.
Valid formats are: IPv4 and IPv6 addresses.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StaticIPAddressPool
This cmdlet returns a **StaticIPAddressPool** object.

## NOTES

## RELATED LINKS

[Get-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStaticIPAddressPool.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[New-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStaticIPAddressPool.md)

[Remove-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStaticIPAddressPool.md)

