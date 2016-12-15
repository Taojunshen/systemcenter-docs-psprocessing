---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225345
schema: 2.0.0
ms.assetid: 64E9CD5C-F4A2-4128-89F1-47E96E77F91C
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMWorkflow

## SYNOPSIS
Retrieves configuration information for Service Manager workflows.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMWorkflow [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMWorkflow [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCSMWorkflow [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMWorkflow** cmdlet retrieves configuration information for Service Manager workflows.

## EXAMPLES

### Example 1: Get workflow configuration
```
PS C:\>Get-SCSMWorkflow
Enabled DisplayName                                             ManagementPackName
------- -----------                                             ------------------
True    New Service Request Workflow                            ServiceManager.ServiceRequest.Library
True    Service Request Status Changed                          ServiceManager.ServiceRequest.Library
True    Resolve Incident Workflow                               ServiceManager.ProblemManagement.Library
True    Dependent Activity Status                               ServiceManager.ActivityManagement.Library
True    Resolve Child Incidents (Parent Incident resolved)      ServiceManager.IncidentManagement.Library
```

This command retrieves the workflow configuration.

### Example 2: Get the Activity Event Workflow Configuration
```
This command gets information for the specified workflow, and then stores it in the $Workflow variable.  
PS C:\>$WorkFlow = Get-SCSMWorkflow -DisplayName "Activity Event Workflow Configuration"


This command passes the contents of $Workflow to the Format-List cmdlet. That cmdlet displays the results as a list. 
PS C:\>$WorkFlow | Format-List
DisplayName          : Activity Status Changed Workflow
Description          : Activity Status Changed Workflow
Enabled              : True
Event                : Update
ManagementPack       : [ServiceManager.ActivityManagement.Library, 31bf3856ad364e35, 7.5.1354.0] 
Criteria             : <Criteria>
                         <Expression>
                           <Or>
                             <Expression>
                               <And>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Pre">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Active"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Post">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Completed"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                               </And>
                             </Expression>
                             <Expression>
                               <And>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Pre">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Active"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Post">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Skipped"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                               </And>
                             </Expression>
                             <Expression>
                               <And>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Pre">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Rerun"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Post">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Skipped"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                               </And>
                             </Expression>
                             <Expression>
                               <And>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Pre">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Active"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                                 <Expression>
                                   <SimpleExpression>
                                     <ValueExpression>
                                       <Property State="Post">$Context/Property[Type='Activity!System.WorkItem.Activity']/Status$</Property>
                                     </ValueExpression>
                                     <Operator>Equal</Operator>
                                     <ValueExpression>
                                       <Value>$MPElement[Name="Activity!ActivityStatusEnum.Failed"]$</Value>
                                     </ValueExpression>
                                   </SimpleExpression>
                                 </Expression>
                               </And>
                             </Expression>
                           </Or>
                         </Expression>
                       </Criteria>
Template             : 
EnableNotification   : False
Notification         : {}
WorkflowSubscription : Microsoft.EnterpriseManagement.Subscriptions.WorkflowSubscription
ManagementPackName   : ServiceManager.ActivityManagement.Library


This command uses standard dot syntax to display the **ManualActivity** property of $Workflow.
PS C:\>$WorkFlow.ManualActivity
DisplayName Description                                                                 Enabled
----------- -----------                                                                 -------
workflow1   Created manual activities will email the reviewers with the assign template false
workflow2   Notify reviewers on updates of a manual activity                            true
```

This example retrieves the configuration of the Activity Event Workflow Configuration workflow.

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
Specifies the display name of the workflow configuration to retrieve.
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
Specifies the ID of the workflow configuration to retrieve.

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
Specifies the name of the workflow configuration to retrieve.
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
Specifies the object that represents the session to a Service Manager management server.

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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Workflows.Workflow
This cmdlet retrieves information about workflows.

## NOTES

## RELATED LINKS

[Get-SCSMWorkflowStatus](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflowStatus.md)

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md)

[Remove-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMWorkflow.md)

[Update-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMWorkflow.md)

