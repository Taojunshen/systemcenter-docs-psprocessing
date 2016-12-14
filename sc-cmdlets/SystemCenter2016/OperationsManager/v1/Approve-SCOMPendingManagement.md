---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187731
schema: 2.0.0
ms.assetid: 2A39116B-60A4-4059-988B-9C29732F1556
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Approve-SCOMPendingManagement.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Approve-SCOMPendingManagement.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Approve-SCOMPendingManagement.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Approve-SCOMPendingManagement

## SYNOPSIS
Approves pending agent management actions.

## SYNTAX

```
Approve-SCOMPendingManagement [-PendingAction] <AgentPendingAction[]> [[-ActionAccount] <PSCredential>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Approve-SCOMPendingManagement** cmdlet approves pending management actions in System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Retrieve pending management entries
```
PS C:\>Get-SCOMPendingManagement | where {$_.AgentPendingActionType -eq "ManualApproval"} | Approve-SCOMPendingManagement -WhatIf
```

This command retrieves the agent management entries that are pending with an action of ManualApproval.
By using the *WhatIf* parameter, the cmdlet displays the actions that occur if the command was implemented.

## PARAMETERS

### -PendingAction
Specifies an array of pending actions to approve.
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

### -ActionAccount
Specifies the credentials for a pending action.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type "` Get-Help Get-Credential`".

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
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
Represents a task that targets an agent on a managed computer, pending administrator approval.

## OUTPUTS

## NOTES

## RELATED LINKS

[Deny-SCOMPendingManagement](xref:SystemCenter2016/OperationsManager/v1/Deny-SCOMPendingManagement.md)

[Get-SCOMPendingManagement](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMPendingManagement.md)

