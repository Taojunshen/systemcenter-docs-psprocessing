---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=235484
schema: 2.0.0
ms.assetid: DB4D968F-A8EB-4ACC-BF16-D206ACCEAAAB
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Remove-SCOMLocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Remove-SCOMLocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Remove-SCOMLocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMLocation

## SYNOPSIS
Removes associations with a location or deletes a location.

## SYNTAX

### FromAgent (Default)
```
Remove-SCOMLocation [-Agent] <AgentManagedComputer[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementServer
```
Remove-SCOMLocation [-ManagementServer] <ManagementServer[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromPool
```
Remove-SCOMLocation [-Pool] <ManagementServicePool[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromLocation
```
Remove-SCOMLocation [-Location] <EnterpriseManagementObject[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMLocation** cmdlet removes the association of a location with an agent-managed computer, management server, or resource pool, or it deletes a location.
To remove an association, specify agent-managed computers, management servers, or resource pools.
To delete a location, specify the location by using the **Get-SCOMLocation** cmdlet.

You can change a location display name, a latitude, or a longitude by using the **Update-SCOMLocation** cmdlet.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### Example 1: Delete a location
```
PS C:\>$Location = Get-SCOMLocation -DisplayName "Seattle, WA"
PS C:\> Remove-SCOMLocation -Location $Location
```

This example deletes a location that has the display name Seattle, WA.
The first command gets the location object that has the display name Seattle, WA, and then stores the object in the $Location variable.

The second command deletes the location object stored in the $Location variable.

### Example 2: Remove an agent-managed computer from a location
```
PS C:\>$Agent = Get-SCOMAgent -Name "Server73.Contoso.com"
PS C:\> Remove-SCOMLocation -Agent $Agent
```

This example removes an agent-managed computer named Server73.Contoso.com from its location.
The first command gets the agent object for the computer named Server73.Contoso.com and then stores the object in the $Agent variable.

The second command removes the location association from the agent-managed computer object stored in the $Agent variable.
This command does not delete the location itself.

### Example 3: Remove a management server from a location
```
PS C:\>$MgmtServer = Get-SCOMManagementServer -Name "MgmtServer01.Contoso.com"
PS C:\> Remove-SCOMLocation -ManagementServer $MgmtServer
```

This example removes a management server from its location.
The first command gets the management server object named MgmtServer01.Contoso.com, and then stores the object in the $MgmtServer variable.

The second command removes the location association from the management server object stored in the $MgmtServer variable.
This command does not delete the location itself.

### Example 4: Remove a resource pool from a location
```
PS C:\>$Pool = Get-SCOMResourcePool -Name "Notifications Resource Pool"
PS C:\> Remove-SCOMLocation -Pool $Pool
```

This example removes a resource pool named Notifications Resource Pool from its location.
The first command gets the resource pool object for a resource pool named Notifications Resource Pool, and then stores the object in the $Pool variable.

The second command removes the location association from the resource pool object stored in the $Pool variable.
This command does not delete the location itself.

## PARAMETERS

### -Agent
Specifies an array of **AgentManagedComputer** objects.
To obtain an **AgentManagedComputer** object, use the **Get-SCOMAgent** cmdlet.

```yaml
Type: AgentManagedComputer[]
Parameter Sets: FromAgent
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
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

### -Location
Specifies an array of locations as **EnterpriseManagementObject** objects.
To obtain a location, use the **Get-SCOMLocation** cmdlet.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromLocation
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementServer
Specifies an array of management server objects.
To obtain a management server object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer[]
Parameter Sets: FromManagementServer
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Pool
Specifies an array of resource pool objects.
To obtain a resource pool object, use the **Get-SCOMResourcePool** cmdlet.

```yaml
Type: ManagementServicePool[]
Parameter Sets: FromPool
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

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

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMManagementServer.md)

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMResourcePool.md)

[Get-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMLocation.md)

[New-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1.0/New-SCOMLocation.md)

[Set-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1.0/Set-SCOMLocation.md)

[Update-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1.0/Update-SCOMLocation.md)

