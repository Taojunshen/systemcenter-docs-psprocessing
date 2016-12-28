---
external help file: OperationsManager-help.xml
online version: 
schema: 2.0.0
ms.assetid: 5D8D8956-5248-44A7-9729-DDC2882F017E
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMTierConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMTierConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMTierConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCOMTierConnector

## SYNOPSIS
Adds a connector to a management group tier.

## SYNTAX

```
Add-SCOMTierConnector -Connector <MonitoringConnector> -Tier <TieredManagementGroup> [-PassThru]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMTierConnector** cmdlet adds a connector to a System Center 2016 - Operations Manager management group tier.
Connectors communicate monitoring information between systems in a tiered management group.

## EXAMPLES

### Example 1: Add a connector to a tiered management group
```
PS C:\>$Tier = Get-SCOMTieredManagementGroup | Select-Object -First 1
PS C:\> Add-SCOMConnector -Name MyProductConnector | Add-SCOMTierConnector -Tier $Tier
```

This example adds a connector to an existing tiered management group.

The first command gets tiered management groups from the server, and passes them to the **Select-Object** cmdlet by using the pipeline operator.
That cmdlet selects the first tiered management group.
For more information, type `Get-Help Select-Object`.
The command stores the first tiered management group in the $Tier variable.

The second command adds a connector named MyProductConnector.
The command then passes output to the **Add-SCOMTierConnector** cmdlet by using the pipeline operator.
That cmdlet adds the connector to the tiered management group in the $Tier variable.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
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
Specifies the System Center 2016 - Operations Manager connector.

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

### -PassThru
Indicates that the cmdlet creates an object.
This parameter allows you to use this cmdlet in a pipeline.
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
Specifies the tiered management group in Operations Manager.

```yaml
Type: TieredManagementGroup
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

