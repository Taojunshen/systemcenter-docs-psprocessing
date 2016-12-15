---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVPNConnection.md
schema: 2.0.0
ms.assetid: 788CB555-82D1-4928-931C-434BD9DA4780
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVPNConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVPNConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVPNConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVPNConnection

## SYNOPSIS
Gets a VPN connection.

## SYNTAX

### ByVMNetworkGateway (Default)
```
Get-SCVPNConnection [-VMMServer <ServerConnection>] -VMNetworkGateway <VMNetworkGateway> [-Name <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCVPNConnection [-VMMServer <ServerConnection>] -ID <Guid> [-Name <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVPNConnection** cmdlet gets a virtual private network (VPN) connection.

## EXAMPLES

### Example 1: Get VPN connections
```
PS C:\>$VmNetworkGateway = Get-SCVMNetworkGateway -Name "VMGateway01"
$VmNetworkGateway = Get-SCVMNetworkGateway -Name "VMGateway1"
PS C:\> $VPNConnection = Get-SCVPNConnection -VMNetworkGateway $VmNetworkGateway -Name "VPN01"
```

The first command gets a network gateway named VMGateway01, and then stores it in the $VmNetworkGateway variable.

The second command gets a VPN connection on the gateway in $VmNetworkGateway, and then stores it in the $VPNConnection variable.

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
Specifies the name of a VMM object.

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

[Add-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVPNConnection.md)

[Read-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVPNConnection.md)

[Remove-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVPNConnection.md)

[Set-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVPNConnection.md)

