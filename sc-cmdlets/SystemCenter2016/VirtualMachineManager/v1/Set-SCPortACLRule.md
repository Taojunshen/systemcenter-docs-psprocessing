---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPortACLRule.md
schema: 2.0.0
ms.assetid: F938F0D8-A12B-4BB1-8EB7-3D24BE20FB71
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCPortACLRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCPortACLRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCPortACLRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCPortACLRule

## SYNOPSIS
Modifies a port ACL rule.

## SYNTAX

```
Set-SCPortACLRule [-VMMServer <ServerConnection>] [-PortACLRule] <PortACLRule> [-Name <String>]
 [[-Description] <String>] [-Type <PortACLRuleDirection>] [-Action <PortACLRuleAction>]
 [-LocalAddressPrefix <String>] [-LocalPortRange <String>] [-RemoteAddressPrefix <String>]
 [-RemotePortRange <String>] [-Protocol <PortACLRuleProtocol>] [-Priority <UInt16>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCPortACLRule** cmdlet modifies a port access control list (ACL) rule in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Modify the port ACL rule priority
```
PS C:\>$PortACLRule = Get-SCPortACLRule -Name "AllowRDPAccess"
PS: C:\> Set-SCPortACLRule -PortACLRule $PortACLRule -Priority 220"
```

The first command gets the port ACL rule named AllowRDPAccess, and then stores it in the $PortACLRule variable.

The second command changes the priority of the rule in $PortACLRule to 220.

### Example 2: Modify the port acl rule remote address range and protocol
```
PS C:\>$PortACLRule = Get-SCPortACLRule -Name "AllowRDPAccess"
PS: C:\> Set-SCPortACLRule -PortACLRule $portACLRule -RemoteAddressPrefix 172.185.21.0/24 -Protocol Udp
```

The first command gets the port ACL rule named AllowRDPAccess, and then stores it in the $PortACLRule variable.

The second command changes the protocol of the ACL rule in $PortACLRule to UDP and sets the remote address range to a different subnet.

## PARAMETERS

### -Action
Specifies a port ACL rule action object.

```yaml
Type: PortACLRuleAction
Parameter Sets: (All)
Aliases: 
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the port ACL rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### -PortACLRule
Specifies the port ACL rule to modify.

```yaml
Type: PortACLRule
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

Required: False
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

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCPortACLRule.md)

[New-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCPortACLRule.md)

[Remove-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCPortACLRule.md)

