---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMBackupNetworkAddress.md
schema: 2.0.0
ms.assetid: A27ABF28-89DC-4852-B628-7FB78E0294AD
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMBackupNetworkAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMBackupNetworkAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMBackupNetworkAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMBackupNetworkAddress

## SYNOPSIS
Gets addresses of backup networks for a DPM server.

## SYNTAX

```
Get-DPMBackupNetworkAddress [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMBackupNetworkAddress** cmdlet gets addresses of backup networks for a System Center 2016 - Data Protection Manager (DPM) server.
DPM lets you configure backup network addresses so that DPM backups do not slow down your primary network.

## EXAMPLES

### Example 1: Get a backup network
```
PS C:\>Get-DPMBackupNetworkAddress -DpmServerName "DPMServer07"
```

This command gets the backup network or networks defined for a DPM server named DPMServer07.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets addresses.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-DPMBackupNetworkAddress](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMBackupNetworkAddress.md)

[Remove-DPMBackupNetworkAddress](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMBackupNetworkAddress.md)

