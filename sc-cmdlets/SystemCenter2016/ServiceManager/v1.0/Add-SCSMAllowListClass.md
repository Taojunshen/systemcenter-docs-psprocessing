---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225317
schema: 2.0.0
ms.assetid: A7E7DAC3-3744-4AE2-9EF0-59A5EBBA63C5
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Add-SCSMAllowListClass.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Add-SCSMAllowListClass.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Add-SCSMAllowListClass.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCSMAllowListClass

## SYNOPSIS
Adds the specified classes to the allow list of classes for synchronization.

## SYNTAX

```
Add-SCSMAllowListClass [-ClassName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCSMAllowListClass** cmdlet adds the specified classes to the allow list of classes that the Service Manager Operations Manager CI Connector uses during synchronization.
The specified classes must already be defined in existing management packs.

## EXAMPLES

### Example 1: Add a class to the allow list
```
PS C:\>Add-SCSMAllowListClass -ClassName "System.SoftwareItem"
PS C:\> Get-SCSMAllowList
name                                                        mp
----                                                        --
System.Service                                              System.Library
System.Database                                             System.Library
Microsoft.Windows.ApplicationComponent                      Microsoft.Windows.Library
Microsoft.Windows.ComputerRole                              Microsoft.Windows.Library
System.Computer                                             System.Library
System.OperatingSystem                                      System.Library
Microsoft.Windows.LogicalDevice                             Microsoft.Windows.Library
System.SoftwareInstallation                                 System.Library
System.WebSite                                              System.Library
System.SoftwareItem                                         System.Software.Library
```

The first command adds the **SoftwareItem** class to the allow list.

The second command retrieves the allow list to verify the addition.

### Example 2: Add an invalid class name
```
PS C:\>Add-SCSMAllowListClass -ClassName "Config"
[CODE_Snippit]Add-SCSMAllowListClass[CODE_Snippit]: The management pack class Config could not be found. Did you mean: 
System.ConfigItem
System.Search.ProviderConfig
System.Announcement.Config
System.GroomingConfiguration
Microsoft.SystemCenter.ConfigureWorkflowTarget
Microsoft.SystemCenter.ConfigItemGroup
Microsoft.SystemCenter.ConfigurationManager.AICatalog
Microsoft.SystemCenter.ConfigurationManager.CollectionInfo
Microsoft.SystemCenter.ConfigurationManager.DCM_CI
Microsoft.SystemCenter.ConfigurationManager.DCM_NonCompliance_CI
Microsoft.SystemCenter.ConfigurationManager.DeployedComputer
Microsoft.SystemCenter.ConfigurationManager.Package
Microsoft.SystemCenter.ConfigurationManager.Program
System.Notification.ConfigurationSource
System.Notification.SIPConfigurationSource
System.Notification.SMTPConfigurationSource
Microsoft.SystemCenter.LinkingFramework.Configuration.CmdbSyncRuleTarget
System.LinkingFramework.SccmSource
Microsoft.EnterpriseManagement.LinkingFramework.OpsMgrConnector.Config
Microsoft.EnterpriseManagement.LinkingFramework.OpsMgrConnector.OpsMgrCIs
System.InboundEmail.Configuration
Microsoft.SystemCenter.ServiceManager.InboundEmail.Configuration.WorkflowTarget
System.WorkItem.Activity.WorkflowTarget
System.WorkItem.ChangeRequest.WorkflowTarget
Microsoft.SystemCenter.WorkItem.DCMIncident
System.WorkItem.Incident.Wizard.AutomaticChangeIncident
System.WorkItem.Incident.Wizard.DCMIntegration
Microsoft.SystemCenter.ServiceManager.Portal.Links.Configuration
ServiceManager.SoftwareDeployment.SCCM.Configuration
? 
At line:1 char:23
+ Add-SCSMAllowListClass <<<<  -ClassName Config
    + CategoryInfo          : InvalidData: (Config:String) [Add-SCSMAllowListClass], ArgumentException
    + FullyQualifiedErrorId : Invalid allow list XML,Microsoft.EnterpriseManagement.SMCmdlets.AddSCSMAllowListClass
```

This command attempts to add a class to the allow list.
However, Config is not a valid value for the *ClassName* parameter.

## PARAMETERS

### -ClassName
Specifies the names of the classes to add to the configuration item Operations Manager CI connector allow list.
Each class name must correspond to an ID property of an existing \<ClassType\> management pack element.
Separate multiple class names with a comma.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### -SCSession
Specifies an object that represents the session to a Service Manager management server.

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

[Get-SCSMAllowList](xref:SystemCenter2016/ServiceManager/v1.0/Get-SCSMAllowList.md)

[Remove-SCSMAllowListClass](xref:SystemCenter2016/ServiceManager/v1.0/Remove-SCSMAllowListClass.md)

[Reset-SCSMAllowList](xref:SystemCenter2016/ServiceManager/v1.0/Reset-SCSMAllowList.md)

