---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 577C0865-9A26-4672-8915-B8CE1FEC603D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCIPAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCIPAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCIPAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCIPAddress

## SYNOPSIS
Gets allocated static and virtual IP addresses.

## SYNTAX

### All (Default)
```
Get-SCIPAddress [-VMMServer <ServerConnection>] [-All] [-UnAssigned] [-Assigned] [-IsMulticast] [-Duplicate]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByPool
```
Get-SCIPAddress [-VMMServer <ServerConnection>] -StaticIPAddressPool <StaticIPAddressPool> [-UnAssigned]
 [-Assigned] [-IsMulticast] [-Duplicate] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### ByID
```
Get-SCIPAddress [-VMMServer <ServerConnection>] -ID <Guid> [-UnAssigned] [-Assigned] [-IsMulticast]
 [-Duplicate] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByAllocatedToObjectID
```
Get-SCIPAddress [-VMMServer <ServerConnection>] -GrantToObjectID <Guid> [-UnAssigned] [-Assigned]
 [-IsMulticast] [-Duplicate] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByIPAddress
```
Get-SCIPAddress [-VMMServer <ServerConnection>] -IPAddress <String> [-UnAssigned] [-Assigned] [-IsMulticast]
 [-Duplicate] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### PublicIPAddress
```
Get-SCIPAddress [-VMMServer <ServerConnection>] [-PublicIPAddress] [-UnAssigned] [-Assigned] [-IsMulticast]
 [-Duplicate] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCIPAddress** cmdlet gets allocated static IP and virtual IP addresses.

## EXAMPLES

### Example 1: Get all allocated IP addresses for a specific IP address pool
```
PS C:\> $IPAddressPool = Get-SCStaticIPAddressPool -IPv4 -Subnet "10.0.0.0/24"
PS C:\> Get-SCIPAddress -StaticIPAddressPool $IPAddressPool
```

The first command gets the IP address pool object with the subnet of 10.0.0.0/24 and stores it in the $IPAddressPool variable.

The second command returns all allocated IP addresses for the IP address pool stored in $IPAddressPool.

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
Indicates that this cmdlet gets IP addresses or MAC addresses that have been allocated from an address pool and assigned to a resource.

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

### -Duplicate
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

### -IPAddress
Specifies an IPv4 or IPv6 address.

```yaml
Type: String
Parameter Sets: ByIPAddress
Aliases: 

Required: True
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

### -PublicIPAddress


```yaml
Type: SwitchParameter
Parameter Sets: PublicIPAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticIPAddressPool
Specifies an IP address pool from which you can assign static IP addresses.

```yaml
Type: StaticIPAddressPool
Parameter Sets: ByPool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UnAssigned
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

### CloudDRPairingInfoData
This cmdlet returns a **CloudDRPairingInfoData** object.

## NOTES

## RELATED LINKS

[Grant-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCIPAddress.md)

[Revoke-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCIPAddress.md)

[Set-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCIPAddress.md)

