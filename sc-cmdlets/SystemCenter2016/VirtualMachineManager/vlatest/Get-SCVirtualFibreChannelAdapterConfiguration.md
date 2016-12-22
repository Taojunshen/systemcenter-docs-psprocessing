---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5FEF391E-3AD7-4AC1-8FFC-FDAC7F72DFBC
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFibreChannelAdapterConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFibreChannelAdapterConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFibreChannelAdapterConfiguration.md
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

[Set-SCVirtualFibreChannelAdapterConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFibreChannelAdapterConfiguration.md)

