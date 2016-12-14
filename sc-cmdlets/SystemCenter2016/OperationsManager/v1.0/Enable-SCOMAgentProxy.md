---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187688
schema: 2.0.0
ms.assetid: C0E5CE85-9A15-40D1-AE29-284C9594AC70
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Enable-SCOMAgentProxy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Enable-SCOMAgentProxy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Enable-SCOMAgentProxy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCOMAgentProxy

## SYNOPSIS
Enables agents to act as proxy agents for other computers.

## SYNTAX

```
Enable-SCOMAgentProxy [-Agent] <AgentManagedComputer[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCOMAgentProxy** cmdlet enables one or more agents to act as a proxy agents and discover managed objects on other computers.

## EXAMPLES

### Example 1: Enable an agent to act as a proxy agent
```
PS C:\>"server01.contoso.com" | Get-SCOMAgent | Enable-SCOMAgentProxy -PassThru
```

This command gets the Operations Manager agent named server01.contoso.com and enables the agent to act as a proxy agent for other agents and agentless managed computers.
The command passes the name of the agent to the *DNSHostName* parameter of the **Get-SCOMAgent** cmdlet.

### Example 2: Enable agents to act as a proxy agent
```
PS C:\>Get-SCOMAgent | Where-Object {$_.ProxyingEnabled.Value -eq $False} | Enable-SCOMAgentProxy -Confirm
```

This command gets all Operations Manager agents that have the **ProxyingEnabled** property set to $False, and then enables the agents to act as a proxy after the user confirms the action.

### Example 3: Enable an agent to act as a proxy agent by using a property value
```
PS C:\>$Agent = Get-SCOMAgent -DNSHostName "server01.contoso.com"
PS C:\> $Agent.ProxyingEnabled
```

This example enables an agent to act as an agent proxy by setting a property of the agent.

The first command gets the Operations Manager agent named server01.contoso.com, and stores it in the $Agent variable.

The second command enables the agent stored in the $Agent variable to act as a proxy agent for other computers.
The command sets the **ProxyingEnabled** property to $True for the agent stored in the $Agent variable.

## PARAMETERS

### -Agent
Specifies an array of **AgentManagedComputer** objects.
This parameter specifies the Operations Manager agents to enable to act as proxy agents.
To obtain an **AgentManagedComputer** object, use the **Get-SCOMADAgent** cmdlet.

```yaml
Type: AgentManagedComputer[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Position: 2
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

[Disable-SCOMAgentProxy](xref:SystemCenter2016/OperationsManager/v1.0/Disable-SCOMAgentProxy.md)

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMAgent.md)

