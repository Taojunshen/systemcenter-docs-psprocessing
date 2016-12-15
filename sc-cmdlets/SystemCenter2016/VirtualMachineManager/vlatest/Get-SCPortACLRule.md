---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPortACL.md
schema: 2.0.0
ms.assetid: 997D0535-8FD9-4ACD-8A78-2C359AC92C92
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPortACLRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPortACLRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPortACLRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCPortACLRule

## SYNOPSIS
Gets a port ACL rule.

## SYNTAX

### All (Default)
```
Get-SCPortACLRule [-VMMServer <ServerConnection>] [-Name <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ById
```
Get-SCPortACLRule [-VMMServer <ServerConnection>] [-Name <String>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByPortACL
```
Get-SCPortACLRule [-VMMServer <ServerConnection>] [-Name <String>] [-PortACL <PortACL>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPortACLRule** cmdlet gets a port access control list (ACL) rule in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Get a port ACL rule
```
PS C:\>Get-SCPortACLRule -Name "AllowRDPAccess"
```

The command gets the port ACL rule named AllowRDPAccess.

### Example 2: Get port ACL rules from an ACL
```
PS C:\>$PortACL = Get-SCPortACL -Name "RDP ACL"
PS C:\> Get-SCPortACLRule -PortACL $PortACL"
```

The first command gets the port ACL named RDP ACL, and then stores it in the $PortACL variable.

The second command gets all the rules under the port ACL in $PortACL.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the ACL rule.

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

### -PortACL
Specifies a port ACL object.

```yaml
Type: PortACL
Parameter Sets: ByPortACL
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-SCPortACL](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPortACL.md)

[New-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCPortACLRule.md)

[Remove-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPortACLRule.md)

[Set-SCPortACLRule](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPortACLRule.md)

