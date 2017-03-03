---
external help file: OperationsManager-help.xml
online version: 
schema: 2.0.0
ms.assetid: AE1E75AC-89A1-462D-82CE-DF234A1A7098
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMTierConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMTierConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMTierConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCOMTierConnector

## SYNOPSIS
Removes a connector from a tiered management group.

## SYNTAX

```
Remove-SCOMTierConnector -Connector <MonitoringConnector> -Tier <TieredManagementGroup>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMTierConnector** cmdlet removes a connector from a tiered management group.
A tiered management group is part of a connected management group that has peer-to-peer connections between its members and that shares data in a single System Center 2016 - Operations Manager console.
Connectors communicate monitoring information between systems in a tiered management group.
Removing a connector from a tier stops the tier from transmitting monitoring information to the connector.

## EXAMPLES

### Example 1: Remove connectors from a management group
```
PS C:\>$Tier = Get-SCOMTieredManagementGroup | Select-Object -First 1
PS C:\> Get-SCOMTierConnector -Tier $Tier | Remove-SCOMTierConnector -Tier $Tier
```

This example clears all connectors from a tiered management group.

The first command uses the **Get-SCOMTieredManagementGroup** cmdlet to get tiered management groups from the server, and passes them to the **Select-Object** cmdlet by using the pipeline operator.
The **Select-Object** cmdlet selects the first tiered management group object, and stores that object in the $Tier variable.
For more information, type `Get-Help Select-Object`.

The second command gets the connectors from the tiered management group in the $Tier variable.
It then passes these connectors to the **Remove-SCOMTierConnector** cmdlet by using the pipeline operator.
The cmdlet removes the connectors from the tiered management group in $Tier.

## PARAMETERS

### -ComputerName
Specifies an array that contains the name of the computer with which to establish a connection.
Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, specify the computer name, localhost, or a dot (.).

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

### -Connector
Specifies the connector to remove.

```yaml
Type: MonitoringConnector
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -SCSession
Specifies an array of management group connection objects that contains a connection to a management server.
To get management group connection objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.
If you do not specify a value for this parameter, the default is the current management group connection.

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
Specifies the tiered management group from which to remove the connector.
To obtain a tiered management group object, use the **Get-SCOMTieredManagementGroup** cmdlet.

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

[Add-SCOMTierConnector](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMTierConnector.md)

[Add-SCOMTieredManagementGroup](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMTieredManagementGroup.md)

[Get-SCOMTierConnector](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMTierConnector.md)

[Get-SCOMTieredManagementGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMTieredManagementGroup.md)

[Remove-SCOMTieredManagementGroup](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMTieredManagementGroup.md)

