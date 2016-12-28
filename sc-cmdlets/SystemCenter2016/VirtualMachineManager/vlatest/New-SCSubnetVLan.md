---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BAF138DA-9EE3-46C9-9EDB-04AB9386AEA5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCSubnetVLan.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCSubnetVLan.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCSubnetVLan.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSubnetVLan

## SYNOPSIS
Creates a subnet VLAN object.

## SYNTAX

```
New-SCSubnetVLan [-VMMServer <ServerConnection>] [-VLanID <Int32>] [-Subnet <String>] [-SupportsDHCP <Boolean>]
 [-SecondaryVLanID <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSubnetVLan** cmdlet creates a subnet VLAN object.
You can use a subnet VLAN to create a logical network definition or VM subnet.

For information about how to create a logical network definition, type `Get-Help New-SCLogicalNetworkDefinition -Detailed`.

For information about how to create a VM subnet, type `Get-Help New-SCVMSubnet -Detailed`.

## EXAMPLES

### Example 1: Create a subnet VLAN
```
PS C:\> $SubnetVLAN = New-SCSubnetVLAN -Subnet "10.0.0.1/24" -VLanID 25
```

This command creates a subnet VLAN object with a subnet value of 10.0.0.1/24 and a VLAN value of 25.

## PARAMETERS

### -SecondaryVLanID
Specifies the secondary VLAN ID for a subnet VLAN.

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

### -Subnet
Specifies an IP subnet (IPv4 or IPv6) in Classless Inter-Domain Routing (CIDR) notation. 

- Example format for an IPv4 subnet: `192.168.0.1/24`
- Example format for an IPv6 subnet: `FD4A:29CD:184F:3A2C::/64`

Note: An IP subnet cannot overlap with any other subnet in a host group or child host groups.

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

### -SupportsDHCP
Indicates whether DHCP is supported by the subnet VLAN.

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

### -VLanID
Assigns a numerical identifier in the range 1-4094 to a virtual network adapter on a virtual machine or to a physical network adapter on a virtual machine host.

Configure a VLanID on a Hyper-V, VMware ESX, or Citrix XenServer host on an externally bound physical network adapter when the VLan mode is Access.

Configure a VLanID on a virtual network adapter of a virtual machine bound to a physical network adapter on the host, or bound to an internal virtual network on the host.

Example format: `-VLanEnabled -VLanMode "Access" -VLANID 35`

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

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### SubnetVLAN
This cmdlet returns a **SubnetVLAN** object.

## NOTES

## RELATED LINKS

[New-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetworkDefinition.md)

[New-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMSubnet.md)

