---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8B0FABCB-1EDD-4FF9-8A70-B40730760E9A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCOMUserRole

## SYNOPSIS
Adds a user role to a management group.

## SYNTAX

### Operator (Default)
```
Add-SCOMUserRole [-Name] <String> [[-DisplayName] <String>] [[-Description] <String>] [[-Users] <String[]>]
 [-Operator] [-TaskScope <ManagementPackTask[]>] [-GroupScope <MonitoringObjectGroup[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ReadOnlyOperator
```
Add-SCOMUserRole [-Name] <String> [[-DisplayName] <String>] [[-Description] <String>] [[-Users] <String[]>]
 [-ReadOnlyOperator] [-GroupScope <MonitoringObjectGroup[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Author
```
Add-SCOMUserRole [-Name] <String> [[-DisplayName] <String>] [[-Description] <String>] [[-Users] <String[]>]
 [-Author] [-ClassScope <ManagementPackClass[]>] [-TaskScope <ManagementPackTask[]>]
 [-GroupScope <MonitoringObjectGroup[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AdvancedOperator
```
Add-SCOMUserRole [-Name] <String> [[-DisplayName] <String>] [[-Description] <String>] [[-Users] <String[]>]
 [-AdvancedOperator] [-TaskScope <ManagementPackTask[]>] [-GroupScope <MonitoringObjectGroup[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMUserRole** cmdlet adds a user role to a management group.
A user role consists of two features: 

- Profile.
Defines the collection of operations to which the user role has access. 
- Scope.
Defines the boundaries for profile operations; for example, tasks and groups.

## EXAMPLES

### Example 1: Add a new Read Only Operator user role
```
PS C:\>Add-SCOMUserRole -Name 'Script Role' -ReadOnlyOperator
```

This command adds a Read Only Operator user role named Script Role.

### Example 2: Add a new user role by specifying user names, tasks, and groups
```
PS C:\>$ApprovedTasks = Get-SCOMTask -Name '*SQL*'
PS C:\> $ApprovedGroups = Get-SCOMGroup -DisplayName '*SQL*'
PS C:\> Add-SCOMUserRole -Name 'SQL Operator' -Operator -GroupScope $ApprovedGroups -TaskScope $ApprovedTasks -User 'Contoso\Katarina','Contoso\Cesar'
```

This example adds a user role based on user names, tasks, and groups.

The first two commands get all task and group objects that have SQL in their names and store the objects in the $ApprovedTasks and $ApprovedGroups variables, respectively.

The last command creates an Operator user role named SQL Operator, which contains the users Katarina and Cesar.
The user role gives these two users access to the tasks and groups that are stored in $ApprovedTasks and $ApprovedGroups.

## PARAMETERS

### -AdvancedOperator
Indicates that the new role is an Advanced Operator.
This role grants members the ability to override the configuration of rules and monitors for specific targets or groups of targets within the configured scope.
The Advanced Operator role also grants all of the permissions that the Operator and Read-Only Operator profiles grant.

```yaml
Type: SwitchParameter
Parameter Sets: AdvancedOperator
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Author
Indicates that the new role is an Author.
This role grants members the ability to create, edit, and delete monitoring configuration that includes tasks, rules, monitors, and views, within the configured scope.
For convenience, an Author role can have permissions for specific groups.
The Author role also grants all of the permissions in the Advanced Operator, Operator, and Read-Only Operator roles.

```yaml
Type: SwitchParameter
Parameter Sets: Author
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClassScope
Specifies an array of **ManagementPackClass** objects that represent the classes to which an Author role has access.
To obtain a **ManagementPackClass** object, use the **Get-SCOMClass** cmdlet.

If you do not specify a value for this parameter, the role has access to all classes.
To deny the role access to all classes, specify $Null or an empty array, @().

```yaml
Type: ManagementPackClass[]
Parameter Sets: Author
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The computer must run the System Center Data Access service.

If you do not specify this parameter, the default is the computer for the current management group connection.

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

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the user role.
If you do not specify a value for this parameter, the cmdlet uses the value of the *DisplayName* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the user role.
If this parameter does not appear, the default is the value in the *Name* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupScope
Specifies an array of **MonitoringObjectGroup** objects that represent the groups to which a user role has access.
To obtain a monitoring object group object, use the **Get-MonitoringObjectGroup** cmdlet.

If you do not specify a value for this parameter, the role has access to all groups.
To deny the role access to all groups, specify $Null or an empty array, @()

```yaml
Type: MonitoringObjectGroup[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the user role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operator
Indicates that the new role is an Operator.
This role grants members the ability to interact with alerts, run tasks, and access views according to their configured scope.
The Operator role also grants all of the permissions that the Read-Only Operator profile grants.

```yaml
Type: SwitchParameter
Parameter Sets: Operator
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReadOnlyOperator
Indicates that the new role is a Read-Only Operator.
This role grants members the ability to view alerts and access views according to their configured scope.

```yaml
Type: SwitchParameter
Parameter Sets: ReadOnlyOperator
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter does not appear, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

```yaml
Type: Connection[]
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
To obtain a **ManagementPackTask** object, use the **ManagementPack.GetTask** cmdlet.
If this parameter does not appear, the role has access to all tasks.
To deny the Author, Operator, or Advanced Operator role access to all tasks, specify $Null or an empty array, @().

```yaml
Type: ManagementPackTask[]
Parameter Sets: Operator, Author, AdvancedOperator
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Users
Specifies an array that contains the names of users who are part of the user role.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-SCOMUserRole](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMUserRole.md)

[Set-SCOMUserRole](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMUserRole.md)

