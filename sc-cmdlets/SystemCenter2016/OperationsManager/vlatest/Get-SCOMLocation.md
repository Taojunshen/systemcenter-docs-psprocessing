---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4C6DF93E-5A78-43EE-A1F4-B77159BFA24F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMLocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMLocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMLocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOMLocation

## SYNOPSIS
Gets locations.

## SYNTAX

### Empty (Default)
```
Get-SCOMLocation [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromAgent
```
Get-SCOMLocation [-Agent] <AgentManagedComputer[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementServer
```
Get-SCOMLocation [-ManagementServer] <ManagementServer[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromPool
```
Get-SCOMLocation [-Pool] <ManagementServicePool[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromDisplayName
```
Get-SCOMLocation [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMOIdParameterSetName
```
Get-SCOMLocation -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMLocation** cmdlet gets locations.
Specify locations to get by display name or ID, or by specifying associated agents, management servers, or resource pools.

You can create a location by using the **New-SCOMLocation** cmdlet.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### Example 1: Get a location by display name
```
PS C:\>Get-SCOMLocation -DisplayName "Seattle, WA"
```

This command gets the location that has the display name Seattle, WA.

### Example 2: Get the location of an agent-managed computer
```
PS C:\>$Agent = Get-SCOMAgent -Name "Server01.Contoso.com"
PS C:\> Get-SCOMLocation -Agent $Agent
```

This example gets a location for an agent-managed computer.
The first command gets the agent object for an agent-managed computer named Server01.Contoso.com and then stores the object in the $Agent variable.

The second command gets the location for the agent object stored in the $Agent variable.

### Example 3: Get the location of a management server
```
PS C:\>$MgmtSvr = Get-SCOMManagementServer -Name "MgmtServer01.Contoso.com"
PS C:\> Get-SCOMLocation -ManagementServer $MgmtSvr
```

This example gets the location for a management server named MgmtServer01.Contoso.com.
The first command gets the management server object for the management server named MgmtServer01.Contoso.com, and then stores the object in the $MgmtSvr variable.

The second command gets the location for the management server object stored in the $MgmtSvr variable.

### Example 4: Get the location of a resource pool
```
PS C:\>$Pool = Get-SCOMResourcePool -Name "Pool01"
PS C:\> Get-SCOMLocation -Pool $Pool
```

This example gets a location for the resource pool named Pool01.
The first command gets the resource pool object for the resource pool named Pool01 and stores the object in the $Pool variable.

The second command gets the location for the pool stored in the $Pool variable.

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

### -DisplayName
Specifies an array of display names.
Values for this parameter depend on which localized management packs you import and the locale of the user that runs Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
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

### -Id
Specifies an array of unique IDs of locations.

```yaml
Type: Guid[]
Parameter Sets: FromEMOIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMManagementServer.md)

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md)

[New-SCOMLocation](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMLocation.md)

[Remove-SCOMLocation](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMLocation.md)

[Set-SCOMLocation](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMLocation.md)

[Update-SCOMLocation](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMLocation.md)

