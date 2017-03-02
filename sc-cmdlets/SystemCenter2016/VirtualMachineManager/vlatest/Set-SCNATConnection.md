---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9F50421D-FD42-499A-904E-3EBE90316C2A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNATConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNATConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNATConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCNATConnection

## SYNOPSIS
Updates a NAT connection.

## SYNTAX

```
Set-SCNATConnection [-VMMServer <ServerConnection>] [-NATConnection] <NATConnection> [-Name <String>]
 [-Description <String>] [-Status <GatewayConnectionStatus>] [-MaximumBandwidthInboundKbps <UInt64>]
 [-MaximumBandwidthOutboundKbps <UInt64>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCNATConnection** cmdlet updates a network address translation (NAT) connection.

## EXAMPLES

### Example 1: Change the name and description for NAT connection of a virtual machine network
```
PS C:\> $VmNetwork = Get-SCVMNetwork -Name "NAT_VMNetwork"
PS C:\> $NatConnection = Get-SCNATConnection -VMNetwork $VmNetwork
PS C:\> Set-SCNATConnection -NATConnection $NatConnection -Name "NatConn_VMNAT1" -Description "NAT Connection for VM Network1"
```

The first command gets the virtual machine network by its name and stores it in the $VmNetwork variable.

The second command gets NAT connection for the virtual machine network and stores it in the $NatConnection variable.

The third command changes the NAT connection name to NatConn_VMNAT1 and its description to NAT Connection for VM Network1.

### Example 2: Change the status for NAT connection of a virtual machine network
```
PS C:\> $VmNetwork = Get-SCVMNetwork -Name "NAT_VMNetwork"
PS C:\> $NatConnection = Get-SCNATConnection -VMNetwork $VmNetwork
PS C:\> Set-SCNATConnection -NATConnection  $NatConnection -Status Disabled"
```

The first command gets the virtual machine network by its name and stores it in the $VmNetwork variable.

The second command gets NAT connection for the virtual machine network and stores it in the $NatConnection variable.

The third command changes the NAT connection status to Disabled.

## PARAMETERS

### -Description
Specifies a description for the NAT connection.

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

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -MaximumBandwidthInboundKbps
Specifies, in kbps, the maximum inbound bandwidth.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumBandwidthOutboundKbps
Specifies, in kbps, the maximum outbound bandwidth.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NATConnection
Specifies a NAT connection object.

```yaml
Type: NATConnection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Status
Specifies a gateway connection status.
The acceptable values for this parameter are:

- Error
- Enabled
- Disabled

```yaml
Type: GatewayConnectionStatus
Parameter Sets: (All)
Aliases: 
Accepted values: Error, Enabled, Disabled

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

## NOTES

## RELATED LINKS

[Add-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNATConnection.md)

[Get-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNATConnection.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Remove-SCNATConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNATConnection.md)

