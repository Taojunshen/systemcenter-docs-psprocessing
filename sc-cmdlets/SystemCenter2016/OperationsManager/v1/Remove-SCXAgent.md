---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 8c527413-7fbe-4db2-90be-40c1ee50a1c7
schema: 2.0.0
ms.assetid: AD9486BA-8C38-4147-9E67-2DF5305A3DEA
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Remove-SCXAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Remove-SCXAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Remove-SCXAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCXAgent

## SYNOPSIS
Removes the targeted managed UNIX and Linux computers from the management group.

## SYNTAX

```
Remove-SCXAgent -Agent <IPersistedUnixComputer[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCXAgent** cmdlet removes the targeted managed UNIX and Linux computers from the management group.
Managed UNIX and Linux computers are passed to the **Remove-SCXAgent** cmdlet as an array of UNIX and Linux computer objects.

For information about retrieving managed UNIX and Linux computers, see the Get-SCXAgent cmdlet.

This cmdlet does not return any output.

## EXAMPLES

### Example 1: Remove management agents
```
PS C:\>$Agents = Get-SCXAgent -Name "scxserver1.contoso.com","scxserver2*","*.development.contoso.com"
PS C:\> Remove-SCXAgent -Agent $Agents
```

The first command gets agents for managed Linux or UNIX computers that match the specified names by using the Get-SCXAgent cmdlet.
The command stores the results in the $Agents array variable.

The final command removes the agents in $Agents.

### Example 2: Uninstall a management agent with the defined Run As account
```
PS C:\>Get-SCXAgent -Name "scxserver1.contoso.com","scxserver2*","*.development.contoso.com" | Remove-SCXAgent
```

This command gets agents for managed Linux or UNIX computer that match the specified names by using **Get-SCXAgent**.
The command passes the agents to the current cmdlet.
The command removes the management agents.

## PARAMETERS

### -Agent
Specifies one or more managed UNIX and Linux computer objects.
For information about how to get a managed UNIX or Linux computer object, type `Get-Help Get-SCXAgent`.

```yaml
Type: IPersistedUnixComputer[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.
There is no failure case for the **Remove-SCXAgent** cmdlet.

## NOTES

## RELATED LINKS

[Get-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Get-SCXAgent.md)

[Install-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Install-SCXAgent.md)

[Uninstall-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Uninstall-SCXAgent.md)

[Update-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Update-SCXAgent.md)

