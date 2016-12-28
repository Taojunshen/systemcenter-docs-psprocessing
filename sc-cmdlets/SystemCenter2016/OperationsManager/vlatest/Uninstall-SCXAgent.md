---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 24FAA327-4BE6-46F3-9EF8-CE73DCDDE685
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Uninstall-SCXAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Uninstall-SCXAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Uninstall-SCXAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Uninstall-SCXAgent

## SYNOPSIS
Uninstalls the management agent on the specified managed UNIX and Linux computers.

## SYNTAX

```
Uninstall-SCXAgent -Agent <IPersistedUnixComputer[]> [-SshCredential <CredentialSet>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-SCXAgent** cmdlet uninstalls the management agent on the specified UNIX and Linux computers.

The required *Agent* parameter specifies the targeted managed UNIX or Linux computers to uninstall and requires a UNIX or Linux computer object.
For information about retrieving managed UNIX or Linux computers, see the Get-SCXAgent cmdlet.
An optional *SSHCredential* parameter can be specified to identify the privileged credential used for uninstallation of the management agent.
If the *SSHCredential* is not specified, the cmdlet attempts to use the defined privileged Run As account for the agent.

This cmdlet does not return any output.

## EXAMPLES

### Example 1: Uninstall a management agent
```
PS C:\>$Agent01 = Get-SCXAgent -Name "nx1.contoso.com"
PS C:\> $SSHCredential = Get-SCXSSHCredential -UserName "DavidChew" -Key "C:\keys\key21.ppk" -ElevationType sudo
PS C:\> Uninstall-SCXAgent -SSHCredential $SSHCredential -Agent $Agent01
```

The first command gets the agent for a managed Linux or UNIX computer named nx1.contoso.com by using the Get-SCXAgent cmdlet.
The command stores it in the $Agent01 variable.

The second command creates a privileged credential for a user by using the Get-SCXSSHCredential cmdlet.
The command stores the result in the $SSHCredential variable.

The final command uninstalls the management agent in $Agent01 by using a specified SSH credential.

### Example 2: Uninstall a management agent with the defined Run As account
```
PS C:\>Get-SCXAgent -Name "nx1.contoso.com" | Uninstall-SCXAgent
```

This command gets the agent for a managed Linux or UNIX computer named nx1.contoso.com by using **Get-SCXAgent**.
The command passes the managed computer to the current cmdlet.
The command uninstalls the management agent by using the defined Run As account.

## PARAMETERS

### -Agent
Specifies one or more managed UNIX or Linux computer objects.
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

### -SshCredential
Specifies a privileged SSH credential used to perform the agent maintenance actions.
If this parameter is not specified, the cmdlet attempts to use the defined agent maintenance Run As account for the agent.

For information about how to get an SSH credential object, type `Get-Help Get-SCXSSHCredential`.

```yaml
Type: CredentialSet
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
This cmdlet returns results, which represent the uninstall status for a computer.
The results contain the following information: 

- Host name 
- Uninstall status 
- Description

The description includes the details of why an uninstall failed.

## NOTES

## RELATED LINKS

[Get-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCXAgent.md)

[Install-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Install-SCXAgent.md)

[Remove-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCXAgent.md)

[Update-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCXAgent.md)

