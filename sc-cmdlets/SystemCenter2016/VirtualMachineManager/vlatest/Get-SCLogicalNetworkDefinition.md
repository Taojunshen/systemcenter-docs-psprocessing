---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 03F90081-5147-4346-8C09-8CC384C18BD3
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetworkDefinition.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetworkDefinition.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetworkDefinition.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCLogicalNetworkDefinition

## SYNOPSIS
Gets a logical network definition.

## SYNTAX

### All (Default)
```
Get-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>] [-LogicalNetwork <LogicalNetwork>]
 [[-Name] <String>] [-Subnet <String>] [-VLanID <Int32>] [-ReturnAllTypes] [<CommonParameters>]
```

### ById
```
Get-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>] [-LogicalNetwork <LogicalNetwork>]
 [[-Name] <String>] [-Subnet <String>] [-VLanID <Int32>] -ID <Guid> [-ReturnAllTypes] [<CommonParameters>]
```

### ByHostGroup
```
Get-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>] [-LogicalNetwork <LogicalNetwork>]
 [[-Name] <String>] [-Subnet <String>] [-VLanID <Int32>] -VMHostGroup <HostGroup> [-ReturnAllTypes]
 [<CommonParameters>]
```

### ByCloud
```
Get-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>] [-LogicalNetwork <LogicalNetwork>]
 [[-Name] <String>] [-Subnet <String>] [-VLanID <Int32>] -Cloud <Cloud> [-ReturnAllTypes] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLogicalNetworkDefinition** cmdlet gets one or more logical network definitions.
A logical network definition (also called a network site) can be associated with one or more logical networks.

## EXAMPLES

### Example 1: Retrieve the logical network definition for a logical network
```
PS C:\> $LogicalNetwork = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup01" }
PS C:\> Get-SCLogicalNetworkDefinition -LogicalNetwork $LogicalNetwork -VMHostGroup $HostGroup
```

The first command gets the logical network named "LogicalNetwork01" and stores it in the $LogicalNetwork variable.

The second command gets the host group named "HostGroup01" and stores it in the $HostGroup variable.

The third command gets the logical network definition for the logical network stored in $LogicalNetwork and the host group stored in the $HostGroup variable (including its parent host group if inheritance is enabled).

## PARAMETERS

### -Cloud
Specifies a private cloud object.

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
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and virtual local area networks (VLANs) that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -ReturnAllTypes
Indicates that this cmdlet returns the logical network definitions of any isolation type.

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
Specifies an IP subnet (IPv4 or IPv6) in Classless Inter-Domain Routing (CIDR) notation.

Example format for an IPv4 subnet: 192.168.0.1/24

Example format for an IPv6 subnet: FD4A:29CD:184F:3A2C::/64

Note that an IP subnet cannot overlap with any other subnet in a host group or child host groups.

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

### -VLanID
Specifies a numerical identifier in the range 1-4094 for a virtual network adapter on a virtual machine or for a physical network adapter on a virtual machine host.

Configure a VLanID on a Hyper-V, VMware ESX, or Citrix XenServer host on an externally bound physical network adapter when the VLan mode is Access.

Configure a VLanID on a virtual network adapter of a virtual machine if it is either of the following: 

 -- Bound to a physical network adapter on the host. 
- Bound to an internal virtual network on the host.

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

### LogicalNetworkDefiniton
This cmdlet returns a **LogicalNetworkDefiniton** object.

## NOTES

## RELATED LINKS

[New-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetworkDefinition.md)

[Remove-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalNetworkDefinition.md)

[Set-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetworkDefinition.md)

[Set-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostNetworkAdapter.md)

