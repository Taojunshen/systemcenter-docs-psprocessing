---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BD89CAB4-8A41-4C85-91AA-E71929F64121
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMParentManagementServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMParentManagementServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMParentManagementServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMParentManagementServer

## SYNOPSIS
Modifies the primary and failover management servers for an agent or gateway management server.

## SYNTAX

### FromAgentPrimaryServer (Default)
```
Set-SCOMParentManagementServer [-Agent] <AgentManagedComputer[]> [-PrimaryServer] <ManagementServer>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromAgentFailoverServer
```
Set-SCOMParentManagementServer [-Agent] <AgentManagedComputer[]> [-FailoverServer] <ManagementServer[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGatewayManagementServer
```
Set-SCOMParentManagementServer [-PrimaryServer] <ManagementServer> [-GatewayServer] <ManagementServer[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGatewayFailoverManagementServer
```
Set-SCOMParentManagementServer [-GatewayServer] <ManagementServer[]> [-FailoverServer] <ManagementServer[]>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMParentManagementServer** cmdlet modifies the primary and failover management servers for an agent or gateway management server.
In System Center 2016 - Operations Manager, primary and failover management servers provide redundancy for agents and gateway management servers.

This cmdlet requires an agent object or a gateway management server object, and a management server object.
For information about how to get an agent object, type `Get-Help Get-SCAgent`.
For information about how to get a gateway management server object, type "`Get-Help Get-SCOMGatewayManagementServer`".

This cmdlet cannot modify both the primary server and the failover management server in the same command.

## EXAMPLES

### Example 1: Set the primary and failover management servers
```
PS C:\>$PrimaryMgmtServer = Get-SCManagementServer -Name "MgmtServer01.Contoso.com"
PS C:\> $FailoverMgmtServer = Get-SCManagementServer -Name "MgmtServer02.Contoso.com"
PS C:\> "Server01.Contoso.com" | Get-SCAgent | Set-SCOMParentManagementServer -PrimaryServer $PrimaryMgmtServer -Passthru
PS C:\> "Server01.Contoso.com" | Get-SCAgent | Set-SCOMParentManagementServer -FailoverServer $FailoverMgmtServer -Passthru
```

This example sets the primary and failover parent management server.

The first two commands use the **Get-SCManagementServer** cmdlet to get a management server to set as the agent's primary management server, and a management server to set as the agent's failover management server.
The commands store the objects in the $PrimaryMgmtServer, and $FailoverMgmtServer variables, respectively.

The third command uses the **Get-SCAgent** cmdlet to get the agent named Server01.Contoso.com and passes the result to the **Set-SCOMParentManagementServer** cmdlet by using the pipeline operator.
The command sets the primary management server specified in the $PrimaryMgmtServer variable.
It then uses the **PassThru** parameter to generate an object.
Without the **PassThru** parameter, **Set-SCOMParentManagementServer** does not generate any output.

The fourth command, in a manner similar to the third command, sets the failover management server specified in the $FailoverMgmtServer variable.

### Example 2: Set the gateway primary server and failover server
```
PS C:\>$PrimaryMgmtServer = Get-SCManagementServer -name "MgmtServer01.Contoso.com"
PS C:\> $FailoverMgmtServer = Get-SCManagementServer -Name "MgmtServer02.Contoso.com"
PS C:\> "GatewayMgmtServer01.Contoso.com" | Get-SCOMGatewayManagementServer | Set-SCOMParentManagementServer -PrimaryServer $PrimaryMgmtServer 
PS C:\> "GatewayMgmtServer01.Contoso.com" | Get-SCOMGatewayManagementServer | Set-SCOMParentManagementServer -FailoverServer $FailoverMgmtServer
```

This example sets the gateway, primary, and failover parent management servers.

The first two commands use the **Get-SCManagementServer** cmdlet to get a management server to set as the gateway server's primary management server, and a management server to set as the gateway server's failover management server.
The commands store the objects in the $PrimaryMgmtServer, and $FailoverMgmtServer variables, respectively.

The third command uses the **Get-SCOMGatewayManagementServer** cmdlet to get the gateway management server named GatewayMgmtServer01.Contoso.com and pipes the result to the **Set-SCOMParentManagementServer** cmdlet to set the primary management server specified in the $PrimaryMgmtServer variables for the gateway management server.

The fourth command uses the **Get-SCOMGatewayManagementServer** cmdlet to get the gateway management server named GatewayMgmtServer01.Contoso.com and pipes the result to the **Set-SCOMParentManagementServer** cmdlet to set the failover management server specified in the $FailoverMgmtServer variable for the gateway management server.

### Example 3: Set the primary management server
```
PS C:\>Set-SCOMParentManagementServer -Agent (Get-SCAgent -Name "Server01.Contoso.com") -PrimaryServer (Get-SCManagementServer -Name "MgmtServer01.Contoso.com")
```

This example sets the primary management server for the specified agent.

The commands in parentheses, which are executed first, get the agent named Server01, and the management server named MgmtServer01.
The cmdlet then passes the results of the commands in parentheses to the **Set-SCOMParentManagementServer** cmdlet, which then sets the primary server for the agent.

## PARAMETERS

### -Agent
Specifies an array of agent objects.
To obtain an **AgentManagedComputer** object, use the **Get-SCOMADAgent** cmdlet.

```yaml
Type: AgentManagedComputer[]
Parameter Sets: FromAgentPrimaryServer, FromAgentFailoverServer
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -FailoverServer
Specifies an array of management server objects for the agent to use as failover servers.
For information about how to get a management server object, type "`Get-Help Get-SCManagementServer`".

```yaml
Type: ManagementServer[]
Parameter Sets: FromAgentFailoverServer, FromGatewayFailoverManagementServer
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayServer
Specifies an array of gateway management server objects.
For information about how to get a management server object, type "`Get-Help Get-SCOMGatewayManagementServer`".

```yaml
Type: ManagementServer[]
Parameter Sets: FromGatewayManagementServer, FromGatewayFailoverManagementServer
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryServer
Specifies an array of management server object for the agent to use as its primary server.

```yaml
Type: ManagementServer
Parameter Sets: FromAgentPrimaryServer
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: ManagementServer
Parameter Sets: FromGatewayManagementServer
Aliases: 

Required: True
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
* You cannot modify both the primary and failover management servers in the same command. To modify both, run **Set-SCOMParentManagementServer** twice, as shown in the examples.

## RELATED LINKS

[Get-SCOMParentManagementServer](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMParentManagementServer.md)

