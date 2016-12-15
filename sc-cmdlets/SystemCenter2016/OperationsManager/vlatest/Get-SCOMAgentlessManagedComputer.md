---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187737
schema: 2.0.0
ms.assetid: A4707627-D268-482B-B0EB-3BE8F5902457
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgentlessManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgentlessManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgentlessManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMAgentlessManagedComputer

## SYNOPSIS
Gets managed computers that do not have Operations Manager agents.

## SYNTAX

### Empty (Default)
```
Get-SCOMAgentlessManagedComputer [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromAgentManagedBy
```
Get-SCOMAgentlessManagedComputer [-ManagedByAgent] <AgentManagedComputer[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementServerManagedBy
```
Get-SCOMAgentlessManagedComputer [-ManagedByManagementServer] <ManagementServer[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCOMAgentlessManagedComputer [-DNSHostName] <String[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMAgentlessManagedComputer** cmdlet gets managed computers that do not have System Center 2016 - Operations Manager agents.

## EXAMPLES

### Example 1: Get agentless managed computers by using a name
```
PS C:\>Get-SCOMAgentlessManagedComputer -DNSHostName "server01","server0*"
```

This command gets the agentless managed computer named server01 and agentless managed computers that have a name that begins with server0.

### Example 2: Get agentless managed computers managed by an agent
```
PS C:\>Get-SCOMAgent -DNSHostName "contoso01" | foreach {Get-SCAgentlessManagedComputer -ManagedByAgent $_}
```

This command gets a list of agentless computers managed by Operations Manager agent.
The command uses the **Get-SCOMAgent** cmdlet to get the Operations Manager agent named contoso01, and passed the result to the **Foreach-Object** cmdlet.
The command gets all agentless managed computers managed by the Operations Manager agent named contoso01.

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

### -ManagedByAgent
Specifies an array of **AgentManagedComputer** objects.
This parameter specifies the Operations Manager agent that performs agentless monitoring.
The action account of the agent that performs the monitoring must have local administrative rights on the computer that it monitors.

To obtain an **AgentManagedComputer** object, use the **Get-SCOMAgent** cmdlet.

```yaml
Type: AgentManagedComputer[]
Parameter Sets: FromAgentManagedBy
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedByManagementServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server that performs agentless monitoring of the agentless managed computers.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer[]
Parameter Sets: FromManagementServerManagedBy
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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
Specifies the name of a Domain Name System (DNS) host.

```yaml
Type: String[]
Parameter Sets: FromName
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

## NOTES

## RELATED LINKS

[Add-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMAgentlessManagedComputer.md)

[Set-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMAgentlessManagedComputer.md)

[Get-SCOMAgentlessManagedComputer](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgentlessManagedComputer.md)

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMManagementServer.md)

