---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 81B8CFAA-6C11-44B9-B3E3-DE898DC74715
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCAdvisorAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCAdvisorAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCAdvisorAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCAdvisorAgent

## SYNOPSIS
Adds Windows-based computers or instance groups to the group of agents that report to the Advisor Connector.

## SYNTAX

```
Add-SCAdvisorAgent [-InputObjects <PartialMonitoringObject[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCAdvisorAgent** cmdlet adds Windows-based computers or instance groups to the group of agents that report to the System Center Advisor Connector.

## EXAMPLES

### Example 1: Add Windows-based computers to the connector for the current management group
```
PS C:\>$WindowsComputers = Get-SCClass -Name "Microsoft.Windows.computer" | Get-SCOMClassInstance
PS C:\> Add-SCAdvisorAgent -InputObjects $WindowsComputers
```

The first command uses the Get-SCClass cmdlet to get all the Windows-based computers, and then passes them to the Get-SCOMClassInstance cmdlet by using the pipeline operator.
The command stores the instances of Windows-based computers in the $WindowsComputers variable.

The second command adds all the Windows-based computers that are stored in $WindowsComputers to the group of agents that report to the Advisor Connector.

### Example 2: Add Windows computers to the connector for a specified computer
```
PS C:\>$WindowsComputers = Get-SCClass -Name Microsoft.Windows.computer | Get-SCOMClassInstance -ComputerName "Computer073"
PS C:\> Add-SCAdvisorAgent -InputObjects $WindowsComputers -ComputerName "Computer073"
```

The first command uses **Get-SCClass** to get all the Windows-based computers, and then passes them to **Get-SCOMClassInstance** by using the pipeline operator.
The command connects to the computer Computer073, and then stores the instances of Windows-based computers in the $WindowsComputers variable.

The second command adds all the Windows-based computers that are stored in $WindowsComputers to the group of agents that report to the Advisor Connector.

## PARAMETERS

### -InputObjects
Specifies an array of computer names to opt in to the Advisor Connector.

```yaml
Type: PartialMonitoringObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be active on the computer.
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
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
For more information about credential objects, type `Get-Help Get-Credential`.

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

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, use the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter is not specified, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

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

[Get-SCAdvisorAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCAdvisorAgent.md)

[Get-SCClass](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCClass.md)

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCManagementGroupConnection](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCManagementGroupConnection.md)

[Remove-SCAdvisorAgent](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCAdvisorAgent.md)

