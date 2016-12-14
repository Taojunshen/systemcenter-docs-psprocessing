---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=235479
schema: 2.0.0
ms.assetid: F9AF6C29-E38B-4FEE-9168-2E4FA230BB0F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Set-SCOMLocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Set-SCOMLocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Set-SCOMLocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMLocation

## SYNOPSIS
Associates agent-managed computers, management servers, or resource pools with a location.

## SYNTAX

### FromAgent (Default)
```
Set-SCOMLocation [-Agent] <AgentManagedComputer[]> -Location <EnterpriseManagementObject> [-PassThru]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromManagementServer
```
Set-SCOMLocation [-ManagementServer] <ManagementServer[]> -Location <EnterpriseManagementObject> [-PassThru]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromPool
```
Set-SCOMLocation [-Pool] <ManagementServicePool[]> -Location <EnterpriseManagementObject> [-PassThru]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMLocation** cmdlet associates one or more agent-managed computers, management servers, or resource pools with a location.
This cmdlet removes a current association, if one exists.
The Web Application Availability Monitoring Summary Map Dashboard displays state information for agents, management servers, and resource pools associated with a location.

You can remove an association by using the **Remove-SCOMLocation** cmdlet.
You can create a location by using the **New-SCOMLocation** cmdlet.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### Example 1: Associate an agent with a location
```
PS C:\>$Location = Get-SCOMLocation -DisplayName "Seattle, WA"
PS C:\> $Agent = Get-SCOMAgent -Name "Server01.Contoso.com"
PS C:\> Set-SCOMLocation -Location $Location -Agent $Agent
```

This example associates an agent-managed computer named Sever01.Contoso.com with the location Seattle, WA.
The first command gets the location object that has the display name of Seattle, WA, and then stores the object in the $Location variable.

The second command gets the agent object named Server01.Contoso.com, and then stores the object in the $Agent variable.

The third command associates the location stored in the $Location variable with the agent-managed computer stored in the $Agent variable.
If you previously associated this agent-managed computer with a location, the command removes that association.

### Example 2: Associate a management server with a location
```
PS C:\>$Location = Get-SCOMLocation -DisplayName "New York, NY"
PS C:\> $MgmtServer = Get-SCOMManagementServer -Name "MgmtServer01.Contoso.com"
PS C:\> Set-SCOMLocation -Location $Location -ManagementServer $MgmtServer
```

This example associates a management server named MgmtServer01.Contoso.com with the location New York, NY.
The first command gets the location object that has the display name of New York, NY, and then stores the object in the $Location variable.

The second command gets the management server object named MgmtServer01.Contoso.com, and stores the object in the $MgmtServer variable.

The third command associates the location stored in the $Location variable with the management server stored in the $MgmtServer variable.
If you previously associated this management server with a location, the command removes that association.

### Example 3: Associate a resource pool to a location
```
PS C:\>$Location = Get-SCOMLocation -DisplayName "Paris, FR"
PS C:\> $Pool = Get-SCOMResourcePool -Name "Notifications Resource Pool"
PS C:\> Set-SCOMLocation -Location $Location -Pool $Pool
```

This example associates a resource pool named Notifications Resource Pool with the location Paris, FR.
The first command gets the location object that has the display name Paris, FR, and then stores the object in the $Location variable.

The second command gets the resource pool named Notifications Resource Pool, and then stores the object in the $Pool variable.

The third command associates the location stored in the $Location variable with the resource pool stored in the $Pool variable.
If you previously associated the resource pool with a location, the command removes that association.

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
Specifies a location as an **EnterpriseManagementObject** object.
To obtain a location, use the **Get-SCOMLocation** cmdlet.

```yaml
Type: EnterpriseManagementObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-SCOMAgent](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMAgent.md)

[Get-SCOMManagementServer](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMManagementServer.md)

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMResourcePool.md)

[Get-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMLocation.md)

[New-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1/New-SCOMLocation.md)

[Remove-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1/Remove-SCOMLocation.md)

[Update-SCOMLocation](xref:SystemCenter2016/OperationsManager/v1/Update-SCOMLocation.md)

