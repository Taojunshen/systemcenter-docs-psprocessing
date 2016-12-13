---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=239724
schema: 2.0.0
ms.assetid: A9139732-4930-468F-9D99-7DEFD23128B4
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMParentManagementServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMParentManagementServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMParentManagementServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMParentManagementServer

## SYNOPSIS
Gets the management servers to which an agent reports.

## SYNTAX

### FromAgent (Default)
```
Get-SCOMParentManagementServer [-Agent] <AgentManagedComputer[]> [<CommonParameters>]
```

### FromGatewayManagementServer
```
Get-SCOMParentManagementServer [-GatewayServer] <ManagementServer[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMParentManagementServer** cmdlet retrieves the management servers to which an agent reports.
In System Center 2016 - Operations Manager, primary and failover management servers provide redundancy for agents and gateway management servers.

## EXAMPLES

### Example 1: Retrieve a list of management servers
```
PS C:\>Get-SCOMParentManagementServer -Agent (Get-SCAgent -Name "Server01.Contoso.com")
```

This command retrieves the management servers to which the agent named Server01 reports.

The command in parentheses executes first and retrieves the agent named Server01.
The cmdlet then uses the results of the command in parentheses as input to the *Agent* parameter.

### Example 2: Retrieve a list of management servers by wildcard
```
PS C:\>$Agents = "Server*.Contoso.com" | Get-SCAgent
PS C:\> Get-SCOMParentManagementServer -Agent $Agents
```

This example retrieves a list of management server for agent names that match a specific string.

The first command uses the **Get-SCAgent** cmdlet to get agents that begin with the string Server with a wildcard character.
The cmdlet stores the agents in the $Agents variable.

The second command uses the **Get-SCOMParentManagementServer** cmdlet to get the management servers in the $Agents variable.

### Example 3: Retrieve a list of management server using pipes
```
PS C:\>"Server01.Contoso.com" | Get-SCAgent | Get-SCOMParentManagementServer
```

This command passes the agent named Server01.Consoso.com to the **Get-SCAgent** cmdlet by using the pipeline operator, and then passes the output to the **Get-SCOMParentManagementServer** cmdlet.

## PARAMETERS

### -Agent
Specifies an array of one or more agent objects.
For more information about how to get an agent object, type "`Get-Help Get-SCAgent`".

```yaml
Type: AgentManagedComputer[]
Parameter Sets: FromAgent
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GatewayServer
Specifies an array of gateway management servers.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer[]
Parameter Sets: FromGatewayManagementServer
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-SCOMParentManagementServer](xref:OperationsManager/v1/Set-SCOMParentManagementServer.md)

