---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187734
schema: 2.0.0
ms.assetid: 7CA21EF2-C12B-4F3E-8D97-FA13D80008DF
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Install-SCOMAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Install-SCOMAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Install-SCOMAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Install-SCOMAgent

## SYNOPSIS
Deploys Operations Manager agents.

## SYNTAX

```
Install-SCOMAgent [-ActionAccount <PSCredential>] [-AgentActionAccount <PSCredential>] -DNSHostName <String[]>
 -PrimaryManagementServer <ManagementServer> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-SCOMAgent** cmdlet deploys one or more System Center 2016 - Operations Manager agents by using client push installation.

## EXAMPLES

### Example 1: Install an agent on a server
```
PS C:\>$PrimaryMgmtServer = Get-SCOMManagementServer -ComputerName "MgmtServer01.Contoso.com"
PS C:\> Install-SCOMAgent -DNSHostName "server01.contoso.com" -PrimaryManagementServer $PrimaryMgmtServer
```

This example installs an agent on a server and sets the primary management server for the agent.

The first command gets the management server object named MgmtServer01.Contoso.com and stores the object in the $PrimaryMgmtServer variable.

The second command installs an agent on Server01.Contoso.com, and sets its primary management server to the management server stored in $PrimaryMgmtServer.

### Example 2: Install an agent on a server by using the action account credentials
```
PS C:\>$InstallAccount = Get-Credential
PS C:\> $PrimaryMgmtServer = Get-SCOMManagementServer -ComputerName "MgmtServer01.Contoso.com"
PS C:\> Install-SCOMAgent -DNSHostName "Server01.Contoso.com" -PrimaryManagementServer $PrimaryMgmtServer -ActionAccount $InstallAccount
```

This example prompts the user to enter credentials and then uses the credentials to install an agent.

The first command prompts the user for credentials and store credentials in the $InstallAccount variable.

The second command gets the management server object named MgmtServer01.Contoso.com and stores the object in the $PrimaryMgmtServer variable.

The third command installs an agent on Server01.Contoso.com by using the credentials stored in $InstallAccount, and sets the primary management server for the agent to the management server stored in $PrimaryMgmtServer.

### Example 3: Install an agent on servers and set the agent action account
```
PS C:\>$Agents = "DC1.contoso.com","DC2.contoso.com","DC3.contoso.com"
PS C:\> $InstallAccount = Get-Credential
PS C:\> $AgentActionAccount = Get-Credential Contoso\ActionAccount
PS C:\> $PrimaryMgmtServer = Get-SCOMManagementserver -ComputerName MgmtServer01.contoso.com
PS C:\> $Install-SCOMAgent -DNSHostName $Agents -PrimaryManagementServer $PrimaryMgmtServer -ActionAccount $InstallAccount -AgentActionAccount $AgentActionAccount -Confirm
```

This example installs agents on three computers and sets the agent action account for the agents.

The first command stores the name of three computers in the $Agents variable.

The second command prompts the user for credentials and stores the credentials in the $InstallAccount variable.

The third command prompts the user for a password for a user account named ActionAccount in the Contoso domain, and stores the credentials in the $AgentActionAccount variable.

The fourth command gets the management server object named MgmtServer01.Contoso.com and stores the object in the $PrimaryMgmtServer variable.

The fifth command installs an agent on the three computers stored in the $Agents variable by using the credentials stored in $InstallAccount.
The command sets the primary management server for the agent to the management server stored in $PrimaryMgmtServer, and sets the agent action account to the ActionAccount user stored in $AgentActionAccount.

## PARAMETERS

### -ActionAccount
Specifies a **PSCredential** object.
This parameter specifies the credentials that Operations Manager uses to run the deployment task.
If you do not specify this parameter or you specify a null value, Operations Manager uses the default action account of the management server for the agent.

This parameter does not specify the action account that the agent uses after you install it on the computer.
By default, the action account that the agent uses is set to Local System.
You can use the **AgentActionAccount** parameter to change the action account that the agent uses.

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

### -AgentActionAccount
Specifies a **PSCredential** object.
This parameter specifies the action account that the agent uses after it is installed on the computer.
By default, the action account that the agent uses is set to Local System.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.
You can use the **Get-SCOMRunAsProfile** cmdlet to get a Run As accounts that you can use for the action account.

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

### -PrimaryManagementServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server for the agent.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DNSHostName
Specifies the name of a Domain Name System (DNS) host.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Get-SCOMRunAsAccount](xref:OperationsManager/v1/Get-SCOMRunAsAccount.md)

[Get-SCOMAgent](xref:OperationsManager/v1/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:OperationsManager/v1/Get-SCOMManagementServer.md)

[Uninstall-SCOMAgent](xref:OperationsManager/v1/Uninstall-SCOMAgent.md)

[Repair-SCOMAgent](xref:OperationsManager/v1/Repair-SCOMAgent.md)

