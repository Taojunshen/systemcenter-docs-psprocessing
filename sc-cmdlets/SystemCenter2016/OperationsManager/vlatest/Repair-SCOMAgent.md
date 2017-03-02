---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 50654ED1-9037-417F-AC72-0ADF94365E34
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Repair-SCOMAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Repair-SCOMAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Repair-SCOMAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Repair-SCOMAgent

## SYNOPSIS
Repairs Operations Manager agents.

## SYNTAX

```
Repair-SCOMAgent [-Actionaccount <PSCredential>] -Agent <AgentManagedComputer[]> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-SCOMAgent** cmdlet repairs one or more System Center 2016 - Operations Manager agent installations.

## EXAMPLES

### Example 1: Repair an Operations Manager agent
```
PS C:\>Get-SCOMAgent -DNSHostName "server01.contoso.com" | Repair-SCOMAgent
```

This command repairs an agent installation.
The command uses the **Get-SCOMAgent** cmdlet to get the Operations Manager agent named server01.contoso.com, and passes the result to the **Repair-SCOMAgent** cmdlet by using the pipe operator.
The second command repairs the agent named server01.contoso.com.

## PARAMETERS

### -Actionaccount
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
This parameter specifies the Operations Manager agents to repair.
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsAccount.md)

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMManagementServer.md)

[Uninstall-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Uninstall-SCOMAgent.md)

[Install-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Install-SCOMAgent.md)

