---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMTemplate.md
schema: 2.0.0
ms.assetid: BB63B90C-4AB3-4D4B-8280-46E1EDDE7A58
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Revoke-SCResource

## SYNOPSIS
Revokes access to a resource from a user or user role.

## SYNTAX

```
Revoke-SCResource [-VMMServer <ServerConnection>] -Resource <ClientObject> [-UserRoleName <String[]>]
 [-UserRoleID <Guid[]>] [-UserName <String>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-SCResource** cmdlet revokes access to a resource from a user or user role.

## EXAMPLES

### Example 1: Revoke access to a resource from a specific user
```
PS C:\>$Resource = Get-SCVMTemplate | where {$_.Name -eq "Template01"} 
PS C:\> Revoke-SCResource -Resource $Resource -Username "Contoso\Katarina"
```

The first command gets the template object named Template01 and stores the object in the $Resource variable.

The second command revokes access to the resource stored in $Resource (Template01) from the user named Katarina.
If the user is a member of multiple user roles, access will be revoked from the user in all of its user roles.

### Example 2: Revoke access to a resource from a user who is a member of multiple user roles
```
PS C:\>$Resource = Get-SCVMTemplate | where {$_.Name -eq "Template01"}
PS C:\> Revoke-SCResource -Resource $Resource -Username "Contoso\Katarina" -UserRoleName @("ContosoSelfServiceUsers", "SelfServiceUserRole02")
```

The first command gets the template object named Template01 and stores the object in the $Resource variable.

The second command revokes access to the resource stored in $Resource (Template01) from the user named Katarina, but only if the user is using the ContosoSelfServiceUsers or SelfServiceUserRole02 user roles.
If Katarina uses a different user role that has access to the resource then she will still be able to access the resource.

### Example 3: Revoke access to a resource from all members of a user role
```
PS C:\>$Resource = Get-SCVMTemplate | where {$_.Name -eq "Template01"}
PS C:\> Revoke-SCResource -Resource $Resource -UserRoleName "ContosoSelfServiceUsers"
```

The first command gets the template object named Template01 and stores the object in the $Resource variable.

The second command revokes access to the resource stored in $Resource (Template01) from all members of the ContosoSelfServiceUsers user role.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -Resource
Specifies a resource object.

```yaml
Type: ClientObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UserName
Specifies a the name of a user.
Enter a user name with the format Domain\User.

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

### -UserRoleID
Specifies the ID of a user role.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRoleName
Specifies the name of a user role.
Types of user roles that are named include Delegated Administrator, Read-Only Administrator, and Self-Service User.

```yaml
Type: String[]
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
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Resource
This cmdlet returns a **Resource** object.

## NOTES

## RELATED LINKS

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Grant-SCResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCResource.md)

