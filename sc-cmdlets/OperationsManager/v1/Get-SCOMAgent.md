---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187686
schema: 2.0.0
ms.assetid: 2BECB23F-FE62-46E6-A4FD-D62287D82D82
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMAgent

## SYNOPSIS
Gets the agent-managed computers in a management group.

## SYNTAX

### Empty (Default)
```
Get-SCOMAgent [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementServer
```
Get-SCOMAgent [-ManagementServer] <ManagementServer> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromAgentNames
```
Get-SCOMAgent [-DNSHostName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMAgent** cmdlet gets the agent-managed computers in a management group.
You can specify the *DNSHostName* parameter to get the agent-managed computers on a Domain Name System (DNS) host, or you can specify the *ManagementServer* parameter to get all the child agent-managed computers for a primary management server.

## EXAMPLES

### Example 1: Get all agents in the management group
```
PS C:\>Get-SCOMAgent -ComputerName "Server01.Contoso.Com"
```

This command establishes a temporary connection with the computer named Server01 and gets all agents in the management group.

### Example 2: Get the agents managed by a management server
```
PS C:\>$MgmtServer = Get-SCOMManagementServer "MgmtServer01.Contoso.com"
PS C:\> Get-SCOMAgent -ManagementServer $MgmtServer
```

This example gets agent-managed computers that are managed by a management server.

The first command gets the management server object named MgmtServer01.Contoso.com and stores the object in the $MgmtServer variable.

The second command gets the agents that are managed by the management server stored in $MgmtServer.

### Example 3: Get agents in a management group by using the agent name
```
PS C:\>Get-SCOMAgent -DNSHostName "server01.contoso.com", "Server02*", "*.Contoso.com"
```

This command gets agents that are named server01.contoso.com, that have a name that begins with Server02, and that are in the Contoso.com domain.

### Example 4: Get all agents in a domain
```
PS C:\>Get-SCOMAgent -DNSHostName "*.Contoso.com" -ComputerName "Server01.Contoso.com"
```

This command establishes a temporary connection with the computer named Server01.Contoso.com and gets all agents in the Contoso.com domain.

## PARAMETERS

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

### -ManagementServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server from which to retrieve all child agents.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: FromManagementServer
Aliases: MS

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -DNSHostName
Specifies the name of a Domain Name System (DNS) host of the agent-managed computer.

```yaml
Type: String[]
Parameter Sets: FromAgentNames
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.EnterpriseManagement.Administration.AgentManagedComputer

## NOTES

## RELATED LINKS

[Install-SCOMAgent](xref:OperationsManager/v1/Install-SCOMAgent.md)

[Uninstall-SCOMAgent](xref:OperationsManager/v1/Uninstall-SCOMAgent.md)

[Repair-SCOMAgent](xref:OperationsManager/v1/Repair-SCOMAgent.md)

[Get-SCOMAgent](xref:OperationsManager/v1/Get-SCOMAgent.md)

