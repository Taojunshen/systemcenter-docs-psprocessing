---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187735
schema: 2.0.0
ms.assetid: B35D90D0-75A4-4C5B-882F-8B2D54E2D3A9
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Uninstall-SCOMAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Uninstall-SCOMAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Uninstall-SCOMAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Uninstall-SCOMAgent

## SYNOPSIS
Uninstalls agents from agent-managed computers.

## SYNTAX

```
Uninstall-SCOMAgent [-ActionAccount <PSCredential>] -Agent <AgentManagedComputer[]> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-SCOMAgent** cmdlet uninstalls agents from agent-managed computers.
Before you uninstall an agent, you must remove the Active Directory Domain Services (AD DS) agent assignments from the management group.
You can use the **Remove-SCOMADAgentAssignment** cmdet to remove AD DS agent assignments from the management group.

## EXAMPLES

### Example 1: Uninstall an agent
```
PS C:\>Get-SCOMAgent -DNSHostName "server01.contoso.com" | Uninstall-SCOMAgent
```

The first command gets the Operations Manager agent object named server01.contoso.com and passes it to the **Uninstall-SCOMAgent** cmdlet by using the pipeline operator.
The second command uninstalls the agent named server01.contoso.com.

### Example 2: Uninstall an agent by using an object variable
```
PS C:\>$Agent = Get-SCOMAgent -DNSHostName "server01.contoso.com"
PS C:\> Uninstall-SCOMAgent -Agent $Agent
```

This example uninstalls the Operations Manager agent on an agent-managed computer.

The first command gets the agent-managed computer object named server01.contoso.com and stores the object in the $Agent variable.

The second command uninstalls the agent stored in $Agent.

### Example 3: Uninstall an agent by using an action account
```
PS C:\>$Agent = Get-SCOMAgent -DNSHostName "server01.contoso.com"
PS C:\> Uninstall-SCOMAgent -Agent $Agent -ActionAccount (Get-Credential)
```

This example uninstalls the Operations Manager agent on an agent-managed computer after the user enters the credentials that Operations Manager requires to uninstall the agent.

The first command gets the agent object named server01.contoso.com and stores the object in the $Agent variable.

The second command prompts the user to enter the credentials that Operations Manager uses to uninstall an agent.
The command then uninstalls the agent stored in $Agent.

## PARAMETERS

### -ActionAccount
Specifies a **PSCredential** object.
This parameter specifies the credentials that Operations Manager uses to run the deployment task.
If you do not specify this parameter or you specify a null value, Operations Manager uses the default action account of the management server for the agent.

To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

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

### -Agent
Specifies an array of **AgentManagedComputer** objects.
This parameter specifies the Operations Manager agents to uninstall.
To obtain an **AgentManagedComputer** object, use the **Get-SCOMADAgent** cmdlet.

```yaml
Type: AgentManagedComputer[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### Microsoft.EnterpriseManagement.Administration.AgentManagedComputer

## OUTPUTS

### Microsoft.EnterpriseManagement.Administration.AgentTaskResult

## NOTES

## RELATED LINKS

[Get-SCOMAgent](xref:OperationsManager/v1/Get-SCOMAgent.md)

[Install-SCOMAgent](xref:OperationsManager/v1/Install-SCOMAgent.md)

[Get-SCOMRunAsAccount](xref:OperationsManager/v1/Get-SCOMRunAsAccount.md)

[Get-SCOMManagementServer](xref:OperationsManager/v1/Get-SCOMManagementServer.md)

[Repair-SCOMAgent](xref:OperationsManager/v1/Repair-SCOMAgent.md)

