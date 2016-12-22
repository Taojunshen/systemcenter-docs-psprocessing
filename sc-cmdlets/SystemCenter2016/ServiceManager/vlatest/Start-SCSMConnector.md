---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E4B7EF3F-A099-48CB-A3E5-E48735C2B0C9
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Start-SCSMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Start-SCSMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Start-SCSMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCSMConnector

## SYNOPSIS
Initiates a synchronization of a Service Manager connector.

## SYNTAX

```
Start-SCSMConnector [-Connector] <Connector[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCSMConnector** cmdlet initiates a synchronization of a Service Manager connector.
You cannot initiate synchronization for a connector that is currently disabled.

## EXAMPLES

### Example 1: Start a connector synchronization
```
PS C:\>Get-SCSMConnector | Start-SCSMConnector
```

This command gets the connector by using the Get-SCSMConnector cmdlet.
The command passes that result to the current cmdlet by using the pipeline operator.
That cmdlet starts synchronization for that connector.

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
Specifies the connector for which this cmdlet initiates synchronization.

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

### -PassThru
Indicates that this cmdlet returns the connector that it synchronized.
You can pass this object to other cmdlets.

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
You can pipe a connector to the *Connector* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMConnector.md)

[Remove-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMConnector.md)

[Update-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMConnector.md)

