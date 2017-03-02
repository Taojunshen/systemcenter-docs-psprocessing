---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 574A8D14-B926-4215-BB39-4E9C3A1DFB8C
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCSMUserRole

## SYNOPSIS
Creates a user role in Service Manager.

## SYNTAX

```
New-SCSMUserRole [-UserRoleType] <UserRoleTypeEnum> -DisplayName <String> [-Description <String>]
 [-Class <ManagementPackClass[]>] [-Group <EnterpriseManagementObject[]>]
 [-CatalogGroup <EnterpriseManagementObject[]>] [-Queue <EnterpriseManagementObject[]>]
 [-Task <ManagementPackConsoleTask[]>] [-View <ManagementPackView[]>]
 [-FormTemplate <ManagementPackObjectTemplate[]>] [-User <String[]>] [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMUserRole** cmdlet creates a user role in Service Manager.

## EXAMPLES

### Example 1: Create a user role with all access
```
PS C:\>New-SCSMUserRole -UserRoleType ActivityImplementer -DisplayName "Role for implementers" -User "WOODGROVE\Domain Admins"
```

This command creates a user role which has access to all management packs, queues, groups, tasks, views, and templates.
The members of the user role are Domain Admins.

### Example 2: Create a read-only role for forms and views
```
PS C:\>New-SCSMUserRole -UserRoleType ReadOnlyOperator -DisplayName "restricted role" -Group @() -Queue @() -Task @() -User "WOODGROVE\Patti Fuller"
```

This command creates a read-only operator role which has access only to forms and views.
The only member in the new role is Patti Fuller.

## PARAMETERS

### -CatalogGroup
{{Fill CatalogGroup Description}}

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Class
Specifies the instances of management pack classes to which the user role has access.
This is only applicable to the Author role.

```yaml
Type: ManagementPackClass[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
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

### -Credential
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

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

### -DisplayName
Specifies the name of the user role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormTemplate
Specifies the form templates that are available to the users in this user role.
Forms that are not specified are not available to users in this role.
Specify None to make no templates available.
Specify All to make all templates available.

```yaml
Type: ManagementPackObjectTemplate[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies the groups that are available to members of this user role, to scope access to only specific groups of configuration items.
Configuration items in groups that are not specified are not available to members in this role.
Specify All to allow access to all groups.
If you do not specify any value, no groups are available.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the user role that it creates.
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

### -Queue
Specifies the queues that are available to members of this user role, to scope access to only specific queues of work items.
Work items in queues that are not specified are not available to members in this user role.
Specify All to allow access to all queues.
If you do not specify any value, no queues are available.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an object that represents a session to a Service Manager management server.

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

### -Task
Specifies a management pack console task.
Specify this parameter only if the **ManagementPack** property is not $Null.
The value All means that all elements are accessible, and the value None means that no elements are accessible.

```yaml
Type: ManagementPackConsoleTask[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies the an array users that are members of the user role.

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

### -UserRoleType
Specifies the type of user role to create.
Valid values are: 

- ActivityImplementers 
- Administrators 
- AdvancedOperators 
- Authors 
- ChangeInitiators 
- ChangeManagers 
- EndUsers 
- IncidentResolvers 
- ProblemAnalysts 
- ReadOnlyOperators 
- Workflows

```yaml
Type: UserRoleTypeEnum
Parameter Sets: (All)
Aliases: 
Accepted values: ActivityImplementer, AdvancedOperator, Author, ChangeInitiator, ChangeManager, EndUser, IncidentResolver, ProblemAnalyst, ReadOnlyOperator, ReleaseManager, ServiceRequestAnalyst

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -View
Specifies the views that are available to members of this user role, to scope access to only specific views.
Views that are not specified are not available to members in this role.
Specify All to allow access to all views.
If you do not specify any value, no views are available.

```yaml
Type: ManagementPackView[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMUserRole.md)

[Remove-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMUserRole.md)

[Update-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMUserRole.md)

