---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 86F0ECB9-E786-4F22-A43A-77CDD7E2A25A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMDiscovery.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMDiscovery.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMDiscovery.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMDiscovery

## SYNOPSIS
Gets discovery information from Service Manager.

## SYNTAX

### Empty (Default)
```
Get-SCSMDiscovery [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromDiscoveryDisplayName
```
Get-SCSMDiscovery [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromDiscoveryId
```
Get-SCSMDiscovery [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCSMDiscovery [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromDiscoveryName
```
Get-SCSMDiscovery [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCSMDiscovery [-Target] <ManagementPackClass[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMDiscovery** cmdlet retrieves discovery information from Service Manager.

## EXAMPLES

### Example 1: Get Service Manager discoveries
```
PS C:\>Get-SCSMDiscovery
Enabled  Name                           Description
-------  ----                           -----------
true     ...DiscoverManagementGroupC... Discovers the relationship for the Management Group to contain the Gateway Management Server Watcher Group
true     ...OpsMgrDBWatcher.Discovery
true     ...PopulateRootManagementSe... Populates this group with the Root Management Server.
true     ...PopulateCollectionManage... Populates this group with all Collection Management Servers.
true     ...DiscoveryHealthServiceCo... Discovers the primary relationships and failover relationships for an agent that is configured for AD integration.
true     ...DiscoverManagementGroupC...
true     ...DiscoverWindowsClientCom... Discovers Windows client computers
true     ...DiscoverWindowsOSProperties Discovers properties on the Operating System class
true     ...PopulateAllComputersGroup   Populates the All Computers Group.
true     ...DiscoverIsVirtualMachine...
true     ...DiscoverManagementGroupC... Discovers the relationship for the Management Group to contain the Root Management Server.
true     ...DiscoverWindowsComputerP... Discovers properties on the Windows computer class
true     ...Agent.PatchDiscovery        This script runs on HealthService instances and finds a list of Operation Manager 2007 Patches that are current...
true     ...DiscoverWindowsProductType  Discovers what type of windows computer the System Center Management service is installed on
true     ...PopulateManagementServer... Populates this group with all Management Servers -- Root, Collection, Gateway.
true     ...DiscoverIsVirtualMachine...
true     ...AgentManagementServer.Di... Discovers the agents that run on as a management server for some management group.
true     InstanceGroup_dbbcf4ea8ff24...
true     WorkItemGroup.21169a7e4a784...
true     ...PopulateSCAgentlessManag... Populates this group with Managed Computer objects that are being monitored remotely.
true     ...SCManagedComputerPropert... Discovers properties on the System Center Managed Computer object.
true     ...PopulateGatewayManagemen... Populates this group with all Gateway Management Servers.
true     ...DiscoverManagementGroupC... Discovers the relationship for the Management Group to contain Collection Management Server Watcher Group
true     ...DiscoverLogicalProcessors
true     ...DiscoverWindowsServerDCC... Discovers Windows Server domain controllers
true     ...DiscoverADManagedComputer   Discovers and creates Agent Relationship Settings objects. This object is used in conjunction with Active Direc...
true     ...PopulateSCAgentManagedCo... Populates this group with Managed Computer objects that have a Health Service installed.
true     ...DiscoverHealthServicePro... Discovers the properties of a management service
true     ...DiscoverOpsMgrDBWatchers...
true     ...PopulateManagedComputerC... Discover the relationship for the grouping client Management Service Watchers.
true     ...DiscoverWindowsServerCom... Discovers Windows Server computers
true     ...DiscoverManagementGroupC... Discover the relationship for the Management Group to contain Agent Watcher Group
true     ...DiscoverManagementGroupC... (Deprecated)Discover the relationship for the Management Group to contain Health Service Watcher Group
```

This command retrieves the discoveries that are defined in Service Manager.

### Example 2: Get discoveries by name
```
PS C:\>Get-SCSMDiscovery -Name "*PopulateRootM*"
Enabled  Name                           Description
-------  ----                           -----------
true     ...PopulateRootManagementSe... Populates this group with the Root Management Server.
```

This command retrieves the discoveries where the name matchs the expression *PopulateRootM*.

### Example 3: Get discoveries by name and display them in a list
```
PS C:\>Get-SCSMDiscovery -Name "*PopulateRootM*" | Format-List
HasNonCategoryOverride          : False
Enabled                         : true
Target                          : ManagementPackElementUniqueIdentifier=0e7983be-95b9-aed8-ff93-8819e4cefcaa
ConfirmDelivery                 : False
Remotable                       : True
Priority                        : Normal
Category                        : Discovery
DataSource                      : DiscoveryDataSource
DiscoveryClassCollection        : {}
DiscoveryRelationshipCollection : {}
XmlTag                          : Discovery
ManagementGroup                 : psimp2
ManagementGroupId               : 048d4708-ede4-5aed-1317-81d1b0d0b395
Name                            : Microsoft.SystemCenter.PopulateRootManagementServerComputerGroup
Id                              : 21f2d4e2-6cde-b219-e392-0a25cbea12c6
DisplayName                     : Populate Root Management Server Computer Group
Description                     : Populates this group with the Root Management Server.
LanguageCode                    : ENU
Comment                         :
Status                          : Unchanged
LastModified                    : 12/2/2010 12:20:38 AM
TimeAdded                       : 12/2/2010 12:20:38 AM
```

This command retrieves the discoveries in which the name matches *PopulateRootM* and then displays the results formatted as a list.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost," or a dot (.).

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
Specifies a user account under which the management group connection runs.
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
Specifies the display name of the discovery object to be retrieved.

```yaml
Type: String[]
Parameter Sets: FromDiscoveryDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies the ID of the discovery object to be retrieved.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromDiscoveryId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies one or more management packs containing the discovery objects to retrieve.

You can enter a **ManagementPack** object that is returned by the **Get-SCManagementPack** cmdlet.

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
Specifies the name of a discovery object to retrieve.

```yaml
Type: String[]
Parameter Sets: FromDiscoveryName
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

### -Target
Specifies the management pack that contains the classes that are targeted by the discovery.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPack
You can pipe a management pack object to the *ManagementPack* parameter of the **Get-SCSMDiscovery** cmdlet.

### System.String
You can pipe a discovery name to the *Name* parameter of the **Get-SCSMDiscovery** cmdlet.

### System.Guid
You can pipe a GUID of a discovery object to the *Id* parameter of the **Get-SCSMDiscovery** cmdlet.

### Microsoft.EnterpriseManagement.Configuration.ManagementPackClass
You can pipe a management pack to the *Target* parameter of the **Get-SCSMDiscovery** cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackDiscovery
This cmdlets generates a discovery object.

## NOTES

## RELATED LINKS

