---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Set-SCVirtualFibreChannelAdapterConfiguration.md
schema: 2.0.0
ms.assetid: 5FEF391E-3AD7-4AC1-8FFC-FDAC7F72DFBC
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualFibreChannelAdapterConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualFibreChannelAdapterConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualFibreChannelAdapterConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualFibreChannelAdapterConfiguration

## SYNOPSIS
Gets a Virtual Fibre Channel adapter configuration for a virtual machine configuration.

## SYNTAX

```
Get-SCVirtualFibreChannelAdapterConfiguration [-VMMServer <ServerConnection>]
 -VMConfiguration <VMConfiguration> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualFibreChannelAdapterConfiguration** cmdlet gets the Virtual Fibre Channel adapter configuration for a virtual machine configuration.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -VMConfiguration
Specifies a virtual machine configuration object.

```yaml
Type: VMConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
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

[Set-SCVirtualFibreChannelAdapterConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVirtualFibreChannelAdapterConfiguration.md)
