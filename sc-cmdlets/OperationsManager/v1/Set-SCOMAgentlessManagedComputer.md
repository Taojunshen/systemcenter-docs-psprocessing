---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187729
schema: 2.0.0
ms.assetid: 4E54E2BB-2F04-4BDC-B64A-29B4D2AF26D0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMAgentlessManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMAgentlessManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMAgentlessManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMAgentlessManagedComputer

## SYNOPSIS
Changes the settings for agentless managed computers.

## SYNTAX

### FromAgentManagedBy
```
Set-SCOMAgentlessManagedComputer [-Computer] <RemotelyManagedComputer[]>
 [-ManagedByAgent] <AgentManagedComputer> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementServerManagedBy
```
Set-SCOMAgentlessManagedComputer [-Computer] <RemotelyManagedComputer[]>
 [-ManagedByManagementServer] <ManagementServer> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMAgentlessManagedComputer** cmdlet changes settings for agentless managed computers.

## EXAMPLES

### Example 1: Set the Operations Manager agent to perform agentless monitoring
```
PS C:\>Get-SCOMAgentlessManagedComputer -DNSHostName "server02.contoso.com" | Set-SCOMAgentlessManagedComputer -ManagedByAgent (Get-SCOMAgent -DNSHostName "OMAgent01.contoso.com") -PassThru
```

This command gets the agentless managed computer named server02 and passes it to the **Set-SCOMAgentlessManagedComputer** cmdlet by using a pipe operator.
The command sets the agent-managed computer named OMAgent01 as the Operations Manager agent that performs agentless monitoring for server02.

## PARAMETERS

### -Computer
Specifies an array of agentless managed computers.
You can use the **Get-SCOMAgentlessManagedComputer** cmdlet to get managed computers that do not have agents.

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

### -ManagedByAgent
Specifies an **AgentManagedComputer** object.
This parameter specifies the Operations Manager agent that performs agentless monitoring.
The action account of the agent that performs the monitoring must have local administrative rights on the computer that it monitors.

To obtain an **AgentManagedComputer** object, use the **Get-SCOMAgent** cmdlet.

```yaml
Type: AgentManagedComputer
Parameter Sets: FromAgentManagedBy
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedByManagementServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server that performs agentless monitoring of the agentless managed computers.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: FromManagementServerManagedBy
Aliases: 

Required: True
Position: 1
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCOMAgentlessManagedComputer](xref:OperationsManager/v1/Add-SCOMAgentlessManagedComputer.md)

[Set-SCOMAgentlessManagedComputer](xref:OperationsManager/v1/Set-SCOMAgentlessManagedComputer.md)

[Get-SCOMAgentlessManagedComputer](xref:OperationsManager/v1/Get-SCOMAgentlessManagedComputer.md)

[Get-SCOMAgent](xref:OperationsManager/v1/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:OperationsManager/v1/Get-SCOMManagementServer.md)

