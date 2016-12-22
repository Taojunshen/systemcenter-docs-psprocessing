---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B35D90D0-75A4-4C5B-882F-8B2D54E2D3A9
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Uninstall-SCOMAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Uninstall-SCOMAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Uninstall-SCOMAgent.md
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

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgent.md)

[Install-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Install-SCOMAgent.md)

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsAccount.md)

[Get-SCOMManagementServer](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMManagementServer.md)

[Repair-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Repair-SCOMAgent.md)

