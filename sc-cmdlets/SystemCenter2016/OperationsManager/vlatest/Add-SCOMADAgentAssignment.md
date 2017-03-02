---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 72527656-23A5-48C1-B1D5-45E321F096FE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMADAgentAssignment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMADAgentAssignment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMADAgentAssignment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCOMADAgentAssignment

## SYNOPSIS
Assigns AD DS agent-managed computers to the management group.

## SYNTAX

```
Add-SCOMADAgentAssignment [-Domain] <String> [-PrimaryServer] <ManagementServer> [-LdapQuery] <String>
 [-RunAsProfile <ManagementPackSecureReference>] [-FailoverServer <ManagementServer[]>] [-Exclude <String[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMADAgentAssignment** cmdlet assigns one or more Active Directory Domain Services (AD DS) agent-managed computers to the System Center 2016 - Operations Manager management group.

Before you use this cmdlet to assign agent-managed computers to the management group, use MOMADAdmin.exe to create an AD DS container for an Operations Manager management group in the domain of the computers.

## EXAMPLES

### Example 1: Assign AD DS agent-managed computers to the management group
```
PS C:\>$PrimaryServer = Get-SCOMManagementServer -Name "DivMgmtSvr01.fabrikam.net"
PS C:\> $Ldap = "(&amp;(sAMAccountType=805306369)(name=SQLServer*))"
PS C:\> Add-SCOMADAgentAssignment -Domain "fabrikam.net" -PrimaryServer $PrimaryServer -LdapQuery $Ldap -Exclude "SQLServer05.fabrikam.net"
```

This example assigns an AD DS agent-managed computer to the management group.

The first command gets the management server object named DivMgmtSvr01.fabrikam.net, and stores the object in the $PrimaryServer variable.

The second command specifies an LDAP query that selects computers with names like SQLServer*.fabrikam.net, and stores the object in the $Ldap variable.

The third command assigns the AD DS agent-managed computers stored in $Ldap to the management group in the fabrikam.net domain.
The command excludes the computer named SQLServer05.fabrikam.net from the management group.

### Example 2: Set failovers for an AD DS agent assignment
```
PS C:\>$PrimaryServer = Get-SCOMManagementServer -Name "DivMgmtSvr01.fabrikam.net"
PS C:\> $Failovers = Get-SCOMManagementServer -Name "FabrikamSecondary*.fabrikam.net"
PS C:\> $RunAs = Get-SCOMRunAsProfile -Name "Active Directory Based Agent Assignment Account"
PS C:\> $Ldap = "(&amp;(sAMAccountType=805306369)(name=SQLServer*))"
PS C:\> Add-SCOMADAgentAssignment -Domain "fabrikam.net" -PrimaryServer $PrimaryServer -LdapQuery $Ldap -FailoverServer $Failovers -RunAsProfile $RunAs
```

This example assigns an AD DS agent-managed computer to the management group and sets the failovers for the agent.

The first command gets the management server object named DivMgmtSvr01.fabrikam.net, and stores the object in the $PrimaryServer variable.

The second command gets the management servers with a name like FabrikamSecondary*.fabrikam.net, and stores the objects in the $Failovers variable.

The third command gets the Runs As profile object named "Active Directory Based Agent Assignment Account" and stores the object in the $RunAs variable.

The fourth command specifies an LDAP query that selects computers with names like SQLServer*.fabrikam.net, and stores the result in the $Ldap variable.

The fifth command assigns the AD DS agent-managed computers stored in $Ldap to the management group in the fabrikam.net domain.
The command specifies the primary management server stored in $PrimaryServer for the agent-managed computers.
The command specifies the management servers stored in $Failovers as failovers for the agent-managed computers.
The command specifies the Run As profile stored in $RunAs for the agent-managed computers.

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

### -Domain
Specifies the name of the domain or domain controller in which the target agents reside.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude
Specifies an array of names of computers.
Operations Manager excludes the computers that you specify from the agent assignment.

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

### -FailoverServer
Specifies an array of names of **ManagementServer** objects.
This parameter specifies the management servers that Operations Manager uses as failovers for the target agents.

By default, Operations Manager uses all non-gateway management servers  for failover.

```yaml
Type: ManagementServer[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LdapQuery
Specifies the LDAP query in the domain which selects the target agent computers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server for the target agent-managed computer.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsProfile
Specifies the Run As profile that Operations Manager uses to run AD DS query workflow.

The Run As profile must be associated with the same RunAs account that you specify when you run MOMADAdmin.exe to create an AD DS container for a System Center 2016 - Operations Manager management group.

```yaml
Type: ManagementPackSecureReference
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

[Get-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMADAgentAssignment.md)

[Update-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMADAgentAssignment.md)

[Remove-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMADAgentAssignment.md)

