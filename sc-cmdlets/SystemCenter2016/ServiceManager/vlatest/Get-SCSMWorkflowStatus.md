---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4BC4D031-01F5-40A6-9B38-BF98617F1322
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflowStatus.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflowStatus.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflowStatus.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMWorkflowStatus

## SYNOPSIS
Retrieves the status of workflows in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMWorkflowStatus [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMWorkflowStatus [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCSMWorkflowStatus [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMWorkflowStatus** cmdlet retrieves the status of workflows in Service Manager.

## EXAMPLES

### Example 1: Get the status of all workflows
```
C:\PS>Get-SCSMWorkflowStatus
Name                                                                   ManagementPackName                               Sealed Enabled TimeAdded
----                                                                   ------------------                               ------ ------- ---------
ServiceManager.IncidentManagement.ParentIncidentActivated.UpdateRule   ServiceManager.IncidentManagement.Library        True   true    8/8/2011 7:00:54 PM
ServiceManager.ActivityManagement.ActivityStatusChangedRule            ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ServiceRequest.Library.Rule.ActivityRerun               ServiceManager.ServiceRequest.Library            True   true    8/8/2011 7:04:54 PM
ServiceManager.ActivityManagement.ReviewerDeletedRule                  ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ActivityManagement.ActivityAddedRule                    ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ChangeManagement.ChangeRequestStatusChangedRule         ServiceManager.ChangeManagement.Library          True   true    8/8/2011 7:00:01 PM
ServiceManager.IncidentManagement.ParentIncidentResolved.UpdateRule    ServiceManager.IncidentManagement.Library        True   true    8/8/2011 7:00:54 PM
ServiceManager.ReleaseManagement.ActivityStatusChangedRule             ServiceManager.ReleaseManagement.Library         True   true    8/8/2011 7:00:24 PM
ServiceManager.ReleaseManagement.ActivityRerunRule                     ServiceManager.ReleaseManagement.Library         True   true    8/8/2011 7:00:24 PM
ServiceManager.ChangeManagement.ActivityStatusChangedRule              ServiceManager.ChangeManagement.Library          True   true    8/8/2011 7:00:01 PM
ServiceManager.ServiceRequest.Library.Rule.ServiceRequestStatusChanged ServiceManager.ServiceRequest.Library            True   true    8/8/2011 7:04:54 PM
ServiceManager.ReleaseManagement.ActivityAddedRule                     ServiceManager.ReleaseManagement.Library         True   true    8/8/2011 7:00:24 PM
ServiceManager.ActivityManagement.ReviewActivityActiveRule             ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ActivityManagement.ActivitySkippedRule                  ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ActivityManagement.ReviewerAddedRule                    ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ProblemManagement.Library.Rule.ResolveIncident          ServiceManager.ProblemManagement.Library         True   true    8/8/2011 7:01:37 PM
ServiceManager.ReleaseManagement.NewReleaseRecordRule                  ServiceManager.ReleaseManagement.Library         True   true    8/8/2011 7:00:24 PM
ServiceManager.ActivityManagement.DependentActivityActiveRule          ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ServiceRequest.Library.Rule.ActivityAdded               ServiceManager.ServiceRequest.Library            True   true    8/8/2011 7:04:54 PM
ServiceManager.ActivityManagement.DependentRelationshipCreatedRule     ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ActivityManagement.ReviewActivityUpdatedRule            ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
SSPModuleInvocationRule                                                ServiceManager.SoftwareDeployment.Configurations False  false   8/8/2011 7:05:21 PM
ServiceManager.IncidentManagement.ParentIncidentResolved.AddRule       ServiceManager.IncidentManagement.Library        True   true    8/8/2011 7:00:54 PM
ServiceManager.ChangeManagement.ActivityAddedRule                      ServiceManager.ChangeManagement.Library          True   true    8/8/2011 7:00:01 PM
ServiceManager.ActivityManagement.ReviewerVotedRule                    ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ActivityManagement.ContainerActivityStatusAlertRule     ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
ServiceManager.ReleaseManagement.ReleaseRecordStatusAlertRule          ServiceManager.ReleaseManagement.Library         True   true    8/8/2011 7:00:24 PM
ServiceManager.ServiceRequest.Library.Rule.ActivityStatusChanged       ServiceManager.ServiceRequest.Library            True   true    8/8/2011 7:04:54 PM
ServiceManager.ChangeManagement.ActivityRerunRule                      ServiceManager.ChangeManagement.Library          True   true    8/8/2011 7:00:01 PM
ServiceManager.ServiceRequest.Library.Rule.NewServiceRequest           ServiceManager.ServiceRequest.Library            True   true    8/8/2011 7:04:54 PM
ServiceManager.ChangeManagement.NewChangeRequestRule                   ServiceManager.ChangeManagement.Library          True   true    8/8/2011 7:00:01 PM
ServiceManager.ActivityManagement.DependentActivityStatusRule          ServiceManager.ActivityManagement.Library        True   true    8/8/2011 6:59:27 PM
```

This command retrieves the status of all workflows.

### Example 2: Get the status of a single workflow
```
PS C:\>Get-SCSMWorkflowStatus -Name "ServiceManager.ActivityManagement.ActivityStatusChangedRule"
Name                                                        ManagementPackName                        Sealed Enabled TimeAdded
----                                                        ------------------                        ------ ------- ---------
ServiceManager.ActivityManagement.ActivityStatusChangedRule ServiceManager.ActivityManagement.Library True   true    12/2/2010 12:21:44 AM
```

This command retrieves the status of the ServiceManager.ActivityManagement.ActivityStatusChangedRule workflow.

### Example 3: Get the status of underlying activities
```
PS C:\>$Status = Get-SCSMWorkflowStatus -Name "ServiceManager.ActivityManagement.ActivityStatusChangedRule"
PS C:\> $Status.GetStatus()
Status    TimeStarted           TimeFinished          Duration         RelatedObject
------    -----------           ------------          --------         -------------
Succeeded 12/2/2010 12:42:42 AM 12/2/2010 12:42:43 AM 00:00:00.1970000 RA3: Initial Screening
```

The first command retrieves the status of the ServiceManager.ActivityManagement.ActivityStatusChangedRule workflow, and then stores it in the $Status variable.

The second command retrieves the status of the underlying activities of the workflow in $Status.

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
Specifies the display name of the workflow object to retrieve.

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
Specifies the unique ID of the workflow object to be retrieved.

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
Specifies the name of the workflow object to retrieve.

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
You can pipe a workflow name to the *DisplayName* parameter.

### System.Guid
You can pipe a GUID of a workflow object to the *Id* parameter.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackRule
This cmdlet retrieves information about workflows.

## NOTES

## RELATED LINKS

[Get-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflow.md)

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md)

[Remove-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMWorkflow.md)

[Update-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMWorkflow.md)

