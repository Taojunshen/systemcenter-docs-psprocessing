---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 79F2B971-4FD4-47F6-B3CE-FA9B1264D05F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSSASConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSSASConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSSASConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSSASConnection

## SYNOPSIS
Gets the existing SQL Server Analysis Services connection.

## SYNTAX

```
Get-SCSSASConnection [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSSASConnection** cmdlet gets the existing SQL Server Analysis Services (SSAS) connection from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Get the existing SSAS connection
```
PS C:\> Get-SCSSASConnection
```

This command gets the existing SSAS connection and displays information about the connection.

## PARAMETERS

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

### SQLAnalysisServicesServer
This cmdlet returns a **SQLAnalysisServicesServer** object.

## NOTES

## RELATED LINKS

[New-SCSSASConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCSSASConnection.md)

[Remove-SCSSASConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSSASConnection.md)

