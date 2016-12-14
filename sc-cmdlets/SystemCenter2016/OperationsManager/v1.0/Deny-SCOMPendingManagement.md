---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187732
schema: 2.0.0
ms.assetid: CAAD701C-C43E-4B93-95BE-EEFEB16FE736
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Deny-SCOMPendingManagement.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Deny-SCOMPendingManagement.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Deny-SCOMPendingManagement.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Deny-SCOMPendingManagement

## SYNOPSIS
Denies pending agent management actions.

## SYNTAX

```
Deny-SCOMPendingManagement [-PendingAction] <AgentPendingAction[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Deny-SCOMPendingManagement** cmdlet denies pending management actions in System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Deny pending management entries
```
PS C:\>Get-SCOMPendingManagement | where {$_.AgentPendingActionType -eq "ManualApproval"} | Deny-SCOMPendingManagement -WhatIf
```

This command retrieves a list of agent management entries that are pending with an action of ManualApproval, and passes the output to the **Deny-SCOMPendingManagement** cmdlet by using the pipeline operator.
By using the *WhatIf* parameter, the cmdlet displays what action would occur if the command was implemented.
In this case, all targets with a pending action of ManualApproval would be denied.

## PARAMETERS

### -PendingAction
Specifies an array of pending actions to deny.
For information about how to get a pending action object, type "`Get-Help Get-SCOMPendingManagement`".

```yaml
Type: AgentPendingAction[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.EnterpriseManagement.Administration.AgentPendingAction
Represents a task that targets an agent on a managed computer.
The task is queued or awaiting administrator approval.

## OUTPUTS

## NOTES

## RELATED LINKS

[Approve-SCOMPendingManagement](xref:SystemCenter2016/OperationsManager/v1.0/Approve-SCOMPendingManagement.md)

[Get-SCOMPendingManagement](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMPendingManagement.md)

