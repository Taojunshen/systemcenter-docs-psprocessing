---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225361
schema: 2.0.0
ms.assetid: D4F01783-217A-4A7F-8380-3FC3C747AE3B
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/New-SCSMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/New-SCSMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/New-SCSMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSMWorkflow

## SYNOPSIS
Creates a workflow in Service Manager.

## SYNTAX

```
New-SCSMWorkflow -Class <String> [-DisplayName] <String> [-Description <String>] [-Enable <Boolean>]
 [-Event <WorkflowEvent>] [-ManagementPack <ManagementPack>] [-Criteria <String>]
 [-Template <ManagementPackObjectTemplate>] [-EnableNotification <Boolean>] [-Notification <Hashtable[]>]
 [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMWorkflow** cmdlet creates a workflow in Service Manager.

## EXAMPLES

### Example 1: Create a workflow for manual activity creation
```
PS C:\>$Template = Get-SCSMObjectTemplate -Name "DefaultManualActivityTemplate"
PS C:\> $Notification = @{ User = "Reviewers"; Template = Get-SCSMObjectTemplate -Name "AssignedToUserNotificationTemplate" },@{ User = "Affected User"; Template = Get-SCSMObjectTemplate -Name DefaultReviewActivityTemplate }
PS C:\> New-SCSMWorkflow -DisplayName "Manual activity workflow 07" -Class "ManualActivity" -Description "Contoso workflow 07." -Enable $True -Event Create -Notification $Notification -Template $Template
```

The first command gets a template named DefaultManualActivityTemplate by using the Get-SCSMObjectTemplate cmdlet.
The command stores the template in the $Template variable.

The second command creates an array of notifications as hash tables, and stores them in the $Notification variable.

The final command creates a workflow which can be used when a manual activity is created.
Because the script specifies no criteria, this workflow applies to any creation of a manual activity.

### Example 2: Create a workflow for manual activity creation for a user
```
PS C:\>$CriteriaString = @'
>>  <Criteria>
>>   <Expression>
>>    <SimpleExpression>
>>     <ValueExpression>
>>      <Property State="Post">
>>  $Context/$Path[Relationship='System.WorkItem.Library!System.WorkItemCreatedByUser' TypeConstraint='System!System.Domain.User']/Property[Type='System!System.Domain.User']/UserName$
>>      </Property>
>>     </ValueExpression>
>>     <Operator>Equal</Operator>
>>     <ValueExpression>
>>      <Value>Evan Narvaez</Value>
>>     </ValueExpression>
>>    </SimpleExpression>
>>   </Expression>
>>  </Criteria>
>>  '@
PS C:\> $ManagementPack = Get-SCSMManagementPack -Name "Workflows"
PS C:\> $Template = Get-SCSMObjectTemplate -Name "DefaultManualActivityTemplate"
PS C:\> $Notification = @{ User = "Reviewers"; Template = Get-SCSMObjectTemplate -Name AssignedToUserNotificationTemplate },@{ User = "Affected User"; Template = Get-SCSMObjectTemplate -Name DefaultReviewActivityTemplate }
PS C:\> New-SCSMWorkflow -DisplayName "Manual activity workflow 09" -Class "ManualActivity" -Criteria $CriteriaString -Description "Contoso workflow 09." -Enable $False -Event Create -ManagementPack $ManagementPack -Template $Template
```

The first command creates a criteria string defined for the manual activity to select only those manual activities that were created by the user Evan Narvaez.
The command stores those criteria in the $CriteriaString variable.

The second command gets the management pack named Workflows by using the Get-SCSMManagementPack cmdlet, and then stores it in the $ManagementPack variable.
A subsequent command uses this value to specify where to save the workflow.
This must not be a sealed management pack.

The third command gets a template named DefaultManualActivityTemplate by using the Get-SCSMObjectTemplate cmdlet.
The command stores the template in the $Template variable.

The fourth command creates an array of notifications as hash tables, and stores them in the $Notification variable.

The final command creates a workflow which can be used when a manual activity is created.

## PARAMETERS

### -Class
Specifies the name of the class that starts the workflow when it changes.
Valid values are: 

- Configuration 
- Change 
- Incident 
- ManualActivity 
- ReviewActivity 
- DeploymentActivity

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

### -Criteria
Specifies an object that represents criteria to restrict the result set.

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

### -Description
Specifies a description for the workflow.

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
Specifies the name of the workflow to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates whether this cmdlet enables or disables the workflow.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNotification
Indicates whether this cmdlet enables or disables notifications from the workflow.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Event
Specifies the condition under which the workflow starts.
Valid values are: 

- Create 
- Update

```yaml
Type: WorkflowEvent
Parameter Sets: (All)
Aliases: 
Accepted values: Create, Update

Required: False
Position: Named
Default value: Created
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementPack
Specifies the management pack in which to store the workflow.
Do not specify a sealed management pack.

```yaml
Type: ManagementPack
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: The default management pack
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notification
Specifies a hash table of users and templates to be used for notifications from the workflow.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the workflow that this cmdlet creates.
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

### -Template
Specifies the template to be applied to the objects which the workflow affects.

```yaml
Type: ManagementPackObjectTemplate
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

[Get-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/v1.0/Get-SCSMWorkflow.md)

[Remove-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/v1.0/Remove-SCSMWorkflow.md)

[Update-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/v1.0/Update-SCSMWorkflow.md)

