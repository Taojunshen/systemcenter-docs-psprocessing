---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProductionVirtualName.md
schema: 2.0.0
ms.assetid: 3A4199DA-6427-4EE8-B496-BB8659191627
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProductionCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProductionCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProductionCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMProductionCluster

## SYNOPSIS
Gets clusters on which the DPM agent is installed.

## SYNTAX

```
Get-DPMProductionCluster [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMProductionCluster** cmdlet gets all clusters on which the System Center 2016 - Data Protection Manager (DPM) agent is installed.

## EXAMPLES

### Example1: Get clusters for a server
```
PS C:\>Get-DPMProductionCluster -DPMServerName "DPMServer02"
```

This command gets the clusters for the DPM server named DPMServer02.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.
If you do not specify a name, the cmdlet uses the name of the current computer.

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

### Cluster

## NOTES

## RELATED LINKS

[Get-DPMProductionVirtualName](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProductionVirtualName.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/v1.0/DataProtectionManager.md)
