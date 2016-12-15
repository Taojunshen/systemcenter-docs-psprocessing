---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 3ffd34f8-0d88-4740-b321-323be5fb894c
schema: 2.0.0
ms.assetid: 0AD56461-3484-425A-B8C3-A4A002132B12
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCXResourcePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCXResourcePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCXResourcePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCXResourcePool

## SYNOPSIS
Changes the managing resource pool for the targeted managed UNIX and Linux computers.

## SYNTAX

```
Set-SCXResourcePool -Agent <IPersistedUnixComputer[]> -ResourcePool <ManagementServicePool>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCXResourcePool** cmdlet changes the managing resource pool for the targeted managed UNIX and Linux computers.

## EXAMPLES

### Example 1: Move an agent to a resource pool
```
PS C:\>$Pool = Get-SCOMResourcePool -DisplayName "Pool 1"
PS C:\> Get-SCXAgent -Name "scxserver1.contoso.com" | Set-SCXResourcePool -ResourcePool $Pool
```

The first command gets the resource pool named Pool 1 by using the Get-SCOMResourcePool cmdlet, and then stores it in the $Pool01.

The second command moves an agent to the resource pool in $Pool01.

### Example 2: Move all the agents in a pool to a different pool
```
PS C:\>$Pool01 = Get-SCOMResourcePool -DisplayName "Pool 1"
PS C:\> $Pool02 = Get-SCOMResourcePool -DisplayName "Pool 2"
PS C:\> $Agents = Get-SCXAgent -ResourcePool $Pool01
PS C:\> Set-SCXResourcePool -Agent $Agents -ResourcePool $Pool02
```

The first command gets the resource pool named Pool 1 by using **Get-SCOMResourcePool**, and then stores it in the $Pool01.

The second command gets the resource pool named Pool 2, and then stores it in the $Pool02.

The third command gets all the agents from $Pool01 by using the Get-SCXAgent cmdlet.

The final command moves all UNIX and Linux agents in $Agents to $Pool02.

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

### -ResourcePool
Specifies a resource pool of servers, one of which is assigned to be the current management server and the other serving as backup management servers.
This parameter requires a resource pool object and returns only the managed computers in that resource pool.

For information about how to get a resource pool object, type `Get-Help Get-SCOMResourcePool`.

```yaml
Type: ManagementServicePool
Parameter Sets: (All)
Aliases: 

Required: True
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

## NOTES

## RELATED LINKS

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md)

[Get-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCXAgent.md)

