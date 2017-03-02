---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6A0D9B81-1E44-4D68-86F0-EA1C837EE80F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMDCMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMDCMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMDCMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMDCMWorkflow

## SYNOPSIS
Retrieves the list of DCM workflows that are defined in Service Manager.

## SYNTAX

```
Get-SCSMDCMWorkflow [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMDCMWorkflow** cmdlet retrieves the Desired Configuration Management (DCM) workflows that are defined in Service Manager.

## EXAMPLES

### Example 1: Get workflows
```
C:\PS>Get-SCSMDCMWorkflow
DisplayName     Description   Enabled

-----------     -----------   -------

My DCM Workflow A Description True
```

This command retrieves DCM workflows.
In this example, there is a single workflow.

### Example 2: Display formatted list of workflows
```
C:\PS>Get-SCSMDCMWorkflow | Format-List
DisplayName           : My DCM Workflow
Description           : A Description
ConfigurationBaseLine : {}
Enabled               : True
ManagementPack        : [ServiceManager.IncidentManagement.Configuration] 
Template              : 
EnableNotification    : True
Notification          : {}
```

This command retrieves DCM workflows.
In this example, there is a single workflow.
The command uses the Format-List cmdlet to format the results.

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
Specifies the display name of the workflow to retrieve.
You can specify wildcard characters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

### Workflow types.
This cmdlet returns workflow types.

## NOTES

## RELATED LINKS

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md)

[Remove-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMDCMWorkflow.md)

[Update-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMDCMWorkflow.md)

