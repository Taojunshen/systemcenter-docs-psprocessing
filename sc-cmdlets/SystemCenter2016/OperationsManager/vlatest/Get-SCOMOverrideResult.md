---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=231734
schema: 2.0.0
ms.assetid: AA7514F0-77F8-407F-907F-49010FD9BEC7
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMOverrideResult.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMOverrideResult.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMOverrideResult.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMOverrideResult

## SYNOPSIS
Retrieves override results.

## SYNTAX

### FromClassDiscovery (Default)
```
Get-SCOMOverrideResult [-Class] <ManagementPackClass[]> [-Discovery] <ManagementPackDiscovery[]>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassMonitor
```
Get-SCOMOverrideResult [-Class] <ManagementPackClass[]> [-Monitor] <ManagementPackMonitor[]>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassRule
```
Get-SCOMOverrideResult [-Class] <ManagementPackClass[]> [-Rule] <ManagementPackRule[]>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromInstanceRule
```
Get-SCOMOverrideResult [-Instance] <EnterpriseManagementObject[]> [-Rule] <ManagementPackRule[]>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromInstanceDiscovery
```
Get-SCOMOverrideResult [-Instance] <EnterpriseManagementObject[]> [-Discovery] <ManagementPackDiscovery[]>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromInstanceMonitor
```
Get-SCOMOverrideResult [-Instance] <EnterpriseManagementObject[]> [-Monitor] <ManagementPackMonitor[]>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMOverrideResult** cmdlet retrieves existing overrides associated with specified workflows that are constrained to a specified class or class instance.

## EXAMPLES

### Example 1: Retrieve a list of overrides for a specific class
```
PS C:\>$Class = Get-SCOMClass -DisplayName "Memory"
PS C:\> $Discovery = Get-SCOMDiscovery -DisplayName "Discover Windows Server Computers"
PS C:\> $Session = Get-SCOMManagementGroupConnection -ComputerName "Server01.Contoso.com"
PS C:\> Get-SCOMOverrideResult -Class $Class -Discovery $Discovery -SCSession $Session
```

This example gets the override result for a specific class.

The first command uses the **Get-SCOMClass** cmdlet to get the class object named Memory and stores the object in the $Class variable.

The second command uses the **Get-SCOMDiscovery** cmdlet to get the discovery object with the display name Discover Windows Server Computers, and stores the object in the $Discovery variable.

The third command uses the **Get-SCOMManagementGroupConnection** cmdlet to get the management group connection object for Server01 and stores the object in the $Session variable.

The last command uses the **Get-SCOMOverrideResult** cmdlet to get the list of overrides for the specified discovery, scoped to the specified class, for the specified management group connection, and returns information about the override result to the user.

### Example 2: Retrieve override results by class instance
```
PS C:\>$Instance = Get-SCOMClassInstance -DisplayName "Operations Manager Agents"
PS C:\> $Monitor = Get-SCOMMonitor -DisplayName "Management Service connectivity state"
PS C:\> Get-SCOMOverrideResult -Instance $Instance -Monitor $Monitor
```

This example gets the override result for a specific class instance.

The first command uses the **Get-SCOMClassInstance** cmdlet to get the class instance object named Operations Manager Agents and stores the object in the $Instance variable.

The second command uses the **Get-SCOMMonitor** cmdlet to get the monitor object with the display name Management Service connectivity state and stores the object in the $Monitor variable.

The last command uses the **Get-SCOMOverrideResult** cmdlet to get the override result for the specified instance and monitor, and returns information about the override result to the user.

### Example 3: Retrieve override results by monitoring rule object
```
PS C:\>$Rule = Get-SCOMRule -DisplayName "Alert on Failed Power Shell Scripts"
PS C:\> Get-SCOMClass -DisplayName "Memory" | Get-SCOMOverrideResult -Rule $Rule
```

This example gets the override result for a monitoring rule object.

The first command uses the **Get-SCOMRule** cmdlet to get the monitoring rule object with the display name Alert on Failed Power Shell Scripts and stores the object in the $Rule variable.

The second command uses the **Get-SCOMClass** cmdlet to get the class object named Memory and uses the pipeline operator to pass the object to the **Get-SCOMOverrideResult** cmdlet, which gets the override result for the specified rule, scoped to the piped class object.

### Example 4: Retrieve override results for a display name
```
PS C:\>$Discovery = Get-SCOMDiscovery -DisplayName "Discover Windows Server Computers"
PS C:\> Get-SCOMClassInstance -DisplayName "Operations Manager Agents" | Get-SCOMOverrideResult -Discovery $Discovery
```

This example gets the override result for a specific display name.

The first command uses the **Get-SCOMDiscovery** cmdlet to get the discovery object with the display name Discover Windows Server Computers and stores the object in the $Discovery variable.

The second command uses the **Get-SCOMClassInstance** cmdlet to get the class instance object named Operations Manager Agents and uses the pipeline operator to pass the object to **Get-SCOMOverrideResult** which gets the override result for the specified discovery, scoped to the piped class instance object.

## PARAMETERS

### -Class
Specifies an array of management pack class objects.
For more information about how to get a management pack class object, type"`Get-Help Get-SCOMClass`".

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromClassDiscovery, FromClassMonitor, FromClassRule
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
For more information, type "`Get-Help Get-Credential`".

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

### -Discovery
Specifies an array of discovery workflow objects to retrieve.
For more information about how to get discovery workflow objects, type"`Get-Help Get-SCOMDiscovery`".

```yaml
Type: ManagementPackDiscovery[]
Parameter Sets: FromClassDiscovery, FromInstanceDiscovery
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance
Specifies an array of instances of a class to retrieve.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromInstanceRule, FromInstanceDiscovery, FromInstanceMonitor
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Monitor
Specifies an array of monitor workflow objects to retrieve.
For more information, type"`Get-Help Get-SCOMMonitor`".

```yaml
Type: ManagementPackMonitor[]
Parameter Sets: FromClassMonitor, FromInstanceMonitor
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies an array of monitoring rule workflow objects to retrieve.
For information about how to get a rule object, type"`Get-Help Get-SCOMRule`".

```yaml
Type: ManagementPackRule[]
Parameter Sets: FromClassRule, FromInstanceRule
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

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

[Get-SCOMMonitor](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMMonitor.md)

[Get-SCOMRule](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRule.md)

