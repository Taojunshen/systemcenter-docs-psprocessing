---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 8c527413-7fbe-4db2-90be-40c1ee50a1c7
schema: 2.0.0
ms.assetid: 5DF5980F-B09D-443E-B1B4-3D47254AFDBD
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Update-SCXAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Update-SCXAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Update-SCXAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCXAgent

## SYNOPSIS
Upgrades the management agent on the specified UNIX and Linux computers to the latest version available.

## SYNTAX

```
Update-SCXAgent -Agent <IPersistedUnixComputer[]> [-WsManCredential <PSCredential>]
 [-SshCredential <CredentialSet>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCXAgent** cmdlet updates the agent on the specified computers to the latest version available.
If the latest available version of the management agent is already installed a targeted computer, no action is taken.

The required *Agent* parameter specifies the targeted managed UNIX and Linux computers to uninstall and requires a UNIX and Linux computer object.
For information about retrieving managed UNIX and Linux computers, see the Get-SCXAgent cmdlet.
This cmdlet accepts *SshCredential* and *WsManCredential* input parameters.
The supplied *SshCredential* parameter is used for privileged agent update actions while the supplied *WsManCredential* is used for low-privileged agent communication.
If the *SshCredential* parameter is not provided, the cmdlet attempts to use the defined agent maintenance Run As account associated with the targeted computer.

The output of this cmdlet is an array of managed UNIX or Linux computer objects representing the targeted systems that were successfully updated.

## EXAMPLES

### Example 1: Update a management agent
```
PS C:\>$Agent01 = Get-SCXAgent -Name "nx1.contoso.com"
PS C:\> $WSCredential = Get-Credential "DavidChew"
PS C:\> $SSHCredential = Get-SCXSSHCredential -UserName "DavidChew" -Key "C:\keys\key21.ppk" -ElevationType sudo
PS C:\> Update-SCXAgent -SSHCredential $SSHCredential -WSManCredential $WSCredential -Agent $Agent01
```

The first command gets the agent for a managed Linux or UNIX computer named nx1.contoso.com by using the Get-SCXAgent cmdlet.
The command stores it in the $Agent01 variable.

The second command gets a credential for a user by using the Get-Credential cmdlet.
The command prompts you for authentication, and then stores the results in the $WSCredential variable.

The third command creates a privileged credential for a user by using the Get-SCXSSHCredential cmdlet.
The command stores the result in the $SSHCredential variable.

The final command updates the management agent in $Agent01 with the values from the second and third commands.

### Example 2: Update a management agent with the defined Run As account
```
PS C:\>Get-SCXAgent -Name "nx1.contoso.com" | Update-SCXAgent
```

This command gets the agent for a managed Linux or UNIX computer named nx1.contoso.com by using **Get-SCXAgent**.
The command passes the managed computer to the current cmdlet.
The command updates the management agent by using the defined Run As account.

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
Specifies a privileged *SshCredential* parameter used to perform the agent update actions.
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

### -WsManCredential
Specifies a credential used for low-privileged agent communication through WSMan.
This cmdlet uses this credential to verify agent availability.

Type a user name, such as User01 or enter a **PSCredential** object, such as one that is returned by the Get-Credential cmdlet.
When you type a user name, you are prompted for a password.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Unix.Computer[]
This cmdlet returns a collection of upgrade results, each representing the upgrade status for a computer.
Each result must contain the following information: 

- Hostname 
- Operating systems 
- Old Agent version 
- New Agent version 
- upgrade status 
- Description

The description includes the details of why an upgrade failed.

## NOTES
* This cmdlet takes in a collection of host names in enumerated fashion. It collects all host names and processes the entire collection in parallel at the end of the pipeline.

## RELATED LINKS

[Get-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Get-SCXAgent.md)

[Install-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Install-SCXAgent.md)

[Remove-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Remove-SCXAgent.md)

[Uninstall-SCXAgent](xref:SystemCenter2016/OperationsManager/v1/Uninstall-SCXAgent.md)

