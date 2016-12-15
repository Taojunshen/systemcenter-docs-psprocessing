---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCVMSubnet.md
schema: 2.0.0
ms.assetid: 36A227B2-F92D-47E9-82B6-65C4935BCDF5
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMSubnet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMSubnet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMSubnet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMSubnet

## SYNOPSIS
Gets a virtual machine subnet.

## SYNTAX

### All (Default)
```
Get-SCVMSubnet [-VMMServer <ServerConnection>] [[-Name] <String>] [-Subnet <String>] [-VMNetwork <VMNetwork>]
 [-Unassigned] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCVMSubnet [-VMMServer <ServerConnection>] -ID <Guid> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMSubnet** cmdlet gets a virtual machine subnet object.

## EXAMPLES

### Example 1: Get a virtual machine subnet by its name
```
PS C:\>$VMSubNet = Get-SCVMSubnet -Name "VMSubnet01"
```

This command gets the virtual machine subnet object named VMSubnet01 and stores the object in the $VMSubnet variable.

## PARAMETERS

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

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: All
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
Specifies an IP subnet (IPv4 or IPv6) in Classless Interdomain Routing (CIDR) notation. 



Example format for an IPv4 subnet: `192.168.0.1/24`

Example format for an IPv6 subnet: `FD4A:29CD:184F:3A2C::/64`

Note: An IP subnet cannot overlap with any other subnet in a host group or child host groups.

```yaml
Type: String
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unassigned
Retrieves IP addresses or MAC addresses that have been allocated from an address pool but not assigned to a resource.

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

### -VMNetwork
Specifies a virtual machine network object.

To get a virtual machine network object, use the Get-SCVMNetwork cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: All
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

[New-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMSubnet.md)

[Remove-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMSubnet.md)

[Set-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMSubnet.md)

