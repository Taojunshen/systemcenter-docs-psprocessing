---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNATRule.md
schema: 2.0.0
ms.assetid: 825A1C70-F837-4362-9C50-03DC4665C04F
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNATRule

## SYNOPSIS
Gets a NAT rule.

## SYNTAX

### ByNATConnection (Default)
```
Get-SCNATRule [-VMMServer <ServerConnection>] -NATConnection <NATConnection> [-Name <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCNATRule [-VMMServer <ServerConnection>] -ID <Guid> [-Name <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByVMNetworkGateway
```
Get-SCNATRule [-VMMServer <ServerConnection>] -VMNetworkGateway <VMNetworkGateway> [-Name <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNATRule** cmdlet gets a network address translation (NAT) rule.

## EXAMPLES

### Example 1: Get NAT rule by name defined on a virtual machine network
```
PS C:\>$VmNetwork = Get-SCVMNetwork -Name "NAT_VMNetwork"
PS C:\> $NatConnection = Get-SCNATConnection -VMNetwork $VmNetwork
PS C:\> Get-SCNATRule -NATConnection $NatConnection -Name "NatRule"
```

The first command gets the virtual machine network by its name and stores it in the $VmNetwork variable.

The second command gets NAT connection for the virtual machine network and stores it in the $NatConnection variable.

The third command get NAT rule defined on a virtual machine network with the name NatRule.

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

### -NATConnection
Specifies a NAT connection object.

```yaml
Type: NATConnection
Parameter Sets: ByNATConnection
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a network object.

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

### -VMNetworkGateway
Specifies a virtual machine network gateway object.

To obtain a **VMNetworkGateway** object, use the Get-SCVMNetworkGateway cmdlet.

```yaml
Type: VMNetworkGateway
Parameter Sets: ByVMNetworkGateway
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

## NOTES

## RELATED LINKS

[Add-SCNATRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNATRule.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetwork.md)

[Get-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetworkGateway.md)

[Get-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATConnection.md)

[Remove-SCNATRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNATRule.md)

