---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225343
schema: 2.0.0
ms.assetid: 896D6C2C-3D38-4D0A-8B15-9F9CF5EBD9BB
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMUserRole

## SYNOPSIS
Retrieves user roles that are defined in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMUserRole [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMUserRole [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCSMUserRole [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMUserRole** cmdlet retrieves user role profiles that are defined in Service Manager.
You can then use this list to add users to one of the user role profiles.
Optionally, you can provide a regular expression to search for a specific user role profile.

## EXAMPLES

### Example 1: Get the user roles for the local computer
```
PS C:\>Get-SCSMUserRole
Name                          Description                   LastModified                  LastModifiedBy
----                          -----------                   ------------                  --------------
ChangeManagers                The Service Manager Change... 6/14/2010 5:14:16 AM
IncidentResolvers             The Service Manager Incide... 6/14/2010 5:14:16 AM
ActivityImplementers          The Service Manager Activi... 6/14/2010 5:14:15 AM
Workflows                     The Service Manager Workfl... 6/14/2010 5:14:16 AM
Administrators                The Service Manager Admini... 6/14/2010 5:14:16 AM
ProblemAnalysts               The Service Manager Proble... 6/14/2010 5:14:16 AM
AdvancedOperators             The Service Manager Advanc... 6/14/2010 5:14:16 AM
Authors                       The Service Manager Author... 6/14/2010 5:14:16 AM
ChangeInitiators              The Service Manager Change... 6/14/2010 5:14:16 AM
ReadOnlyOperators             The Service Manager Read-O... 6/14/2010 5:14:16 AM
EndUsers                      The Service Manager End Us... 6/14/2010 5:14:16 AM
```

This command retrieves the list of user roles from the local computer.

### Example 2: Get the Administrators role
```
PS C:\>Get-SCSMUserRole -Name "Administrators"
Name                          Description                   LastModified                  LastModifiedBy
----                          -----------                   ------------                  --------------
Administrators                The Service Manager Admini... 6/14/2010 5:14:16 AM
```

This command retrieves the Administrators user role.

### Example 3: Get the Administrators role for a specific computer
```
PS C:\>Get-SCSMUserRole -Name "Administrators" -ComputerName "WIN-752RWDX24M"
Name                          Description                   LastModified                  LastModifiedBy
----                          -----------                   ------------                  --------------
Administrators                The Service Manager Admini... 6/14/2010 5:14:16 AM
```

This command retrieves the Administrators user role from the Service Manager instance that is running on the computer that has the specified name.

### Example 4: Display the classes of a role
```
PS C:\>$Role = Get-SCSMUserRole -DisplayName "CustomRole"
PS C:\> $Role
DisplayName                   Description                    LastModified                  LastModifiedBy
-----------                   -----------                    ------------                  --------------
CustomRole                    Custom Description             8/6/2010 12:23:46 AM          WOODGROVE\Administrator PS C:\>$Role.Classes
Abstract Name                                                                DisplayName
-------- ----                                                                -----------
True     Microsoft.SystemCenter.ServiceDesigner.Messaging.Storage            Storage
True     Microsoft.SystemCenter.ServiceDesigner.ServiceComponentGroup        Distributed Application Component
False    Microsoft.SystemCenter.StorageDevicesGroup                          Storage Devices Group
True     Microsoft.SystemCenter.ServiceDesigner.WebApplication               Line of Business Web Application
True     Microsoft.SystemCenter.ConfigItemGroup                              All Groups
False    System.WorkItem.Incident                                            Incident
True     Microsoft.SystemCenter.ServiceDesigner.Messaging                    Messaging
True     Microsoft.SystemCenter.InstanceGroup                                All Instance Groups
True     Microsoft.SystemCenter.ServiceDesigner.WebApplication.WebSiteGroup  Web Application Web Sites
True     Microsoft.SystemCenter.ServiceDesigner.WebApplication.DatabaseGroup Web Application Databases
True     Microsoft.SystemCenter.ServiceDesigner.GenericService               Blank
True     Microsoft.SystemCenter.ServiceDesigner.Service                      User Created Distributed Application
False    Microsoft.SystemCenter.BusinessService                              Business Service
```

The first command gets the user role named CustomRole, and then stores it in the $Role variable.

The second command displays the contents of $Role.

The third command displays the classes of $Role.

## PARAMETERS

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

### -DisplayName
Specifies the display name of the user role to retrieve.
You can specify a regular expression.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the user role to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the user role to retrieve.
You can specify a regular expression.

```yaml
Type: String[]
Parameter Sets: FromName
Aliases: 

Required: True
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a name to the *DisplayName* parameter.

### System.Guid
You can pipe a GUID to the *Id* parameter.

## OUTPUTS

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.UserRoles.Role
The **UserRole** object provides the information about the Service Manager User Roles.
This object can be used in conjunction with the Update-SCSMUserRole cmdlet to add a user to a user role.

## NOTES

## RELATED LINKS

[New-SCSMUserRole](xref:SystemCenter2016/ServiceManager/v1.0/New-SCSMUserRole.md)

[Remove-SCSMUserRole](xref:SystemCenter2016/ServiceManager/v1.0/Remove-SCSMUserRole.md)

[Update-SCSMUserRole](xref:SystemCenter2016/ServiceManager/v1.0/Update-SCSMUserRole.md)

