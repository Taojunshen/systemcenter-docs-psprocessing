---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNetworkRoute.md
schema: 2.0.0
ms.assetid: FAB212CF-270B-41DD-A317-5CAEC8023130
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNetworkRoute.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNetworkRoute.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNetworkRoute.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCNetworkRoute

## SYNOPSIS
Creates a network route.

## SYNTAX

```
New-SCNetworkRoute [-VMMServer <ServerConnection>] -DestinationPrefix <String> -NextHop <String>
 [-Metric <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCNetworkRoute** cmdlet creates a network route.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DestinationPrefix
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metric
Specifies a numerical metric associated with a network route.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHop
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

[Add-SCNetworkRoute](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNetworkRoute.md)

[Get-SCNetworkRoute](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkRoute.md)

[Remove-SCNetworkRoute](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNetworkRoute.md)

