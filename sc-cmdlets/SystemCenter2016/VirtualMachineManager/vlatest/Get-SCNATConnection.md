---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 653F06B0-AF5E-4A2F-B33A-D51593CE5A66
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCNATConnection

## SYNOPSIS
Gets a NAT connection.

## SYNTAX

### ByVMNetworkGateway (Default)
```
Get-SCNATConnection [-VMMServer <ServerConnection>] -VMNetworkGateway <VMNetworkGateway> [-Name <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCNATConnection [-VMMServer <ServerConnection>] -ID <Guid> [-Name <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByVMNetwork
```
Get-SCNATConnection [-VMMServer <ServerConnection>] -VMNetwork <VMNetwork> [-Name <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNATConnection** cmdlet gets a network address translation (NAT) connection.

## EXAMPLES

### Example 1: Get the NAT connection for a virtual machine network
```
PS C:\> $VmNetwork = Get-SCVMNetwork -Name "NAT_VMNetwork"
PS C:\> $NatConnection = Get-SCNATConnection -VMNetwork $VmNetwork"
```

The first command gets the virtual machine network by its name, and then stores it in the $VmNetwork variable.

The second command gets NAT connection for the virtual machine network in $VmNetwork, and then stores it in the $NatConnection variable.

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

To get a virtual machine network object, use the **Get-SCVMNetwork** cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: ByVMNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkGateway
Specifies a virtual machine network gateway object.

To obtain a **VMNetworkGateway** object, use the **Get-SCVMNetworkGateway** cmdlet.

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

[Add-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNATConnection.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetwork.md)

[Get-SCVMNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetworkGateway.md)

[Remove-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNATConnection.md)

[Set-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNATConnection.md)

