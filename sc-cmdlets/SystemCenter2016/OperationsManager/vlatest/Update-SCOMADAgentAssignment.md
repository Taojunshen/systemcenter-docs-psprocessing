---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 771294B4-5C9B-459F-AF2D-9A01C059B76E
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Update-SCOMADAgentAssignment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Update-SCOMADAgentAssignment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Update-SCOMADAgentAssignment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCOMADAgentAssignment

## SYNOPSIS
Changes settings of an AD DS agent assignment.

## SYNTAX

```
Update-SCOMADAgentAssignment -AgentAssignment <AgentAssignment> -PrimaryServer <ManagementServer>
 [[-LdapQuery] <String>] [-Exclude <String[]>] [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCOMADAgentAssignment** cmdlet changes settings of an Active Directory Domain Services (AD DS) agent assignment.
You can use this cmdlet to change the LDAP query and exclusion list settings of the agent assignment.
To change other settings of the agent assignment, remove the agent assignment and re-create it.

## EXAMPLES

### Example 1: Change the LDAP query for an agent assignment
```
PS C:\>Get-SCOMADAgentAssignment -Domain "contoso.com" | Update-SCOMADAgentAssignment -LdapQuery "(&amp;(sAMAccountType=805306369)(name=SQLSERVER*))"
```

This command gets the AD DS agent assignment for a domain.
The command uses the **Get-SCOMADAgentAssignment** cmdlet to get the AD DS agent assignment named contoso.com, and passes the result to the **Update-SCOMADAgentAssignment** cmdlet by using the pipeline operator.
The command changes the LDAP query of the agent assignment for the domain named contoso.com to return only computers with names that match SQLSERVER.

## PARAMETERS

### -AgentAssignment
Specifies an **AgentAssignment** object.
To obtain an **AgentAssignment** object, use the **Get-SCOMADAgentAssignment** cmdlet.

```yaml
Type: AgentAssignment
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

### -Exclude
Specifies an array of names of computers.
Operations Manager excludes the computers that you specify from the agent assignment.
Operations Manager excludes these computers even if the LDAP query returns the computers.

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

### -LdapQuery
Specifies the LDAP query in the domain which selects the target agent computers.
If you do not specify this parameter, the cmdlet uses the current LDAP query.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
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

### -PrimaryServer
Specifies a **ManagementServer** object.
This parameter specifies the primary management server for the target agent-managed computers.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Add-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMADAgentAssignment.md)

[Remove-SCOMADAgentAssignment](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMADAgentAssignment.md)

