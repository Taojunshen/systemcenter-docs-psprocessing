---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 36FD0973-4B7F-41FA-ADC0-D8774C661E3B
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRelationshipInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRelationshipInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRelationshipInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMRelationshipInstance

## SYNOPSIS
Gets the relationship instances from Service Manager.

## SYNTAX

### Empty (Default)
```
Get-SCSMRelationshipInstance [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromRelationshipInstanceId
```
Get-SCSMRelationshipInstance [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipInstanceSourceTarget
```
Get-SCSMRelationshipInstance [[-SourceInstance] <EnterpriseManagementObject[]>]
 [[-TargetInstance] <EnterpriseManagementObject[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMRelationshipInstance** cmdlet retrieves the instances of relationships from Service Manager.
These relationships describe the relationship of one **ClassInstance** to another **ClassInstance**.

## EXAMPLES

### Example 1: Get all relationship instances for a class
```
PS C:\>$HealthService = Get-SCClassInstance -Class (Get-SCClass -name "Microsoft.SystemCenter.HealthService") 
PS C:\>Get-SCSMRelationshipInstance -SourceInstance $HealthService -TargetInstance $HealthService | Format-Table SourceObject,TargetObject -au
SourceObject                  TargetObject
------------                  ------------
WIN-752HJBSX24M.woodgrove.com Software Deployment Workflow Target (internal)
WIN-752HJBSX24M.woodgrove.com Activity Event Workflow Configuration
WIN-752HJBSX24M.woodgrove.com System Center Operations Manager Synchronization Workflow (internal)
WIN-752HJBSX24M.woodgrove.com Grooming Workflow Target (internal)
WIN-752HJBSX24M.woodgrove.com SQL Job Workflow Target
WIN-752HJBSX24M.woodgrove.com Microsoft.ServiceManager.InternalDiscoveryCollectorTarget
WIN-752HJBSX24M.woodgrove.com Release Record Event Workflow Configuration
WIN-752HJBSX24M.woodgrove.com Change Request Event Workflow Configuration
WIN-752HJBSX24M.woodgrove.com Microsoft.EnterpriseManagement.LinkingFramework.OpsMgrConnector.SyncTaskWorkflowTarget
WIN-752HJBSX24M.woodgrove.com Subscription Workflow Target
WIN-752HJBSX24M.woodgrove.com Deployment Workflow Target
WIN-752HJBSX24M.woodgrove.com Change Request Workflow Target
WIN-752HJBSX24M.woodgrove.com Problem Workflow Target
WIN-752HJBSX24M.woodgrove.com mygroup
WIN-752HJBSX24M.woodgrove.com Linking Framework Connector Workflow Target (internal)
WIN-752HJBSX24M.woodgrove.com Microsoft.SystemCenter.MonitoringHostKeepAlive.Workflows.WorkflowTarget
WIN-752HJBSX24M.woodgrove.com Release Record Workflow Target
WIN-752HJBSX24M.woodgrove.com Authoring Workflow Target
WIN-752HJBSX24M.woodgrove.com Incident Event Workflow Configuration
WIN-752HJBSX24M.woodgrove.com Microsoft.SystemCenter.WorkflowFoundation.WorkflowTarget
WIN-752HJBSX24M.woodgrove.com WIN-752HJBSX24M.woodgrove.com
WIN-752HJBSX24M.woodgrove.com Microsoft.ServiceManager.InternalDiscoverySourceTarget
WIN-752HJBSX24M.woodgrove.com Subscriptions Workflow Target
WIN-752HJBSX24M.woodgrove.com Activity Workflow Target
WIN-752HJBSX24M.woodgrove.com WIN-752HJBSX24M.woodgrove.com
WIN-752HJBSX24M.woodgrove.com Desired Configuration Management Event Workflow Configuration
WIN-752HJBSX24M.woodgrove.com Grooming Workflow Target
WIN-752HJBSX24M.woodgrove.com Inbound E-mail Configuration Target (internal)
WIN-752HJBSX24M.woodgrove.com queue1
WIN-752HJBSX24M.woodgrove.com Workflow Target (internal)
```

These commands retrieve all relationship instances for which the source instance and the target instance is the **HealthService** class.

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

### -Id
Specifies the ID of the relationship object to retrieve.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromRelationshipInstanceId
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

### -SourceInstance
Specifies the instances that represent the source class of the relationships to be retrieved.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromRelationshipInstanceSourceTarget
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetInstance
Specifies the instances that represent the target class of the relationships to be retrieved.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromRelationshipInstanceSourceTarget
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid
You can pipe a GUID of a relationship object to the **Id** parameter of the **Get-SCSMRelationshipInstance** cmdlet.

## OUTPUTS

### EnterpriseManagementRelationshipObject
This cmdlet generates a relationship object.

## NOTES

## RELATED LINKS

[Service Manager Administrator Cmdlets Group 1](xref:SystemCenter2016/ServiceManagerCore/vlatest/ServiceManagerCore.md)

