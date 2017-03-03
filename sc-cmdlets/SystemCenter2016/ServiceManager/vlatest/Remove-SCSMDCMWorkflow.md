---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F30C171F-3F22-4D07-92CF-14394F1F3FB5
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMDCMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMDCMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMDCMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCSMDCMWorkflow

## SYNOPSIS
Removes a DCM workflow from Service Manager.

## SYNTAX

```
Remove-SCSMDCMWorkflow [-Workflow] <DCMWorkflow[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMDCMWorkflow** cmdlet removes a Desired Configuration Management (DCM) workflow from Service Manager.

## EXAMPLES

### Example 1: Remove a workflow
```
The first command gets the workflows that match the specified display name by using the Get-SCSMDCMWorkflow cmdlet. The cmdlet displays the results. 
PS C:\>Get-SCSMDCMWorkflow -DisplayName "MyDCM*"
DisplayName   Description           Enabled
-----------   -----------           -------
MyDCMWorkflow This is a description False

The second command passes the results of the **Get-SCSMDCMWorkflow** cmdlet to the current cmdlet by using the pipeline operator. The command removes the workflow. 
PS C:\>Get-SCSMDCMWorkflow -DisplayName "MyDCM*" | Remove-SCSMDCMWorkflow 

The final command repeats the first command. The results show that the workflow has been deleted. 
PS C:\>Get-SCSMDCMWorkflow -DisplayName "MyDCM*"
```

This example removes a DCM workflow.

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
Specifies instances of DCM workflows.

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
You can pipe a Service Manager DCM workflow to the *Workflow* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMDCMWorkflow.md)

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md)

[Update-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMDCMWorkflow.md)

