---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F812DAD4-216B-4462-8F8B-A3B9B74FF6EA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCMACAddress

## SYNOPSIS
Gets allocated MAC addresses.

## SYNTAX

### All (Default)
```
Get-SCMACAddress [-VMMServer <ServerConnection>] [-All] [-UnAssigned] [-Assigned] [<CommonParameters>]
```

### ByPool
```
Get-SCMACAddress [-VMMServer <ServerConnection>] -MACAddressPool <MACAddressPool> [-UnAssigned] [-Assigned]
 [<CommonParameters>]
```

### ByID
```
Get-SCMACAddress [-VMMServer <ServerConnection>] -ID <Guid> [-UnAssigned] [-Assigned] [<CommonParameters>]
```

### ByAllocatedToObjectID
```
Get-SCMACAddress [-VMMServer <ServerConnection>] -GrantToObjectID <Guid> [-UnAssigned] [-Assigned]
 [<CommonParameters>]
```

### ByMACAddress
```
Get-SCMACAddress [-VMMServer <ServerConnection>] -MACAddress <String> [-UnAssigned] [-Assigned]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCMACAddress cmdlet** gets allocated Media Access Control (MAC) addresses.

## EXAMPLES

### Example 1: Get the allocated MAC addresses for a specific MAC address pool
```
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> Set-SCVMHostGroup -VMHostGroup $HostGroup -InheritNetworkSettings $False
PS C:\> $MACAddressPool = @(Get-SCMACAddressPool -VMHostGroup $HostGroup)
PS C:\> Get-SCMACAddress -MACAddressPool $MACAddressPool[0]
```

The first command gets the host group object at the path "All Hosts\HostGroup02\Production" and stores the object in the $HostGroup variable.

The second command disables inheritance of network settings for the host group stored in $HostGroup.
This is done so that the next command returns only the MAC address pools associated with All Hosts\HostGroup02\Production, rather than all the MAC address pools inherited by this host group.

The third command gets the MAC address pool objects associated with the host group stored in $HostGroup and stores the objects in the $MACAddressPool array.

The last command gets the allocated MAC addresses for the first MAC address pool in $MACAddressPool.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Assigned
Indicates that this cmdlet retrieves IP addresses or MAC addresses that have been allocated from an address pool and assigned to a resource.

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

### -GrantToObjectID
Specifies the ID of an object to which an allocated IP address or MAC address is assigned.

```yaml
Type: Guid
Parameter Sets: ByAllocatedToObjectID
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
Parameter Sets: ByID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddress
Specifies the Media Access Control (MAC) address, or a set of MAC addresses, for a physical or virtual network adapter on a computer.

- Example format for a single MAC address: `-MACAddress "00-15-5D-B4-DC-00"`
- Example format for a set of MAC addresses: `-MACAddress "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`

```yaml
Type: String
Parameter Sets: ByMACAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MACAddressPool
Specifies a MAC address pool.

```yaml
Type: MACAddressPool
Parameter Sets: ByPool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnAssigned
Retrieves IP addresses or MAC addresses that have been allocated from an address pool but not assigned to a resource.

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

### CloudPairing[]
This cmdlet returns an array of **CloudPairing** objects.

## NOTES

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Grant-SCMACAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCMACAddress.md)

[Revoke-SCMACAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCMACAddress.md)

[Set-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md)

