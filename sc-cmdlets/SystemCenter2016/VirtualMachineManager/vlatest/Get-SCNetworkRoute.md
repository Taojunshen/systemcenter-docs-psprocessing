---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNetworkRoute.md
schema: 2.0.0
ms.assetid: 9AE0C3A8-0C4B-4F0B-BDBD-0E17E0E5040A
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkRoute.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkRoute.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkRoute.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNetworkRoute

## SYNOPSIS
Gets a network route.

## SYNTAX

### ByVMNetworkGateway (Default)
```
Get-SCNetworkRoute [-VMMServer <ServerConnection>] -Gateway <VMNetworkGateway> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByConnection
```
Get-SCNetworkRoute [-VMMServer <ServerConnection>] [-VPNConnection <VPNConnection>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCNetworkRoute [-VMMServer <ServerConnection>] -ID <Guid> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNetworkRoute** cmdlet gets a network route.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Gateway
Specifies a virtual machine network gateway object.

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

### -VPNConnection
Specifies a virtual private network (VPN) connection object.

To obtain a VPN connection object, use the Get-SCVPNConnection cmdlet.

```yaml
Type: VPNConnection
Parameter Sets: ByConnection
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

[Add-SCNetworkRoute](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNetworkRoute.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVPNConnection.md)

[New-SCNetworkRoute](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCNetworkRoute.md)

[Remove-SCNetworkRoute](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNetworkRoute.md)

