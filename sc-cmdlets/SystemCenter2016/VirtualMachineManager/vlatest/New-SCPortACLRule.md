---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPortACLRule.md
schema: 2.0.0
ms.assetid: 6C60489D-4903-4F62-9F57-83326322B836
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPortACLRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPortACLRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCPortACLRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCPortACLRule

## SYNOPSIS
Creates a port ACL rule.

## SYNTAX

```
New-SCPortACLRule [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-PortACL <PortACL>]
 -Type <PortACLRuleDirection> -Action <PortACLRuleAction> [-LocalAddressPrefix <String>]
 [-LocalPortRange <String>] [-RemoteAddressPrefix <String>] [-RemotePortRange <String>]
 -Protocol <PortACLRuleProtocol> -Priority <UInt16> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCPortACLRule** cmdlet creates a port access control list (ACL) rule for Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Create a port ACL rule
```
PS C:\>$PortACL = New-SCPortACL -Name "RDP ACL" -Description "Acl on RDP access"
PS: C:\> New-SCPortACLRule -Name "AllowRDPAccess" -PortACL $PortACL -Description "Allow RDP Rule from a subnet" -Action Allow -Type Inbound -Priority 110 -Protocol Tcp -LocalPortRange 3389 -RemoteAddressPrefix 10.184.20.0/24
```

The first command creates a port ACL, and then stores it in the $PortACL variable.

The second command creates a port ACL rule to allow RDP access from a remote subnet.

## PARAMETERS

### -Action
Specifies a port ACL rule action.
The acceptable values for this parameter are:

- Allow
- Deny

```yaml
Type: PortACLRuleAction
Parameter Sets: (All)
Aliases: 
Accepted values: Allow, Deny

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the ACL rule.

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

### -LocalAddressPrefix
Specifies the local address prefix.

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

### -LocalPortRange
Specifies the local port range.

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

### -Name
Specifies the name of the port ACL rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -PortACL
Specifies a port ACL object.

```yaml
Type: PortACL
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Priority
Specifies the priority.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol.
The acceptable values for this parameter are:

- Tcp
- Udp
- Any

```yaml
Type: PortACLRuleProtocol
Parameter Sets: (All)
Aliases: 
Accepted values: Tcp, Udp, Any

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteAddressPrefix
Specifies the remote address prefix.

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

### -RemotePortRange
Specifies the remote port range.

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

### -Type
Specifies the type.
The acceptable values for this parameter are:

- Inbound
- Outbound

```yaml
Type: PortACLRuleDirection
Parameter Sets: (All)
Aliases: 
Accepted values: Inbound, Outbound

Required: True
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

## NOTES

## RELATED LINKS

[Get-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPortACLRule.md)

[Remove-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPortACLRule.md)

[Set-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPortACLRule.md)

