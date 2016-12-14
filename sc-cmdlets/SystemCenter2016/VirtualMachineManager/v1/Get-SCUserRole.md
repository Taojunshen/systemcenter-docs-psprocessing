---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Grant-SCResource.md
schema: 2.0.0
ms.assetid: 90D76175-B3B6-4797-B706-025E9E81965D
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCUserRole

## SYNOPSIS
Gets a VMM user role.

## SYNTAX

```
Get-SCUserRole [-VMMServer <ServerConnection>] [[-Name] <String>] [-UserRoleProfile <Profile>] [-ID <Guid>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCUserRole** cmdlet gets one or more Virtual Machine Manager (VMM) user roles.
VMM uses role-based security to define the boundaries within which members of a given user role can operate and the set of allowed operations members of a user role can perform.

For information about creating user roles, type `Get-Help New-SCUserRole`.

For information about setting the properties of a user role, including the scope for delegated and read-only administrators and the scope and actions for self-service users, type `Get-Help Set-SCUserRole`.

## EXAMPLES

### Example 1: Get all user roles
```
PS C:\>Get-SCUserRole -VMMServer "VMMServer01.Contoso.com"
```

This command gets all VMM user roles on the server named VMMServer01.Contoso.com.
The command displays information about each user role.

### Example 2: Get a user role by name
```
PS C:\>Get-SCUserRole -Name "Administrator"
```

This command gets the user role object named Administrator.
The command displays information about that user role.

### Example 3: Get a user role by profile
```
PS C:\>Get-SCUserRole -VMMServer "VMMServer01.Contoso.com" -UserRoleProfile "SelfServiceUser"
```

This command gets the user roles the server named VMMServer01 that have a user role profile of SelfServiceUser.
The command displays information about these user roles.

### Example 4: Display properties and other information about user role objects
```
PS C:\>$UserRoles = Get-SCUserRole -VMMServer "VMMServer01.Contoso.com"
PS C:\> $UserRoles | Select-Object -Property Name, UserRoleProfile, ParentUserRole, Cloud
PS C:\> $UserRoles | Get-Member
```

The first command gets all user role objects on the server named VMMServer01, and then stores those objects in the $UserRoles variable.

The second command passes each user role object in $UserRoles to the Select-Object cmdlet, which then displays the name, user role profile, parent user role, and cloud for each user role

The final command passes each user role in $UserRoles to the Get-Member cmdlet, which displays the .NET type for each user role and the methods and properties associated with each user role type.

## PARAMETERS

### -ID
Specifies the unique ID for the user role that this cmdlet gets.

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

### -Name
Specifies the name of the VMM user role that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### -UserRoleProfile
Specifies the type of profile that is the basis for the user roles that this cmdlet gets.
The acceptable values for this parameter are:

- DelegatedAdmin
- ReadOnlyAdmin
- SelfServiceUser

```yaml
Type: Profile
Parameter Sets: (All)
Aliases: 
Accepted values: Administrator, DelegatedAdmin, TenantAdmin, SelfServiceUser, ReadOnlyAdmin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies the VMM server on which this cmdlet gets user roles.

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

### UserRole
This cmdlet returns a **UserRole** object.

## NOTES

## RELATED LINKS

[Grant-SCResource](xref:SystemCenter2016/VirtualMachineManager/v1/Grant-SCResource.md)

[New-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCUserRole.md)

[Remove-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCUserRole.md)

[Revoke-SCResource](xref:SystemCenter2016/VirtualMachineManager/v1/Revoke-SCResource.md)

[Set-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCUserRole.md)

