---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FDD24C72-0FA0-4A1E-B3F1-00C2A4538FDF
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMDCMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMDCMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMDCMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Update-SCSMDCMWorkflow

## SYNOPSIS
Updates properties of a DCM workflow.

## SYNTAX

```
Update-SCSMDCMWorkflow [-Workflow] <DCMWorkflow[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMDCMWorkflow** cmdlet updates properties of a Desired Configuration Management (DCM) workflow.

## EXAMPLES

### Example 1: Change the description of a workflow
```
The first command gets workflows by using the Get-SCSMDCMWorkflow cmdlet. The command stores the workflow in the $Workflow variable.
PS C:\>$Workflow = Get-SCSMDCMWorkflow -DisplayName "Activity Event Workflow Configuration"

The second command assigns a new value to the **Description** property of $Workflow. 
PS C:\>$Workflow.Description = "This is a new description"

The third command passes the contents of $Workflow to the Format-List cmdlet by using the pipeline operator. The command displays the contents of $Workflow as a list. 
PS C:\>$Workflow | Format-List
DisplayName           : Activity Event Workflow Configuration
Description           : This is a new description
ConfigurationBaseLine : {}
Enabled               : False
ManagementPack        : [ServiceManager.IncidentManagement.Configuration] 
Template              : DefaultIncidentTemplate
EnableNotification    : True
Notification          : {System.Collections.Hashtable, System.Collections.Hashtable}

The final command updates the workflow to match the current value stored in $Workflow.
PS C:\>Update-SCSMDCMWorkflow -Workflow $Workflow
```

This example changes the description of a DCM workflow.

## PARAMETERS

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

### -PassThru
Indicates that this cmdlet returns the workflow that it updates.
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

### -Workflow
Specifies the instance of a DCM workflow to update.

```yaml
Type: DCMWorkflow[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Workflows.DCMWorkflow
You can pipe a DCM workflow to the *Workflow* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMDCMWorkflow.md)

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md)

[Remove-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMDCMWorkflow.md)

