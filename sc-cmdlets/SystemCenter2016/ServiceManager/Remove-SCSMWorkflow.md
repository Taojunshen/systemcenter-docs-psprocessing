---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225372
schema: 2.0.0
ms.assetid: 9AA6C164-BE4D-43AD-80F0-1D8B59CA714F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Remove-SCSMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Remove-SCSMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Remove-SCSMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMWorkflow

## SYNOPSIS
Removes a workflow from Service Manager.

## SYNTAX

```
Remove-SCSMWorkflow [-Workflow] <Workflow[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMWorkflow** cmdlet removes a workflow from Service Manager.

## EXAMPLES

### Example 1: Remove a workflow
```
PS C:\>Get-SCSMWorkflow -Name "Incident02" | Remove-SCSMWorkflow
```

This command gets the workflow named Incident02 by using the Get-SCSMWorkflow cmdlet.
The command passes that object to the current cmdlet by using the pipeline operator.
That cmdlet deletes that workflow.

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
Specifies an object that represents the workflow to remove.

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
You can pipe a workflow to the *Workflow* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/Get-SCSMWorkflow.md)

[Get-SCSMWorkflowStatus](xref:SystemCenter2016/ServiceManager/Get-SCSMWorkflowStatus.md)

[New-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/New-SCSMDCMWorkflow.md)

[Update-SCSMWorkflow](xref:SystemCenter2016/ServiceManager/Update-SCSMWorkflow.md)

