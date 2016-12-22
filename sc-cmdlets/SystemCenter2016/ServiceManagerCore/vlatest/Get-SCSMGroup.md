---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9B3C5546-5BA7-4BC0-9372-1380C7D2992A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMGroup

## SYNOPSIS
Gets groups from Service Manager.

## SYNTAX

### Empty (Default)
```
Get-SCSMGroup [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromGroupDisplayName
```
Get-SCSMGroup [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromGroupGuid
```
Get-SCSMGroup [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMGroup** cmdlet retrieves groups from Service Manager.
The output of this cmdlet may be used by other cmdlets, such as the **New-SCSMUserRole** cmdlet.

## EXAMPLES

### Example 1: Get groups from Service Manager
```
PS C:\>Get-SCSMGroup
Id                                   FullName
--                                   --------
3c8ac4f3-475e-44dd-4163-8a97af363705 Microsoft.SystemCenter.AllComputersGroup
04bca169-5094-4b85-8704-067f333aa830 Microsoft.SystemCenter.CollectionManagementServerComputersGroup
95fe7deb-f466-ca83-aa8d-9845c386cd5a Microsoft.SystemCenter.GatewayManagementServerComputersGroup
099bfe0f-fddb-8d5a-67af-a79317eb6e91 Microsoft.SystemCenter.ManagementServerComputersGroup
0e7983be-95b9-aed8-ff93-8819e4cefcaa Microsoft.SystemCenter.RootManagementServerComputersGroup
3c1ef0a3-b773-11c8-b150-c4e47e5b7d91 Microsoft.SystemCenter.AgentlessManagedComputerGroup
e394c529-dfca-bdb4-5a86-d46078622200 Microsoft.SystemCenter.AgentManagedComputerGroup
e929bd61-1615-ba70-62b2-9fd5eee8aa09 Microsoft.SystemCenter.ManagedComputerClientHealthServiceWatcherGroup
93cb6af4-3e3d-53f6-06a7-04a469197a9c Microsoft.SystemCenter.OpsMgrDBWatchersGroup
a528b843-301e-4e61-6679-104243bbdb6b InstanceGroup_dbbcf4ea8ff241839b6154026698ceb2
```

This command retrieves groups from Service Manager.

### Example 2: Get groups and display their details in a table
```
PS C:\>Get-SCSMGroup |Format-Table fullname,displayname
FullName                                                                      DisplayName
--------                                                                      -----------
Microsoft.SystemCenter.AllComputersGroup                                      All Windows Computers
Microsoft.SystemCenter.CollectionManagementServerComputersGroup               Collection Management Server Computer Group
Microsoft.SystemCenter.GatewayManagementServerComputersGroup                  Gateway Management Server Computer Group
Microsoft.SystemCenter.ManagementServerComputersGroup                         Management Server Computer Group
Microsoft.SystemCenter.RootManagementServerComputersGroup                     Root Management Server Computer Group
Microsoft.SystemCenter.AgentlessManagedComputerGroup                          Agentless Managed Computer Group
Microsoft.SystemCenter.AgentManagedComputerGroup                              Agent Managed Computer Group
Microsoft.SystemCenter.ManagedComputerClientHealthServiceWatcherGroup         Managed Computer Client Management Service Watcher Group
Microsoft.SystemCenter.OpsMgrDBWatchersGroup                                  System Center Operations Manager Operational Database Watcher Group
InstanceGroup_dbbcf4ea8ff241839b6154026698ceb2                                mygroup
```

This command retrieves groups and then displays their **FullName** and **DisplayName** properties.

### Example 3: Get the details of a group
```
PS C:\>Get-SCSMGroup -DisplayName "All Windows Computers"
Id                                   FullName
--                                   --------
3c8ac4f3-475e-44dd-4163-8a97af363705 Microsoft.SystemCenter.AllComputersGroup
```

This command retrieves the All Windows Computers group.

### Example 4: Get a group and display its properties
```
PS C:\>Get-SCSMGroup -DisplayName "All Windows Computers"|Format-List
Name                                         :
Path                                         :
DisplayName                                  : All Windows Computers
FullName                                     : Microsoft.SystemCenter.AllComputersGroup
ManagementPackClassIds                       : {3c8ac4f3-475e-44dd-4163-8a97af363705}
LeastDerivedNonAbstractManagementPackClassId : 3c8ac4f3-475e-44dd-4163-8a97af363705
TimeAdded                                    : 12/2/2010 12:19:56 AM
LastModifiedBy                               :
Values                                       : {System.ConfigItem.ObjectStatusEnum.Active, (null), (null), All Windows Computers}
LastModified                                 : 12/2/2010 12:19:56 AM
IsNew                                        : False
HasChanges                                   : False
Id                                           : 3c8ac4f3-475e-44dd-4163-8a97af363705
ManagementGroup                              : psimp2
ManagementGroupId                            : 048d4708-ede4-5aed-1317-81d1b0d0b395
```

This command retrieves the All Windows Computers group and then displays all of its properties.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

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
Specifies a user account under which the management group connection will run.
The account must have access to the server that is specified in the *ComputerName* parameter, if the server is specified.
The default value is the current user.

You can enter a **PSCredential** object that is returned by the **Get-Credential** cmdlet.

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
Specifies the display name of the groups to retrieve.

```yaml
Type: String[]
Parameter Sets: FromGroupDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Id
Specifies the ID of the groups to retrieve.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromGroupGuid
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the **Get-SCManagementGroupConnection** cmdlet.

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

### System.Guid
You can pipe a group GUID to the *Id* parameter of the **Get-SCSMGroup** cmdlet.

### System.String
You can pipe a name of a group to the *DisplayName* parameter of the **Get-SCSMGroup** cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Common.EnterpriseManagementObject
The output of this cmdlets is a group object.

## NOTES

## RELATED LINKS

