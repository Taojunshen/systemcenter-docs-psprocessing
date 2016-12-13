---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVPNConnection.md
schema: 2.0.0
ms.assetid: 52CB99D3-2309-4E7B-B43E-86C93A8B02DE
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVPNConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVPNConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVPNConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVPNConnection

## SYNOPSIS
Removes a VPN connection from VMM.

## SYNTAX

```
Remove-SCVPNConnection [-VMMServer <ServerConnection>] [-VPNConnection] <VPNConnection> [-Force]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVPNConnection** cmdlet deletes a virtual private network (VPN) connection from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove a VPN connection
```
PS C:\>$VmNetworkGateway = Get-SCVMNetworkGateway -Name "VMGateway01"
PS C:\> $VPNConnection = Get-SCVPNConnection -VMNetworkGateway $VmNetworkGateway -Name "VPN01"
PS C:\> Remove-SCVPNConnection -VPNConnection $VPNConnection
```

The first command gets a network gateway named VMGateway01, and then stores it in the $VmNetworkGateway variable.

The second command gets a VPN connection on the gateway in $VmNetworkGateway, and then stores it in the $VPNConnection variable.

The final command removes the VPN connection in $VPNConnection.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

To obtain a VPN connection object, use the Get-SCVPNConnection cmdlet.

```yaml
Type: VPNConnection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCVPNConnection](xref:VirtualMachineManager/v1/Add-SCVPNConnection.md)

[Get-SCVPNConnection](xref:VirtualMachineManager/v1/Get-SCVPNConnection.md)

[Read-SCVPNConnection](xref:VirtualMachineManager/v1/Read-SCVPNConnection.md)

[Set-SCVPNConnection](xref:VirtualMachineManager/v1/Set-SCVPNConnection.md)

