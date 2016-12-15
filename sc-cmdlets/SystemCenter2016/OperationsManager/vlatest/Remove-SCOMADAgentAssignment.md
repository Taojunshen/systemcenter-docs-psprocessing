---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239485
schema: 2.0.0
ms.assetid: F21A18CE-B2DE-4584-94F4-1BB77B4B17CF
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMADAgentAssignment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMADAgentAssignment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMADAgentAssignment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMADAgentAssignment

## SYNOPSIS
Removes AD DS agent assignments from the management group.

## SYNTAX

```
Remove-SCOMADAgentAssignment -AgentAssignment <AgentAssignment> -PrimaryServer <ManagementServer>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMADAgentAssignment** cmdlet removes Active Directory Domain Services (AD DS) agent assignments from the management group.

After you remove an agent assignment, the agent managed computers are not monitored by the management group.
The state of these computers changes to critical, because the computers no longer send heartbeats to the management group.
You can remove these computers from the management group and, if the computer is not assigned to other management groups, you can uninstall the System Center 2016 - Operations Manager agent.

## EXAMPLES

### Example 1: Remove an agent assignment by using the primary server
```
PS C:\>Get-SCOMManagementServer "OMServer01*" | Get-SCOMADAgentAssignment | Remove-SCOMADAgentAssignment
```

This command removes all AD DS agent assignments for a primary management server.
The command uses the **Get-SCOMManagementServer** cmdlet to get the management server named OMServer01, and passes the result to the **Get-SCOMADAgentAssignment** cmdlet by using the pipeline operator.

The command gets all AD DS agent assignments that have the primary server named OMServer01, and passes the results to the **Remove-SCOMADAgentAssignment** cmdlet by using the pipeline operator.
The command removes the agent assignments that have the primary server named OMServer01.

### Example 2: Remove an agent assignment by using the domain
```
PS C:\>Get-SCOMADAgentAssignment -Domain "contoso.com" | Remove-SCOMADAgentAssignment
```

This command gets all AD DS agent assignments for a domain.
The command uses the **Get-SCOMADAgentAssignment** cmdlet to get the AD DS agent assignment named contoso.com, and passes the result to the **Remove-SCOMADAgentAssignment** cmdlet by using the pipeline operator.
The command cmdlet removes the AD DS agent assignments for the domain named contoso.com.

## PARAMETERS

### -AgentAssignment
Specifies an **AgentAssignment** object.
To obtain an **AgentAssignment** object, use the **Get-SCOMADAgentAssignment** cmdlet.

```yaml
Type: AgentAssignment
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be running on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server for the target agent-managed computers.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

A connection object represents a connection to a management server.
The default is the current management group connection.

```yaml
Type: Connection[]
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

[Get-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMADAgentAssignment.md)

[Add-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMADAgentAssignment.md)

[Update-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMADAgentAssignment.md)

