---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B14A1D36-724F-458A-88A0-C63E6F06FBAE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMDiskRescan.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMDiskRescan.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMDiskRescan.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMDiskRescan

## SYNOPSIS
Scans for disks and disk configuration changes.

## SYNTAX

```
Start-DPMDiskRescan [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMDiskRescan** cmdlet scans for new disks and disk configuration changes on a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Scan a disk for configuration changes
```
PS C:\>Start-DPMDiskRescan -DPMServerName "Contoso-DPMServer"
```

This command scans a DPM server for new disks or changes to disk configurations.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server that this cmdlet scans.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Job

## NOTES

## RELATED LINKS

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

