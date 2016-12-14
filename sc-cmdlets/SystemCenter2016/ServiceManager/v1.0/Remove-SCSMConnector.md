---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225363
schema: 2.0.0
ms.assetid: C8487696-AE0F-462F-9D9E-166006D37D05
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Remove-SCSMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Remove-SCSMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Remove-SCSMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMConnector

## SYNOPSIS
Removes a connector from Service Manager.

## SYNTAX

```
Remove-SCSMConnector [-Connector] <Connector[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMConnector** cmdlet removes a connector from Service Manager.

## EXAMPLES

### Example 1: Removed enabled connectors by using a display name
```
PS C:\>Get-SCSMConnector | Where-Object { $_.displayname -eq "AD Connector" -and $_.enabled} | Remove-SCSMConnector
```

This command removes all connectors that are enabled and that are named AD Connector.
The command uses the Get-SCSMConnector cmdlet to get all Service Manager connectors.
The command passes the results to the Where-Object cmdlet, which passes on only those that meet the specified criteria.
The current cmdlet removes those connectors.

## PARAMETERS

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

### -Connector
Specifies the connector object that this cmdlet removes from the system.

```yaml
Type: Connector[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Connectors.Connector
You can pipe a Service Manager connector to the *Connector* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMConnector](xref:SystemCenter2016/ServiceManager/v1.0/Get-SCSMConnector.md)

[Start-SCSMConnector](xref:SystemCenter2016/ServiceManager/v1.0/Start-SCSMConnector.md)

[Update-SCSMConnector](xref:SystemCenter2016/ServiceManager/v1.0/Update-SCSMConnector.md)

