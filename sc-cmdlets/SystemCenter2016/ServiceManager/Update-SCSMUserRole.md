---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225389
schema: 2.0.0
ms.assetid: 339FC8DD-46D8-48B0-9341-2FA585AD1584
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Update-SCSMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Update-SCSMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Update-SCSMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCSMUserRole

## SYNOPSIS
Sets the UserRole property for a Service Manager user.

## SYNTAX

```
Update-SCSMUserRole [-UserRole] <Role[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMUserRole** cmdlet sets the **UserRole** property for a Service Manager user.

## EXAMPLES

### Example 1: Add a user to a user role
```
PS C:\>$Role = Get-SCSMUserRole -Name "IncidentResolvers"
PS C:\> $User = Get-SCSMUser -UserName "PattiFuller"
PS C:\> $Role.User += $User
PS C:\> Update-SCSMUserRole -Role $Role
```

The first command gets the user role named IncidentResolvers by using **Get-SCSMUserRole**, and then stores it in the $Role variable.

The second command gets a user by using the Get-SCSMUser cmdlet, and then stores that object in the $User variable.

The third command appends $User to the **User** property of $Role.

The final command updates the role to match the current value of $Role.

### Example 2: Remove a user from a role
```
PS C:\>Get-SCSMUserRole -Name "Administrators"
WOODGROVE\Administrator
WOODGROVE\Domain Admins


The second command assigns the user role previously displayed to the $Role variable. 
PS C:\>$Role = Get-SCSMUserRole -Name "Administrators"

The third command assigns the first user role to the **User** property of $Role. This command that property, removing all except the specified user. 
PS C:\>$Role.User = $Role.Users[0]

The final command updates the role to match the current value of $Role.
PS C:\>Update-SCSMUserRole -Role $Role
```

This example removes a user from a user role.
The first command displays administrators.

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

### -PassThru
Indicates that this cmdlet returns the user role that it updates.
You can pass this object to other cmdlets.

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

### -UserRole
Specifies the **UserRole** object to which to add the user.

```yaml
Type: Role[]
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.UserRoles.Role
You can pipe a **UserRole** object to the *UserRole* parameter.
To obtain a user role, use the Get-SCSMUserRole cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMUser](xref:SystemCenter2016/ServiceManager/Get-SCSMUser.md)

[Get-SCSMUserRole](xref:SystemCenter2016/ServiceManager/Get-SCSMUserRole.md)

[New-SCSMUserRole](xref:SystemCenter2016/ServiceManager/New-SCSMUserRole.md)

[Remove-SCSMUserRole](xref:SystemCenter2016/ServiceManager/Remove-SCSMUserRole.md)

