---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 78b47320-21b5-40fc-8452-ea9e6288e9e8
schema: 2.0.0
ms.assetid: 95E52FB5-3157-4C2B-81D2-9345F4B0C98C
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/Set-SCSpfTelemetry.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/Set-SCSpfTelemetry.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceProviderFoundation/v1/Set-SCSpfTelemetry.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSpfTelemetry

## SYNOPSIS
Sets telemetry.

## SYNTAX

### Empty (Default)
```
Set-SCSpfTelemetry [<CommonParameters>]
```

### FromTelemetryStateParameterSetName
```
Set-SCSpfTelemetry -Enabled <Boolean> [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSpfTelemetry** cmdlet enables or disables telemetry for Service Provider Foundation.

Microsoft collects diagnostic and usage data from Service Provider Foundation over the Internet.
Microsoft uses this data to improve the quality, security, and integrity of its products and services.
You can use this cmdlet to enable or disable the telemetry that Microsoft collects.

## EXAMPLES

### Example 1: Disable telemetry
```
PS C:\>Set-SCSPFTelemetry -Enabled $False
```

This command disables the sharing of diagnostics and usage data in Service Provider Foundation.

### Example 2: Enable telemetry
```
PS C:\>Set-SCSPFTelemetry -Enabled $True
```

This command enables diagnostics and usage data sharing in Service Provider Foundation.

## PARAMETERS

### -Enabled
Indicates whether telemetry is enabled.

```yaml
Type: Boolean
Parameter Sets: FromTelemetryStateParameterSetName
Aliases: 

Required: True
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

