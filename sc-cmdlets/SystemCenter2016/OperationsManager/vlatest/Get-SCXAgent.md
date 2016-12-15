---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 3ffd34f8-0d88-4740-b321-323be5fb894c
schema: 2.0.0
ms.assetid: 8C527413-7FBE-4DB2-90BE-40C1EE50A1C7
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCXAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCXAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCXAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCXAgent

## SYNOPSIS
Gets a list of managed UNIX and Linux computers in a management group.

## SYNTAX

### Empty (Default)
```
Get-SCXAgent [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromAgentNamesParameterSetName
```
Get-SCXAgent [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromAgentGuidsParameterSetName
```
Get-SCXAgent -ID <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromResourcePoolParameterSetName
```
Get-SCXAgent -ResourcePool <ManagementServicePool> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCXAgent** cmdlet retrieves the managed UNIX and Linux computers that match the provided selection criteria.
If no selection criteria are specified, all managed UNIX and Linux computers in the management group are returned.

Results are returned as an array of managed UNIX and Linux computer objects.

## EXAMPLES

### Example 1: Return managed UNIX and Linux computers
```
PS C:\>Get-SCXAgent
```

This command returns all managed UNIX and Linux computers in the resource pool.

### Example 2: Return managed UNIX and Linux computers from a resource pool
```
PS C:\>$ResourcePool = Get-SCOMResourcePool -DisplayName "pool01"
PS C:\> Get-SCXAgent -ResourcePool $ResourcePool
```

The first command gets a resource pool by using the Get-SCOMResourcePool cmdlet, and stores it in the $ResourcePool variable.

The second command returns all managed UNIX and Linux computers for the resource pool in $ResourcePool.

### Example 3: Return managed UNIX and Linux computers by using the name
```
PS C:\>Get-SCXAgent -Name "nx1.contoso.com,nx2.*","*.development.contoso.com"
```

This command returns managed UNIX and Linux computers with names that match a provided list of strings.

### Example 4: Return managed UNIX and Linux computers by using the pipeline
```
PS C:\>"server1", "server2", "server3" | Get-SCXAgent
```

This command provides the *Name* parameter through the pipeline.

### Example 5: Connect to a resource pool and get a managed computer by name
```
PS C:\>Get-SCXAgent -Name "*development.contoso.com" -ComputerName "server1.contoso.com"
```

This command connects to a resource pool with a temporary connection, by using the current user's credentials, and returns only the managed computers that match the **Name** property.

## PARAMETERS

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

### -ID
Specifies the ID of a managed UNIX or Linux computer object.
Returns only the only managed computers with ID properties that match this value.
This parameter is accepted from the pipeline.

```yaml
Type: Guid[]
Parameter Sets: FromAgentGuidsParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a list of fully qualified domain names for one or more managed UNIX and Linux computers.
Returns only the managed computers that match the **Name** property.

You can include wildcards, in which case all computers matching the wildcard are returned.
For information about using wildcards, type `Get-Help About_Wildcards`.

This parameter is accepted from the pipeline.

```yaml
Type: String[]
Parameter Sets: FromAgentNamesParameterSetName
Aliases: DisplayName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePool
Specifies a resource pool of servers, one of which is assigned to be the current management server and the other serving as backup management servers.
This parameter requires a resource pool object and returns only the managed computers in that resource pool.

For information about how to get a **SCOMResourcePool** object, type `Get-Help Get-SCOMResourcePool`.

```yaml
Type: ManagementServicePool
Parameter Sets: FromResourcePoolParameterSetName
Aliases: RP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Unix.Computer[]
This cmdlet returns one or more Computer objects that represent managed UNIX and Linux computers when the UNIX and Linux computers match input criteria.

## NOTES

## RELATED LINKS

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md)

[Install-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Install-SCXAgent.md)

[Remove-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCXAgent.md)

[Uninstall-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Uninstall-SCXAgent.md)

[Update-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCXAgent.md)

