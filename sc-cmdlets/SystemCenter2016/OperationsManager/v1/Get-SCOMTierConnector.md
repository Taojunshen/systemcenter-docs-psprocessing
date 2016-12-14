---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239448
schema: 2.0.0
ms.assetid: 228671ED-D5BE-4E69-AEF5-2AB694B14473
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMTierConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMTierConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMTierConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMTierConnector

## SYNOPSIS
Gets the connectors associated with a tiered management group.

## SYNTAX

### Empty (Default)
```
Get-SCOMTierConnector -Tier <TieredManagementGroup> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### Name
```
Get-SCOMTierConnector -Name <String[]> -Tier <TieredManagementGroup> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### DisplayName
```
Get-SCOMTierConnector [-DisplayName] <String[]> -Tier <TieredManagementGroup> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### Id
```
Get-SCOMTierConnector -Id <Guid[]> -Tier <TieredManagementGroup> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMTierConnector** cmdlet gets the connectors associated with a tiered management group.
A tiered management group is part of a connected management group that has peer-to-peer connections between its members and that shares data in a single System Center 2016 - Operations Manager console.

## EXAMPLES

### Example 1: Get connectors for all tiered management groups
```
PS C:\>Get-SCOMTieredManagementGroup | Get-SCOMTierConnector
```

This command gets all connectors for all tiered management groups.
The command uses the **Get-SCOMTieredManagementGroup** cmdlet to get management groups and pass them to the **Get-SCOMTierConnector** cmdlet by using the pipeline operator.

### Example 2: Get connectors for a tiered management group
```
PS C:\>Get-SCOMTieredManagementGroup -Name "ContosoTier" | Get-SCOMTierConnector -Name "*MyConnector*"
```

This command gets all connectors that have MyConnector in their names for the management group named ContosoTier.
The command uses the **Get-SCOMTieredManagementGroup** cmdlet to get the management group named ContosoTier and passes that management group to the **Get-SCOMTierConnector** cmdlet by using the pipeline operator.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The computer must run the System Center Data Access service.

If you do not specify this parameter, the default is the computer for the current management group connection.

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

### -DisplayName
Specifies an array of display names for connectors.

```yaml
Type: String[]
Parameter Sets: DisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an array of connector IDs.

```yaml
Type: Guid[]
Parameter Sets: Id
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of connector names.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If you do not specify a value for this parameter, the cmdlet uses the active persistent connection to a management group.
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

### -Tier
Specifies the management group tier.

```yaml
Type: TieredManagementGroup
Parameter Sets: (All)
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

[Add-SCOMTierConnector](xref:SystemCenter2016/OperationsManager/v1/Add-SCOMTierConnector.md)

[Add-SCOMTieredManagementGroup](xref:SystemCenter2016/OperationsManager/v1/Add-SCOMTieredManagementGroup.md)

[Get-SCOMTierConnector](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMTierConnector.md)

[Get-SCOMTieredManagementGroup](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMTieredManagementGroup.md)

[Remove-SCOMTieredManagementGroup](xref:SystemCenter2016/OperationsManager/v1/Remove-SCOMTieredManagementGroup.md)

[Remove-SCOMTierConnector](xref:SystemCenter2016/OperationsManager/v1/Remove-SCOMTierConnector.md)

