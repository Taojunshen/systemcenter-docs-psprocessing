---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 08034BE8-7617-4782-B0C3-FCAD6EA10D6A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMTask.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMTask.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMTask.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMTask

## SYNOPSIS
Retrieves tasks that are defined in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMTask [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMTask [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromName
```
Get-SCSMTask [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMTask** cmdlet retrieves tasks that are defined in Service Manager.

## EXAMPLES

### Example 1: Get all tasks associated with incidents
```
PS C:\>Get-SCSMTask -DisplayName "*incident*"
Enabled Category   Name                                                                description
------- --------   ----                                                                -----------
True    Alert      System.WorkItem.Incident.GeneralSettings.Task                       View or edit the general settings for incident management

True    Alert      System.WorkItem.Incident.ViewAlertDetailsCommand.Task               View alert details
True    Alert      Microsoft.EnterpriseManagement.ServiceManager.UI.Administration.... Create an Incident Resolver user role
True    Alert      System.WorkItem.Incident.ViewHealthStateCommand.Task                View the configuration item's health state
True    Alert      System.WorkItem.Incident.RequestUserInputCommand.Task               Request user input
True    Alert      ServiceManager.IncidentManagement.Library.Task.DesiredConfiguration Configure System Center Configuration Manager Desired Configuration... 
True    Alert      System.WorkItem.Incident.CreateIncidentforConfigItem.Task           Create an incident linked to the current item
True    Alert      System.WorkItem.Incident.ChangeStatusCommand.Task                   Change the incident status
True    Alert      System.WorkItem.Incident.ActivateIncidentCommand.Task               Activate the incident
True    Alert      ConsoleTask.HelpIncident                                            Service Manager Incident Management Help
True    Alert      System.WorkItem.Incident.AssignToMeCommand.Task                     Assign the incident to me
True    Alert      System.WorkItem.Incident.New.Task                                   Create an incident
True    Alert      ServiceManager.IncidentManagement.Library.Task.AutomaticIncident... Configure incident change workflows
True    Alert      System.WorkItem.Incident.EscalateIncidentCommand.Task               Escalate or transfer the incident
True    Alert      System.WorkItem.Incident.AssignCommand.Task                         Assign the incident to an analyst
True    Alert      System.WorkItem.Incident.PingComputerCommand.Task                   Ping related computers
True    Alert      System.WorkItem.Incident.ApplyTemplateCommand.Task                  Apply a template
True    Alert      System.WorkItem.Incident.RemoteComputerCommand.Task                 Remote desktop
True    Alert      System.WorkItem.Incident.CloseIncidentCommand.Task                  Close the incident
True    Alert      System.WorkItem.Incident.ResolveIncidentCommand.Task                Resolve the incident
```

This command retrieves all tasks that are associated with incidents.

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
Default value: None
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
Specifies the display name of the task object to retrieve.

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
Specifies the ID of the task object to retrieve.

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
Specifies the name of the task object to retrieve.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a name to the *DisplayName* parameter.

### System.Guid
You can pipe a GUID to the *Id* parameter.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackConsoleTask
This cmdlet returns task objects.

## NOTES

## RELATED LINKS

