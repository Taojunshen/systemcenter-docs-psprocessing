---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7689EE1C-8424-459F-BC05-47CD635B5F0D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCUserRole

## SYNOPSIS
Creates a user role for a group of VMM users.

## SYNTAX

```
New-SCUserRole [-VMMServer <ServerConnection>] [-Name] <String> -UserRoleProfile <Profile> [-ID <Guid>]
 [-JobGroup <Guid>] [-Description <String>] [-ParentUserRole <UserRole>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCUserRole** cmdlet creates a user role for a group of Virtual Machine Manager (VMM) users.
You can create the following user roles: Delegated Administrator, Read-Only Administrator, and Self-Service User.
Only one Administrator role exists.
You cannot create another Administrator role or delete the existing one.

If you are a member of a Delegated Administrator user role, you can create a user role.
However, the scope of the new user role must be a subset of the scope of its parent user role.

After you create a user role, you can use the **Set-SCUserRole** cmdlet to rename the user role, to add or remove members, and to add or modify the scope of objects that members of the role can manage.
For a Self-Service user role, you can specify which actions members of a Self-Service user role can take on their virtual machines, and you can define a quota that limits the number of virtual machines self-service users can create.
Although you cannot create or remove the Administrator role or limit its scope, you can use **Set-SCUserRole** to add or remove members to that role.

For information about how to modify the properties of a user role, type `Get-Help Set-SCUserRole`.

## EXAMPLES

### Example 1: Create a Delegated Administrator user role
```
PS C:\> New-SCUserRole -Name "ContosoDelegatedAdmin" -Description "Delegated Administrators for the Contoso.com domain" -UserRoleProfile "DelegatedAdmin"
```

This command creates a delegated administrator user role named ContosoDelegatedAdmin, provides the description Delegated Administrators for the Contoso.com domain, and uses the *UserRoleProfile* parameter to designate the user role type as Delegated Administrator.

### Example 2: Create a Self Service user role
```
PS C:\> $SelfServiceRole = New-SCUserRole -Name "ContosoSelfServiceUsers" -UserRoleProfile "SelfServiceUser"
```

This command creates a new user role named ContosoSelfServiceUsers, uses the *UserRoleProfile* parameter to designate the new user role type as Self-Service user, and stores the new user role object in the $SelfServiceRole variable.

## PARAMETERS

### -Description
Specifies a description for the user role.

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

### -ID
Specifies the unique ID for the new user role.

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

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

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

### -Name
Specifies a name for the new user role.

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
This parameter lets you audit of PRO tips.

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

### -ParentUserRole
Specifies an existing VMM user role as the parent of the new user role.

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

### -UserRoleProfile
Specifies the type of profile that is the basis for the new user role.
The acceptable values for this parameter are:

- DelegatedAdmin
- ReadOnlyAdmin
- SelfServiceUser

```yaml
Type: Profile
Parameter Sets: (All)
Aliases: 
Accepted values: Administrator, DelegatedAdmin, TenantAdmin, SelfServiceUser, ReadOnlyAdmin

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies the VMM server on which this cmdlet creates a user role.

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

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Remove-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUserRole.md)

[Set-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRole.md)

