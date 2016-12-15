---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: c3fd9539-4364-4dc7-9a67-b7243decfed3
schema: 2.0.0
ms.assetid: 9745A271-4F85-49AF-B881-D63F9D0712A6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCDefaultGateway.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCDefaultGateway.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCDefaultGateway.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCDefaultGateway

## SYNOPSIS
Creates a default gateway object that is used when creating or modifying static IP address pools.

## SYNTAX

### Automatic (Default)
```
New-SCDefaultGateway [-VMMServer <ServerConnection>] -IPAddress <String> [-Automatic] [<CommonParameters>]
```

### ByMetric
```
New-SCDefaultGateway [-VMMServer <ServerConnection>] -IPAddress <String> -Metric <Int32> [<CommonParameters>]
```

## DESCRIPTION
The **New-SCDefaultGateway** cmdlet creates a Virtual Machine Manager (VMM) default gateway object that is used when creating or modifying static IP address pools.
The default metric is automatic; to change this setting, use the *Metric* parameter.

## EXAMPLES

### Example 1: Create a default gateway object with an automatically calculated metric
```
PS C:\>$Gateway = New-SCDefaultGateway -IPAddress 10.0.0.1 -Automatic
```

This command creates a gateway object with an IP address of 10.0.0.1, automatically computes the metric for the gateway object, and then stores the object in the $Gateway variable.

### Example 2: Create a default gateway object and manually set its metric
```
PS C:\>$Gateway = New-SCDefaultGateway -IPAddress 10.0.1.1 -Metric 10
```

This command creates a gateway object with an IP address of 10.0.0.1, sets its metric to 10, and then stores the object in the $Gateway variable.

## PARAMETERS

### -Automatic
Indicates if the metric associated with a network gateway is automatically computed.

```yaml
Type: SwitchParameter
Parameter Sets: Automatic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an IPv4 or IPv6 address.

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
Specifies a numerical metric associated with a network gateway.

```yaml
Type: Int32
Parameter Sets: ByMetric
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

### DefaultGateway
This cmdlet returns a **DefaultGateway** object.

## NOTES

## RELATED LINKS

