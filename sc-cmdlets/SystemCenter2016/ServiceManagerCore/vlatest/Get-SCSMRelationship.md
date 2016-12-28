---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7D223F99-0592-4551-A671-BA9985CF362E
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRelationship.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRelationship.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRelationship.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMRelationship

## SYNOPSIS
Gets information about relationship objects from Service Manager.

## SYNTAX

### Empty (Default)
```
Get-SCSMRelationship [[-Source] <ManagementPackClass[]>] [[-Target] <ManagementPackClass[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipDisplayName
```
Get-SCSMRelationship [-DisplayName] <String[]> [[-Source] <ManagementPackClass[]>]
 [[-Target] <ManagementPackClass[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipId
```
Get-SCSMRelationship [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCSMRelationship [-ManagementPack] <ManagementPack[]> [[-Source] <ManagementPackClass[]>]
 [[-Target] <ManagementPackClass[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipName
```
Get-SCSMRelationship [-Name] <String[]> [[-Source] <ManagementPackClass[]>] [[-Target] <ManagementPackClass[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMRelationship** cmdlet retrieves information about relationship objects from Service Manager.

## EXAMPLES

### Example 1: Get information about relationship objects
```
PS C:\>Get-SCSMRelationship | Select-Object -first 3
DisplayName : Primary User
Source      : System.Computer
Target      : System.User

DisplayName : Contains Configuration Item
Source      : System.ConfigItem
Target      : System.ConfigItem

DisplayName : Affects Customers
Source      : System.ConfigItem
Target      : System.User
```

This command retrieves information about three relationship objects.

### Example 2: Get relationships that target configuration items
```
PS C:\>$x = Get-SCSMClass -name "system.configitem"
PS C:\>Get-SCSMRelationship â€"Target $x
DisplayName : Contains Configuration Item

Source      : System.ConfigItem

Target      : System.ConfigItem

DisplayName : Is Related to Configuration Item

Source      : System.ConfigItem

Target      : System.ConfigItem


DisplayName : About Configuration Item

Source      : System.WorkItem

Target      : System.ConfigItem


DisplayName : Is Related to Configuration Item

Source      : System.WorkItem

Target      : System.ConfigItem


DisplayName : Collection has configuration item

Source      : Microsoft.SystemCenter.ConfigurationManager.CollectionInfo

Target      : System.ConfigItem
```

Thse commands retrieve relationships that target configuration items.

### Example 3: Get relationships that target configuration items and their derived types
```
PS C:\>$x = Get-SCClass -name "system.configitem"
PS C:\>$y = @($x; $x.GetDerivedTypes())
PS C:\>Get-SCSMRelationship â€"Target $y
DisplayName : Contains Configuration Item

Source      : System.ConfigItem

Target      : System.ConfigItem


DisplayName : Is Related to Configuration Item

Source      : System.ConfigItem

Target      : System.ConfigItem


DisplayName : About Configuration Item

Source      : System.WorkItem

Target      : System.ConfigItem


DisplayName : Is Related to Configuration Item

Source      : System.WorkItem

Target      : System.ConfigItem


DisplayName : Collection has configuration item

Source      : Microsoft.SystemCenter.ConfigurationManager.CollectionInfo

Target      : System.ConfigItem


DisplayName : Is Related to Software Item

Source      : Microsoft.SystemCenter.ConfigurationManager.DCM_CI

Target      : Microsoft.SystemCenter.ConfigurationManager.DCM_CI


DisplayName : Contains program

Source      : Microsoft.SystemCenter.ConfigurationManager.Package

Target      : Microsoft.SystemCenter.ConfigurationManager.ProgramV5


DisplayName : Hosts program

Source      : Microsoft.SystemCenter.ConfigurationManager.Package

Target      : Microsoft.SystemCenter.ConfigurationManager.Program


DisplayName : Contains Physical Hardware

Source      : Microsoft.SystemCenter.ServiceDesigner.Messaging.Storage

Target      : System.PhysicalEntity


DisplayName : Links To Knowledge Document

Source      : System.Entity

Target      : System.Knowledge.Article


DisplayName : 

Source      : Microsoft.EnterpriseManagement.LinkingFramework.OpsMgrConnector

Target      : Microsoft.EnterpriseManagement.LinkingFramework.OpsMgrConnector.Config


DisplayName : Is Related to Baseline Configuration Item

Source      : Microsoft.SystemCenter.WorkItem.DCMIncident

Target      : Microsoft.SystemCenter.ConfigurationManager.DCM_CI


DisplayName : Is Related to Configuration Item

Source      : Microsoft.SystemCenter.WorkItem.DCMIncident

Target      : Microsoft.SystemCenter.ConfigurationManager.DCM_CI


DisplayName : Assigned Program

Source      : Microsoft.SystemCenter.ConfigurationManager.Package

Target      : Microsoft.SystemCenter.ConfigurationManager.Program
```

These commands retrieve relationships that target configuration items and any types that are derived from these configuration items.

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
Default value: Current user context
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the relationship object to retrieve.

```yaml
Type: String[]
Parameter Sets: FromRelationshipDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies the ID of the relationship object to retrieve.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromRelationshipId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies one or more management packs containing the relationships to retrieve.

You can enter a **ManagementPack** object that is returned by the Get-SCManagementPack cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the relationship object to retrieve.

```yaml
Type: String[]
Parameter Sets: FromRelationshipName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the Get-SCManagementGroupConnection cmdlet.

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

### -Source
Specifies the classes that represent the source of the relationship.
If more than one class is specified, any relationship that has one of those classes as a source is returned.
The source class of the relationship must be an exact match of the specified class type.

If you specify classes for both the *Target* and the *Source* parameters, the cmdlet returns all relationships in which the target class is one of the specified target classes and the source class is one of the specified source classes.

```yaml
Type: ManagementPackClass[]
Parameter Sets: Empty, FromRelationshipDisplayName, FromManagementPack, FromRelationshipName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Target
Specifies the classes that represent the target of the relationship.
If more than one class is specified, any relationship that has one of those classes as a target is returned.
The target class of the relationship must be an exact match of the specified class type.

If you specify classes for both the *Target* and the *Source* parameters, the cmdlet returns all relationships in which the target class is one of the specified target classes and the source class is one of the specified source classes.

```yaml
Type: ManagementPackClass[]
Parameter Sets: Empty, FromRelationshipDisplayName, FromManagementPack, FromRelationshipName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackClass
You can pipe a source class to the *Source* parameter of the **Get-SCSMRelationship** cmdlet.

### Microsoft.EnterpriseManagement.Configuration.ManagementPackClass
You can pipe a target class to the *Target* parameter of the **Get-SCSMRelationship** cmdlet.

### System.Guid
You can pipe a GUID to the *Id* parameter of the **Get-SCSMRelationship** cmdlet.

### Microsoft.EnterpriseManagement.Configuration.ManagementPack
You can pipe a management pack to the *ManagementPack* parameter of the **Get-SCSMRelationship** cmdlet.

### System.String
You can pipe a name to the *Name* parameter of the **Get-SCSMRelationship** cmdlet.

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Service Manager Administrator Cmdlets Group 1](xref:SystemCenter2016/ServiceManagerCore/vlatest/ServiceManagerCore.md)

