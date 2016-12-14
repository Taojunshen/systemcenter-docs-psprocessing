---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187736
schema: 2.0.0
ms.assetid: 105302A4-83DF-4FD8-B0BB-678D579DA205
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Add-SCOMAgentlessManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Add-SCOMAgentlessManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Add-SCOMAgentlessManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCOMAgentlessManagedComputer

## SYNOPSIS
Adds agentless-managed computers to a management group.

## SYNTAX

### FromAgentManagedBy
```
Add-SCOMAgentlessManagedComputer [-ManagedByAgent] <AgentManagedComputer> [-DNSHostName] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromManagementServerManagedBy
```
Add-SCOMAgentlessManagedComputer [-ManagedByManagementServer] <ManagementServer> [-DNSHostName] <String[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMAgentlessManagedComputer** cmdlet adds one or more managed computers that do not have System Center 2016 - Operations Manager agents to a management group.
Specify the *ManagedByAgent* parameter to have a managed agent, called a proxy agent, monitor the agentless managed computers.
Specify the *ManagedByManagementServer* parameter to have a management server monitor the agentless-managed computers.

## EXAMPLES

### Example 1: Add an agentless- managed computer to a management group-
```
PS C:\>Add-SCOMAgentlessManagedComputer -DNSHostName "server01.contoso.com" -ManagedByManagementServer (Get-SCOMManagementServer -ComputerName "MgmtServer01.Contoso.com") -Confirm
```

This command specifies that the management server named MgmtServer01 performs agentless monitoring of the computer named server01.
The *Confirm* parameter specifies that the cmdlet prompts the user to confirm the operation before the command runs.

## PARAMETERS

### -ManagedByAgent
Specifies an **AgentManagedComputer** object.
This parameter specifies the Operations Manager agent that performs agentless monitoring of the agentless-managed computers.
The action account of the agent that performs the monitoring must have local administrative rights on the computer that it monitors.

To obtain an **AgentManagedComputer** object, use the **Get-SCOMADAgent** cmdlet.

```yaml
Type: AgentManagedComputer
Parameter Sets: FromAgentManagedBy
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedByManagementServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server that performs agentless monitoring of the agentless-managed computers.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: FromManagementServerManagedBy
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DNSHostName
Specifies an array of names of Domain Name System (DNS) hosts.
This parameter specifies the agentless-managed computers that you want to add to the management group.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Get-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMAgentlessManagedComputer.md)

[Set-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/v1.0/Set-SCOMAgentlessManagedComputer.md)

