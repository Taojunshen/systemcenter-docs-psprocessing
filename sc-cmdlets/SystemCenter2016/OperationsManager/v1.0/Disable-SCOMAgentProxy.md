---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187689
schema: 2.0.0
ms.assetid: 7BEFD112-837A-4FD3-97B2-C0B3BE3D29F5
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Disable-SCOMAgentProxy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Disable-SCOMAgentProxy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Disable-SCOMAgentProxy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCOMAgentProxy

## SYNOPSIS
Disables agents from acting as a proxy agent for other computers.

## SYNTAX

```
Disable-SCOMAgentProxy [-Agent] <AgentManagedComputer[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCOMAgentProxy** cmdlet disables System Center 2016 - Operations Manager agents from acting as a proxy agents and discovering managed objects on other computers.

## EXAMPLES

### Example 1: Disable a proxy agent
```
PS C:\>"Server01.Contoso.com" | Get-SCOMAgent | Disable-SCOMAgentProxy
```

This command gets the Operations Manager agent named server01.contoso.com and disables it from acting as a proxy agent.

### Example 2: Disable agents that act as a proxy agent
```
PS C:\>Get-SCOMAgent | Where-Object {$_.ProxyingEnabled.Value -eq $True} | Disable-SCOMAgentProxy
```

This command gets all Operations Manager agents that have the **ProxyingEnabled** property set to $True, and then disables the agents from acting as a proxy agent.

## PARAMETERS

### -Agent
Specifies an array of **AgentManagedComputer** objects.
This parameter specifies the Operations Manager agents to disable from acting as proxy agents.
To obtain an **AgentManagedComputer** object, use the **Get-SCOMAgent** cmdlet.

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

[Enable-SCOMAgentProxy](xref:SystemCenter2016/OperationsManager/v1.0/Enable-SCOMAgentProxy.md)

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMAgent.md)

[Get-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMAgentlessManagedComputer.md)

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMAgent.md)

