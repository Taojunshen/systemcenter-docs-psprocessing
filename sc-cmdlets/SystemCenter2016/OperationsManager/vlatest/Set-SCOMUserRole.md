---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=239729
schema: 2.0.0
ms.assetid: 0AC16C5A-E83C-4A22-89DA-1F85B993C57B
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMUserRole

## SYNOPSIS
Configures an Operations Manager user role.

## SYNTAX

### FromUser
```
Set-SCOMUserRole [-UserRole] <UserRole> -User <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromAllClassScope
```
Set-SCOMUserRole [-UserRole] <UserRole> [-AllClass] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromClassScope
```
Set-SCOMUserRole [-UserRole] <UserRole> -ClassScope <ManagementPackClass[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromAllTaskScope
```
Set-SCOMUserRole [-UserRole] <UserRole> [-AllTask] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromTaskScope
```
Set-SCOMUserRole [-UserRole] <UserRole> -TaskScope <ManagementPackTask[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromAllGroupScope
```
Set-SCOMUserRole [-UserRole] <UserRole> [-AllGroup] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGroupcope
```
Set-SCOMUserRole [-UserRole] <UserRole> -GroupScope <MonitoringObjectGroup[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMUserRole** cmdlet configures a System Center 2016 - Operations Manager user role.
A user role contains two features: 

- Profile.
Defines the collection of operations to which the user role has access. 
- Scope.
Defines the boundaries for profile operations; for example, tasks and groups. 

You can use this cmdlet to update the user list or the scope of the user role.

## EXAMPLES

### Example 1: Grant a user role access to all tasks
```
PS C:\>$Role = Get-SCOMUserRole -Name "Constoso Operators"
PS C:\> $Role | Set-SCOMUserRole -AllTask -PassThru | Set-SCOMUserRole -AllGroup
```

This example shows how to update a user role to grant it access to all tasks.

The first command gets the user role object named Contoso Operators and stores the object in the $Role variable.

The second command uses the pipeline operator to pass the user role stored in the $Role variable to the **Set-SCOMUserRole** cmdlet.
This cmdlet grants the user role access to all tasks and returns the updated user role object.
The command then passes the updated object to **Set-SCOMUserRole** by using the pipeline operator, which approves the role for all groups.

### Example 2: Grant a user role access to specific tasks
```
PS C:\>$Role = Get-SCOMUserRole -Name "Constoso SQL Operators"
PS C:\> $NewTaskList = Get-SCOMTask -Name "*SQL*"
PS C:\> $Role | Set-SCOMUserRole -TaskScope $NewTaskList
```

This example shows how to update a user role to grant it access to specific tasks.

The first command gets the user role object named Contoso SQL Operators and stores the object in the $Role variable.

The second command gets all task objects with SQL in their names and stores the objects in the $NewTaskList variable.

The last command uses the pipeline operator to pass the user role stored in the $Role variable to **Set-SCOMUserRole**, which resets the collection of approved tasks to the list stored in the $NewTaskList variable.

### Example 3: Add a user a user role
```
PS C:\>$Role = Get-SCOMUserRole -Name "Contoso Read-Only Operators"
PS C:\> $Role | Set-SCOMUserRole -User ($Role.Users + "Contoso\Cesar")
```

This example adds a user to a user role.

The first command gets the user role object named Contoso Read-Only Operators and stores the object in the $Role variable.

The second command uses the pipeline operator to pass the object stored in the $Role variable to the **Set-SCOMUserRole** cmdlet, which adds the user Contoso\Cesar to the existing list of users for the role.

## PARAMETERS

### -AllClass
Indicates that the permissions that an Author user role grants extend to all classes.

```yaml
Type: SwitchParameter
Parameter Sets: FromAllClassScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllGroup
Indicates that the permissions that a user role grants extend to all groups.

```yaml
Type: SwitchParameter
Parameter Sets: FromAllGroupScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllTask
Indicates that the permissions that an Author, Operator, or Advanced Operator user role grants extend to all tasks.

```yaml
Type: SwitchParameter
Parameter Sets: FromAllTaskScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassScope
Specifies an array of **ManagementPackClass** objects that represent the classes to which an Author role has access.
To obtain a **ManagementPackClass** object, use the **Get-SCOMClass** cmdlet.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromClassScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupScope
Specifies an array of **MonitoringObjectGroup** objects that represent the groups to which a user role has access.
To obtain a monitoring object group object, use the **Get-MonitoringObjectGroup** cmdlet.

If you do not specify a value for this parameter, the role has access to all groups.
To deny the role access to all groups, specify $Null or an empty array, @().

```yaml
Type: MonitoringObjectGroup[]
Parameter Sets: FromGroupcope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

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

### -TaskScope
Specifies an array of **ManagementPackTask** objects that represent the tasks to which an Author, Operator, or Advanced Operator role has access.

If you do not specify a value for this parameter, the role has access to all tasks.
To deny the Author, Operator, or Advanced Operator role access to all tasks, specify $Null or an empty array, @().

```yaml
Type: ManagementPackTask[]
Parameter Sets: FromTaskScope
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies an array of user names that are part of this user role.
This list replaces any existing list of users.
To clear all users from a user role, specify $Null or an empty array, @().

```yaml
Type: String[]
Parameter Sets: FromUser
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object.
To obtain a **UserRole** object, us the **Get-SCOMUserRole** cmdlet.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

[Add-SCOMUserRole](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMUserRole.md)

[Get-SCOMUserRole](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMUserRole.md)

[Get-SCClass](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCClass.md)

