---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187738
schema: 2.0.0
ms.assetid: 145FAC62-DBBC-4D2B-8BAD-34A5874845A5
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Remove-SCOMAgentlessManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Remove-SCOMAgentlessManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Remove-SCOMAgentlessManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMAgentlessManagedComputer

## SYNOPSIS
Removes agentless managed computers from a management group.

## SYNTAX

```
Remove-SCOMAgentlessManagedComputer [-Computer] <RemotelyManagedComputer[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMAgentlessManagedComputer** cmdlet removes one or more agentless managed computers from a management group.

## EXAMPLES

### Example 1: Remove agentless managed computers from the management group
```
PS C:\>Get-SCOMAgentlesslyManagedComputer -DNSHostName "server01*" | Remove-SCOMAgentlessManagedComputer -Confirm
```

This command removes managed computers that do not have Operations Manager agent.
The command uses the **Get-SCOMAgentlesslyManagedComputer** cmdlet to get all agentless managed computers with names that begin with server01, and passes the results to the **Remove-SCOMAgentlessManagedComputer** cmdlet by using the pipeline operator.
The command removes the agentless managed computers returned by the **Get-SCOMAgentlesslyManagedComputer** cmdlet from the management group.

## PARAMETERS

### -Computer
Specifies an array of agentless managed computers.
You can use the **Get-SCOMAgentlessManagedComputer** cmdlet to get managed computers that do not have Operations Manager agents.

```yaml
Type: RemotelyManagedComputer[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMAgentlessManagedComputer.md)

[Add-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/v1/Add-SCOMAgentlessManagedComputer.md)

[Set-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/v1/Set-SCOMAgentlessManagedComputer.md)

