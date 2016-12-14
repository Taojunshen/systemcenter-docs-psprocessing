---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMGlobalProperty.md
schema: 2.0.0
ms.assetid: A473C727-2800-4568-A1B5-0914A8E1CC34
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMGlobalProperty.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMGlobalProperty.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMGlobalProperty.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMGlobalProperty

## SYNOPSIS
Retrieves the global properties for a DPM server.

## SYNTAX

```
Get-DPMGlobalProperty [[-DPMServerName] <String>] [-PropertyName] <GlobalProperties> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMGlobalProperty** cmdlet retrieves the global properties for a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Retrieve global properties
```
PS C:\>Get-DPMGlobalProperty -PropertyName AllowLocalDataProtection
```

This command uses the **Get-DPMGlobalProperty** cmdlet to retrieve the global property for local data protection on a server.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server of which this cmdlet gets properties.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertyName
Specifies a property that this cmdlet gets properties.

The acceptable values for this parameter are:

- IsNetworkChecksumRequired
- TruncateSharePointDbLogs
- LibraryRefreshInterval
- OptimizeTapeUsage
- TapeWritePeriodRatio
- ExchangeSCRProtection
- AllowLocalDataProtection

```yaml
Type: GlobalProperties
Parameter Sets: (All)
Aliases: 
Accepted values: IsNetworkChecksumRequired, TruncateSharePointDbLogs, LibraryRefreshInterval, ExchangeSCRProtection, AllowLocalDataProtection, RegisteredWriters, ConsiderForAutoDeployment, MaxCapacityForClientAutoDeployment, KnownVMMServers, HyperVPagefileExclusions

Required: True
Position: 2
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

[Set-DPMGlobalProperty](xref:SystemCenter2016/DataProtectionManager/v1.0/Set-DPMGlobalProperty.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/v1.0/DataProtectionManager.md)

