---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: dd490ed7-43ea-41e4-b24c-5fc7ae529858
schema: 2.0.0
ms.assetid: 2EFB0A6F-A22A-425D-8DDB-21C48BC31367
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTag.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTag.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCTag.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCTag

## SYNOPSIS
Gets existing tags.

## SYNTAX

```
Get-SCTag [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCTag** cmdlet gets all existing user-defined tags.

## EXAMPLES

### Example 1: Get all tags on a specified VMM management server
```
PS C:\> Get-SCTag -VMMServer "VMMServer01"
```

This command gets all tags on VMMServer01.

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

### String[]
This cmdlet returns an array of **String** objects.

## NOTES

## RELATED LINKS

