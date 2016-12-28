---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 341D7933-67E3-4EDD-B8CD-69F6DA3BDEC5
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCSMWorkflow

## SYNOPSIS
Updates workflow properties.

## SYNTAX

```
Update-SCSMWorkflow [-Workflow] <Workflow[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMWorkflow** cmdlet updates workflow properties.

## EXAMPLES

### Example 1: Remove criteria from a workflow
```
PS C:\>$Workflow = Get-SCSMWorkflow -DisplayName "CustomWorkflow"
PS C:\> $Workflow.Criteria = $Null
PS C:\> Update-SCSMWorkflow -Workflow $Workflow
```

The first command gets the workflow named CustomWorkflow by using **Get-SCSMWorkflow**.
The command stores the workflow in the $Workflow variable.

The second command assigns a value of $Null to the **Criteria** property.
The command removes the criteria from the workflow.

The final command updates the workflow to the current value of $Workflow.

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
Specifies a workflow object that this cmdlet updates.
To obtain a workflow, use the Get-SCSMWorkflow cmdlet.

```yaml
Type: Workflow[]
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Workflows.Workflow
You can pipe a workflow object to the *Workflow* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflow.md)

[Get-SCSMWorkflowStatus](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMWorkflowStatus.md)

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md)

[Remove-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMWorkflow.md)

