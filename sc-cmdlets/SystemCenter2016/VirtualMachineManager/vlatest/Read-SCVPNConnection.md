---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B857B917-6CC8-4F66-8967-99CF3CF39E78
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVPNConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVPNConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVPNConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCVPNConnection

## SYNOPSIS
Refreshes a VPN connection.

## SYNTAX

### ByVPNConnection (Default)
```
Read-SCVPNConnection [-VMMServer <ServerConnection>] -VPNConnection <VPNConnection> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### ByID
```
Read-SCVPNConnection [-VMMServer <ServerConnection>] -ID <Guid> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCVPNConnection** cmdlet refreshes a virtual private network (VPN) connection.

## EXAMPLES

### Example 1: Refresh information about a VPN connection
```
PS C:\> $VmNetworkGateway = Get-SCVMNetworkGateway -Name "VMGateway01"
PS C:\> $VPNConnection = Get-SCVPNConnection -VMNetworkGateway $VmNetworkGateway -Name "VPN01"
PS C:\> Read-SCVPNConnection -VPNConnection $VPNConnection"
```

The first command gets a network gateway named VMGateway01, and then stores it in the $VmNetworkGateway variable.

The second command gets a VPN connection on the gateway in $VmNetworkGateway, and then stores it in the $VPNConnection variable.

The final command refreshes information about the VPN connection in $VPNConnection.

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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

To obtain a VPN connection object, use the **Get-SCVPNConnection** cmdlet.

```yaml
Type: VPNConnection
Parameter Sets: ByVPNConnection
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVPNConnection.md)

[Get-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVPNConnection.md)

[Remove-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVPNConnection.md)

[Set-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVPNConnection.md)

